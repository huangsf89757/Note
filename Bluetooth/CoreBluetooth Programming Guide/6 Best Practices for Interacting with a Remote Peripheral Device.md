# Best Practices for Interacting with a Remote Peripheral Device 与远程外围设备交互的最佳实践

The Core Bluetooth framework makes many of the central-side transactions transparent to your app. That is, your app has control over, and is responsible for, implementing most aspects of the central role, such as device discovery and connectivity, and exploring and interacting with a remote peripheral’s data. This chapter provides guidelines and best practices for harnessing this level of control in a responsible way, especially when developing your app for an iOS device.
Core Bluetooth框架使许多中心端事务对您的应用透明，也就是说，您的应用可以控制并负责实现中心角色的大多数方面，例如设备发现和连接，以及探索远程外设的数据并与之交互。本章提供了以负责任的方式利用这种级别的控制的指导原则和最佳实践，尤其是在为iOS设备开发应用时。



## Be Mindful of Radio Usage and Power Consumption 注意无线电使用和功耗

When developing an app that interacts with Bluetooth low energy devices, remember that Bluetooth low energy communication shares your device’s radio to transmit signals over the air. Since other forms of wireless communication may need to use your device’s radio—for instance, Wi-Fi, classic Bluetooth, and even other apps using Bluetooth low energy—develop your app to minimize how much it uses the radio.
在开发与低功耗蓝牙设备交互的应用时，请记住，低功耗蓝牙通信会共享设备的无线电以通过无线方式传输信号。由于其他形式的无线通信可能需要使用设备的无线电（例如Wi-Fi、经典蓝牙，甚至其他使用低功耗蓝牙的应用），因此开发应用时应尽量减少无线电的使用量。

Minimizing radio usage is especially important when developing an app for an iOS device, because radio usage has an adverse effect on an iOS device’s battery life. The following guidelines will help you be a good citizen of your device’s radio. As a result, your app will perform better and your device’s battery will last longer.
在为iOS设备开发应用时，尽量减少无线电的使用尤为重要，因为无线电的使用会对iOS设备的电池寿命产生不利影响。以下指南将帮助您成为设备无线电的好公民。因此，您的应用程序的性能将更好，设备的电池续航时间也将更长。



### Scan for Devices Only When You Need To 仅在需要时扫描设备

When you call the `scanForPeripheralsWithServices:options:` method of the `CBCentralManager` class to discover remote peripheral’s that are advertising services, your central device uses its radio to listen for advertising devices until you explicitly tell it to stop.
当您调用 `CBCentralManager` 类的 `scanForPeripheralsWithServices:options:` 方法来发现作为广告服务的远程外围设备时，您的中央设备将使用其无线电侦听广告设备，直到您明确告诉它停止。

Unless you need to discover more devices, stop scanning for other devices after you have found one you want to connect to. Use the `stopScan` method of the `CBCentralManager` class to stop scanning for other devices, as shown in [Connecting to a Peripheral Device After You’ve Discovered It](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW4).
除非您需要发现更多设备，否则请在找到要连接的设备后停止扫描其他设备。使用 `CBCentralManager` 类的 `stopScan` 方法停止扫描其他设备，如发现外围设备后连接到外围设备中所示。



### Specify the CBCentralManagerScanOptionAllowDuplicatesKey Option Only When Necessary 仅在必要时指定CBCentralManagerScanOptionAllowDuplicatesKey选项

Remote peripheral devices may send out multiple advertising packets per second to announce their presence to listening centrals. When you are scanning for devices using the `scanForPeripheralsWithServices:options:` method, the default behavior of the method is to coalesce multiple discoveries of an advertising peripheral into a single discovery event—that is, the central manager calls the `centralManager:didDiscoverPeripheral:advertisementData:RSSI:` method of its delegate object for each new peripheral it discovers, regardless of how many advertising packets it receives. The central manager also calls this delegate method when the advertisement data of an already-discovered peripheral changes.
远程外围设备可以每秒发出多个通告分组，以向监听中心通告它们的存在。当您使用 `scanForPeripheralsWithServices:options:` 方法扫描设备时，该方法的默认行为是将多个发现的通告外设合并到单个发现事件中-也就是说，中央管理器为发现的每个新外设调用其委托对象的 `centralManager:didDiscoverPeripheral:advertisementData:RSSI:` 方法，而不管它收到多少通告数据包。当已经发现的外围设备的通告数据发生变化时，中央管理器也会调用此委托方法。

If you want to change the default behavior, you can specify the `CBCentralManagerScanOptionAllowDuplicatesKey` constant as a scan option when calling the `scanForPeripheralsWithServices:options:` method. When you do, a discovery event is generated each time the central receives an advertising packet from the peripheral. Turning off the default behavior can be useful for certain use cases, such as initiating a connection to a peripheral based on the peripheral’s proximity (using the peripheral received signal strength indicator (RSSI) value). That said, keep in mind that specifying this scan option may have an adverse effect on battery life and app performance. Therefore, specify this scan option only when it is necessary to fulfill a particular use case.
如果您想更改默认行为，可以在调用 `scanForPeripheralsWithServices:options:` 方法时将 `CBCentralManagerScanOptionAllowDuplicatesKey` 常量指定为扫描选项。当您这样做时，每次中心设备从外围设备接收到通告数据包时都会生成一个发现事件。关闭默认行为对于某些用例可能很有用，例如基于外设的接近度（使用外设接收信号强度指示符（RSSI）值）发起与外设的连接。也就是说，请记住，指定此扫描选项可能会对电池寿命和应用程序性能产生不利影响。因此，仅当需要满足特定用例时才指定此扫描选项。



### Explore a Peripheral’s Data Wisely 明智地探索外设数据

A peripheral device may have many more services and characteristics than you may be interested in when you are developing an app to fulfill a specific use case. Discovering all of a peripheral’s services and associated characteristics can negatively affect battery life and your app’s performance. Therefore, you should look for and discover only the services and associated characteristics your app needs.
外围设备可能具有比您在开发应用以满足特定用例时可能感兴趣的更多的服务和特性。发现外设的所有服务和相关特性可能会对电池寿命和应用性能产生负面影响。因此，您应该只查找和发现应用所需的服务和相关特征。

For example, imagine that you are connected to a peripheral device that has many services available, but your app needs access to only two of them. You can look for and discover these two services only, by passing in an array of their service UUIDs (represented by `CBUUID` objects) to the `discoverServices:` method of the `CBPeripheral` class, like this:
例如，假设您连接到一个具有许多可用服务的外围设备，但您的应用只需要访问其中的两个服务。您可以只查找和发现这两个服务，方法是将它们的服务UUID数组（由 `CBUUID` 对象表示）传递给 `CBPeripheral` 类的 `discoverServices:` 方法，如下所示：

```
    [peripheral discoverServices:@[firstServiceUUID, secondServiceUUID]];
```

After you have discovered the two services you are interested in, you can similarly look for and discover only the characteristics of these services that you are interested in. Again, simply pass in an array of the UUIDs that identify the characteristics you want to discover (for each service) to the `discoverCharacteristics:forService:` method of the `CBPeripheral` class.
在您发现了您感兴趣的两个服务之后，您可以类似地只查找和发现您感兴趣的这些服务的特征。同样，只需将一个UUID数组传递给 `CBPeripheral` 类的 `discoverCharacteristics:forService:` 方法，这些UUID标识您希望发现的特征（对于每个服务）。



### Subscribe to Characteristic Values That Change Often 订阅经常变化的特征值

As described in [Retrieving the Value of a Characteristic](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW7), there are two ways you can retrieve a characteristic’s value:
如检索特征的值中所述，有两种方法可以检索特征的值：

- You can explicitly poll for a characteristic’s value by calling the `readValueForCharacteristic:` method each time you need the value.
  您可以通过在每次需要某个特性的值时调用 `readValueForCharacteristic:` 方法来显式地轮询该值。
- You can subscribe to the characteristic’s value by calling the `setNotifyValue:forCharacteristic:` method once to receive a notification from the peripheral when the value changes.
  您可以通过调用一次 `setNotifyValue:forCharacteristic:` 方法来订阅特性的值，以便在值更改时接收来自外围设备的通知。

It is best practice to subscribe to a characteristic’s value when possible, especially for characteristic values that change often. For an example of how to subscribe to a characteristic’s value, see [Subscribing to a Characteristic’s Value](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW16).
最佳实践是尽可能订阅特征值，特别是经常更改的特征值。有关如何订阅特征值的示例，请参阅订阅特征值。



### Disconnect from a Device When You Have All the Data You Need 当您拥有所需的所有数据时断开与设备的连接

You can help reduce your app’s radio usage by disconnecting from a peripheral device when a connection is no longer needed. You should disconnect from a peripheral device in both of the following situations:
当不再需要连接时，您可以通过断开与外围设备的连接来帮助减少应用的无线电使用。在以下两种情况下，都应断开与外围设备的连接：

- All characteristic values that you’ve subscribed to have stopped sending notifications. (You can determine whether a characteristic’s value is notifying by accessing the characteristic’s `isNotifying` property.)
  您订阅的所有特征值已停止发送通知。(You可以通过访问特征的 `isNotifying` 属性来确定特征的值是否正在通知。）
- You have all of the data you need from the peripheral device.
  您可以从外围设备获得所需的所有数据。

In both cases, cancel any subscriptions you may have and then disconnect from the peripheral. You can cancel any subscription to a characteristic’s value by calling the `setNotifyValue:forCharacteristic:` method, setting the first parameter to `NO`. You can cancel a connection to a peripheral device by calling the `cancelPeripheralConnection:` method of the `CBCentralManager` class, like this:
在这两种情况下，请取消您可能拥有的任何订阅，然后断开与外围设备的连接。您可以通过调用 `setNotifyValue:forCharacteristic:` 方法并将第一个参数设置为 `NO` 来取消对特征值的任何订阅。您可以通过调用 `CBCentralManager` 类的 `cancelPeripheralConnection:` 方法来取消与外围设备的连接，如下所示：

```
    [myCentralManager cancelPeripheralConnection:peripheral];
```



**Note:** The `cancelPeripheralConnection:` method is nonblocking, and any `CBPeripheral` class commands that are still pending to the peripheral you’re trying to disconnect may or may not finish executing. Because other apps may still have a connection to the peripheral, canceling a local connection does not guarantee that the underlying physical link is immediately disconnected. From your app’s perspective, however, the peripheral is considered disconnected, and the central manager object calls the `centralManager:didDisconnectPeripheral:error:` method of its delegate object.
注意： `cancelPeripheralConnection:` 方法是非阻塞的，并且对于您试图断开连接的外围设备，任何仍处于挂起状态的 `CBPeripheral` 类命令可能会也可能不会完成执行。由于其他应用可能仍与外围设备保持连接，因此取消本地连接并不能保证立即断开底层物理链路。但是，从应用的角度来看，外围设备被视为断开连接，中央管理器对象调用其委托对象的 `centralManager:didDisconnectPeripheral:error:` 方法。





## Reconnecting to Peripherals 重新连接到外围设备

Using the Core Bluetooth framework, there are three ways you can reconnect to a peripheral. You can:
使用Core Bluetooth框架，有三种方法可以重新连接到外设。您可以：

- Retrieve a list of known peripherals—peripherals that you’ve discovered or connected to in the past—using the `retrievePeripheralsWithIdentifiers:` method. If the peripheral you’re looking for is in the list, try to connect to it. This reconnection option is described in [Retrieving a List of Known Peripherals](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW10).
  使用 `retrievePeripheralsWithIdentifiers:` 方法搜索已知外围设备（您过去发现或连接到的外围设备）的列表。如果要查找的外围设备在列表中，请尝试连接到该外围设备。此重新连接选项在检索已知外围设备列表中进行了说明。
- Retrieve a list of peripheral devices that are currently connected to the system using the `retrieveConnectedPeripheralsWithServices:` method. If the peripheral you’re looking for is in the list, connect it locally to your app. This reconnection option is described in [Retrieving a List of Connected Peripherals](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW11).
  使用 `retrieveConnectedPeripheralsWithServices:` 方法检查当前连接到系统的外围设备列表。如果您要查找的外设在列表中，请将其本地连接到您的应用。有关此重新连接选项的说明，请参阅检索已连接外设列表。
- Scan for and discover a peripheral using the `scanForPeripheralsWithServices:options:` method. If you find it, connect to it. These steps are described in [Discovering Peripheral Devices That Are Advertising](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW3) and [Connecting to a Peripheral Device After You’ve Discovered It](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW4).
  使用 `scanForPeripheralsWithServices:options:` 方法扫描并发现外设。这些步骤在发现正在播发的外围设备和发现后连接到外围设备中进行了描述。

Depending on the use case, you may not want to have to scan for and discover the same peripheral every time you want to reconnect to it. Instead, you may want to try to reconnect using the other options first. As Figure 5-1 shows, one possible reconnection workflow may be to try each of these options in the order in which they’re listed above.
根据使用情况，您可能不希望每次要重新连接到同一外围设备时都必须扫描并发现该外围设备。相反，您可能希望先尝试使用其他选项重新连接。如图5-1所示，一个可能的重新连接工作流程可能是按照上面列出的顺序尝试每个选项。

**Figure 5-1** A sample reconnection workflow
图5-1重新连接工作流示例![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/ReconnectingToAPeripheral_2x.png)



**Note:** The number of reconnection options you decide to try, and the order in which you do so, may vary by the use case your app is trying to fulfill. For example, you may decide not to use the first connection option at all, or you may decide to try the first two options in parallel.
注意：您决定尝试的重新连接选项的数量以及执行该操作的顺序可能因您的应用尝试实现的用例而异。例如，您可能决定根本不使用第一个连接选项，或者您可能决定并行尝试前两个选项。





### Retrieving a List of Known Peripherals 检索已知外围设备列表

The first time you discover a peripheral, the system generates an identifier (a UUID, represented by an `NSUUID` object) to identify the peripheral. You can then store this identifier (using, for instance, the resources of the `NSUserDefaults` class), and later use it to try to reconnect to the peripheral using the `retrievePeripheralsWithIdentifiers:` method of the `CBCentralManager` class. The following describes one way to use this method to reconnect to a peripheral you’ve previously connected to.
第一次发现外设时，系统会生成一个标识符（UUID，由 `NSUUID` 对象表示）来标识外设。然后，您可以存储此标识符（例如，使用 `NSUserDefaults` 类的资源），稍后使用它来尝试使用 `CBCentralManager` 类的 `retrievePeripheralsWithIdentifiers:` 方法重新连接到外围设备。下面介绍了使用此方法重新连接到以前连接的外围设备的一种方法。

When your app launches, call the `retrievePeripheralsWithIdentifiers:` method, passing in an array containing the identifiers of the peripherals you’ve previously discovered and connected to (and whose identifiers you have saved), like this:
当您的应用启动时，调用 `retrievePeripheralsWithIdentifiers:` 方法，传入一个数组，其中包含您之前发现并连接到的外围设备的标识符（以及您已保存的标识符），如下所示：

| `    knownPeripherals =`                                     |
| ------------------------------------------------------------ |
| `        [myCentralManager retrievePeripheralsWithIdentifiers:savedIdentifiers];` |

The central manager tries to match the identifiers you provided to the identifiers of previously discovered peripherals and returns the results as an array of `CBPeripheral` objects. If no matches are found, the array is empty and you should try one of the other two reconnection options. If the array is not empty, let the user select (in the UI) which peripheral to try to reconnect to.
中央管理器尝试将您提供的标识符与以前发现的外围设备的标识符进行匹配，并将结果作为 `CBPeripheral` 对象数组返回。如果没有找到匹配项，则数组为空，您应该尝试其他两个重新连接选项之一。如果阵列不为空，则让用户选择（在UI中）要尝试重新连接的外围设备。

When the user selects a peripheral, try to connect to it by calling the `connectPeripheral:options:` method of the `CBCentralManager` class. If the peripheral device is still available to be connected to, the central manager calls the `centralManager:didConnectPeripheral:` method of its delegate object and the peripheral device is successfully reconnected.
当用户选择一个外设时，尝试通过调用 `CBCentralManager` 类的 `connectPeripheral:options:` 方法连接到它。如果外围设备仍然可以连接，则中央管理器调用其委托对象的 `centralManager:didConnectPeripheral:` 方法，并且外围设备被成功地重新连接。



**Note:** A peripheral device may not be available to be connected to for a few reasons. For instance, the device may not be in the vicinity of the central. In addition, some Bluetooth low energy devices use a random device address that changes periodically. Therefore, even if the device is nearby, the address of the device may have changed since the last time it was discovered by the system, in which case the `CBPeripheral` object you are trying to connect to doesn’t correspond to the actual peripheral device. If you cannot reconnect to the peripheral because its address has changed, you must rediscover it using the `scanForPeripheralsWithServices:options:` method.
注：由于多种原因，可能无法连接外围设备。例如，设备可能不在中心附近。此外，某些低功耗蓝牙设备使用定期更改的随机设备地址。因此，即使设备在附近，设备的地址也可能在系统上次发现后发生了更改，在这种情况下，您尝试连接的 `CBPeripheral` 对象与实际的外围设备不对应。如果您无法重新连接到外围设备，因为它的地址已更改，您必须使用 `scanForPeripheralsWithServices:options:` 方法重新发现它。

For more information about random device addresses, see the Bluetooth 4.0 specification, Volume 3, Part C, Section 10.8 and [Bluetooth Accessory Design Guidelines for Apple Products](https://developer.apple.com/hardwaredrivers/BluetoothDesignGuidelines.pdf).
有关随机设备地址的更多信息，请参阅蓝牙4.0规范第3卷C部分第10.8节和适用于Apple产品的蓝牙配件设计指南。





### Retrieving a List of Connected Peripherals 检索连接的外围设备列表

Another way to reconnect to a peripheral is by checking to see whether the peripheral you’re looking for is already connected to the system (for instance, by another app). You can do so by calling the `retrieveConnectedPeripheralsWithServices:` method of the `CBCentralManager` class, which returns an array of `CBPeripheral` objects representing peripheral devices that are currently connected to the system.
重新连接到外设的另一种方法是检查您要查找的外设是否已连接到系统（例如，通过另一个应用程序）。您可以通过调用 `CBCentralManager` 类的 `retrieveConnectedPeripheralsWithServices:` 方法来实现这一点，该方法返回一个表示当前连接到系统的外围设备的 `CBPeripheral` 对象数组。

Because there may be more than one peripheral currently connected to the system, you can pass in an array of `CBUUID` objects (these object represent service UUIDs) to retrieve only peripherals that are currently connected to the system *and* contain any services that are identified by the UUIDs you specified. If there are no peripheral devices currently connected to the system, the array is empty and you should try one of the other two reconnection options. If the array is not empty, let the user select (in the UI) which one to try to reconnect to.
由于当前可能有多个外围设备连接到系统，因此您可以传入一个 `CBUUID` 对象数组（这些对象表示服务UUID），以仅检索当前连接到系统的外围设备，并包含由您指定的UUID标识的任何服务。如果当前没有外围设备连接到系统，则阵列为空，您应该尝试其他两个重新连接选项之一。如果数组不为空，让用户选择（在UI中）尝试重新连接到哪个数组。

Assuming that the user finds and selects the desired peripheral, connect it locally to your app by calling the `connectPeripheral:options:` method of the `CBCentralManager` class. (Even though the device is already connected to the system, you must still connect it locally to your app to begin exploring and interacting with it.) When the local connection is established, the central manager calls the `centralManager:didConnectPeripheral:` method of its delegate object, and the peripheral device is successfully reconnected.
假设用户找到并选择了所需的外设，通过调用 `CBCentralManager` 类的 `connectPeripheral:options:` 方法将其本地连接到您的应用。(Even尽管设备已连接到系统，但您仍必须将其本地连接到应用，才能开始探索设备并与其进行交互。）当建立本地连接时，中央管理器调用其委托对象的 `centralManager:didConnectPeripheral:` 方法，外围设备成功重新连接。