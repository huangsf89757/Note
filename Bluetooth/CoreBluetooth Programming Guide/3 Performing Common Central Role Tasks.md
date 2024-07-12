# Performing Common Central Role Tasks 执行常见中心角色任务

Devices that implement the central role in Bluetooth low energy communication perform a number of common tasks—for example, discovering and connecting to available peripherals, and exploring and interacting with the data that peripherals have to offer. Devices that implement the peripheral role also perform a number of common, but different, tasks—for example, publishing and advertising services, and responding to read, write, and subscription requests from connected centrals.
在低功耗蓝牙通信中发挥核心作用的设备执行许多常见任务，例如，发现并连接到可用的外设，以及探索外设必须提供的数据并与之交互。实现外围设备角色的设备还执行许多常见但不同的任务，例如发布和广告服务，以及响应来自连接的中心设备的读、写和订阅请求。

In this chapter, you will learn how to use the Core Bluetooth framework to perform the most common types of Bluetooth low energy tasks from the central side. The code-based examples that follow will assist you in developing your app to implement the central role on your local device. Specifically, you will learn how to:
在本章中，您将学习如何使用Core Bluetooth框架从中央端执行最常见类型的低功耗蓝牙任务。以下基于代码的示例将帮助您开发应用程序，以便在本地设备上实现中心角色。具体来说，您将学习如何：

- Start up a central manager object
  启动中央管理器对象
- Discover and connect to peripheral devices that are advertising
  发现并连接到正在发布广告的外围设备
- Explore the data on a peripheral device after you’ve connected to it
  在连接到外围设备后浏览该设备上的数据
- Send read and write requests to a characteristic value of a peripheral’s service
  向外设服务的特征值发送读写请求
- Subscribe to a characteristic’s value to be notified when it is updated
  订阅更新时要通知的特征值

In the next chapter, you will learn how to develop your app to implement the peripheral role on your local device.
在下一章中，您将学习如何开发您的应用，以便在本地设备上实现外围设备角色。

The code examples that you find in this chapter are simple and abstract; you may need to make appropriate changes to incorporate them into your real world app. More advanced topics related to implementing the central role—including tips, tricks, and best practices—are covered in the later chapters, [Core Bluetooth Background Processing for iOS Apps](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW1) and [Best Practices for Interacting with a Remote Peripheral Device](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW1).
本章中的代码示例既简单又抽象;您可能需要进行适当的更改，才能将它们整合到您的真实的应用中。与实现中心角色相关的更高级主题（包括提示、技巧和最佳实践）将在后续章节“iOS应用的核心蓝牙后台处理”和“与远程外围设备交互的最佳实践”中介绍。



## Starting Up a Central Manager 启动中央管理器

Because a `CBCentralManager` object is the Core Bluetooth object-oriented representation of a local central device, you allocate and initialize a central manager instance before you can perform any Bluetooth low energy transactions. You initialize your central manager by calling its `initWithDelegate:queue:options:` method:
由于 `CBCentralManager` 对象是本地中央设备的Core Bluetooth面向对象表示，因此在执行任何低功耗蓝牙事务之前，您需要分配并初始化中央管理器实例。您可以通过调用其 `initWithDelegate:queue:options:` 方法来初始化中央管理器：

| `    myCentralManager =`                                     |
| ------------------------------------------------------------ |
| `        [[CBCentralManager alloc] initWithDelegate:self queue:nil options:nil];` |

In this example, `self` is set as the delegate to receive any central role events. By specifying the dispatch queue as `nil`, the central manager dispatches central role events using the main queue.
在此示例中， `self` 被设置为接收任何中心角色事件的委托。通过将分派队列指定为 `nil` ，中央管理器使用主队列分派中央角色事件。

When you create a central manager, the central manager calls the `centralManagerDidUpdateState:` method of its delegate object. You must implement this delegate method to ensure that Bluetooth low energy is supported and available to use on the central device. For more information about how to implement this delegate method, see *[CBCentralManagerDelegate Protocol Reference](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate)*.
创建中央管理器时，中央管理器调用其委托对象的 `centralManagerDidUpdateState:` 方法。您必须实现此委托方法以确保支持低功耗蓝牙并可在中央设备上使用。有关如何实现此委托方法的更多信息，请参见CBCentralManagerDelegate Protocol Reference。



## Discovering Peripheral Devices That Are Advertising 发现正在做广告的外围设备

Once initialized, the central manager’s first task is peripheral discovery. As mentioned in [Centrals Discover and Connect to Peripherals That Are Advertising](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothOverview/CoreBluetoothOverview.html#//apple_ref/doc/uid/TP40013257-CH2-SW3), peripherals make their presence known by advertising. Your app discovers nearby peripheral devices that are advertising by calling the central manager’s `scanForPeripheralsWithServices:options:` method:
一旦初始化，中央管理器的第一个任务就是发现外围设备。如中心设备发现并连接到正在做广告的外围设备中所述，外围设备通过广告来显示其存在。您的应用通过调用中央管理器的 `scanForPeripheralsWithServices:options:` 方法来发现附近正在进行广告的外围设备：

```
    [myCentralManager scanForPeripheralsWithServices:nil options:nil];
```



**Note:** If you specify `nil` for the first parameter, the central manager returns *all* discovered peripherals, regardless of their supported services. In a real app, you typically specify an array of `CBUUID` objects, each of which represents the universally unique identifier (UUID) of a service that a peripheral is advertising. When you specify an array of service UUIDs, the central manager returns only peripherals that advertise those services, allowing you to scan only for devices that you may be interested in.
注：如果为第一个参数指定 `nil` ，则中央管理器将返回所有发现的外围设备，而不考虑其支持的服务。在一个真实的应用程序中，您通常会指定一个由 `CBUUID` 对象组成的数组，其中每个对象都表示外围设备正在通告的服务的通用唯一标识符（UUID）。当您指定服务UUID数组时，中央管理器仅返回通告这些服务的外围设备，从而允许您仅扫描可能感兴趣的设备。

UUIDs, and the `CBUUID` objects that represent them, are discussed in more detail in [Services and Characteristics Are Identified by UUIDs](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW8).
UUID和表示它们的 `CBUUID` 对象在由UUID标识的服务和特征中有更详细的讨论。



Every time the central manager discovers a peripheral, it calls the `centralManager:didDiscoverPeripheral:advertisementData:RSSI:` method of its delegate object. The newly discovered peripheral is returned as a `CBPeripheral` object. If you plan to connect to the discovered peripheral, keep a strong reference to it so the system does not deallocate it. The following example shows a scenario where you use a class property to maintain a reference to the discovered peripheral:
每次中央管理器发现外围设备时，它都会调用其委托对象的 `centralManager:didDiscoverPeripheral:advertisementData:RSSI:` 方法。新发现的外围设备作为 `CBPeripheral` 对象返回。如果计划连接到发现的外围设备，请保留对它的强引用，以便系统不会释放它。以下示例显示了一个使用类属性维护对发现的外围设备的引用的方案：

| `- (void)centralManager:(CBCentralManager *)central`       |
| ---------------------------------------------------------- |
| ` didDiscoverPeripheral:(CBPeripheral *)peripheral`        |
| `     advertisementData:(NSDictionary *)advertisementData` |
| `                  RSSI:(NSNumber *)RSSI {`                |
| ` `                                                        |
| `    NSLog(@"Discovered %@", peripheral.name);`            |
| `    self.discoveredPeripheral = peripheral;`              |
| `    ...`                                                  |

If you expect to connect to multiple devices, you might instead keep an `NSArray` of discovered peripherals. In any case, once you’ve found all the peripheral devices that you’re interested in connecting to, stop scanning for other devices in order to save power:
如果您希望连接到多个设备，则可以保留 `NSArray` 个已发现的外围设备。在任何情况下，一旦找到了所有您感兴趣的连接到的外围设备，停止扫描其他设备，以节省电力：

```
    [myCentralManager stopScan];
```



## Connecting to a Peripheral Device After You’ve Discovered It 发现外围设备后连接到它

After you discover a peripheral device advertising services you are interested in, you request a connection to the peripheral by calling the central manager’s `connectPeripheral:options:` method, naming the discovered peripheral that you want to connect to:
在发现一个外围设备广告服务后，您可以通过调用中央管理器的 `connectPeripheral:options:` 方法请求连接到该外围设备，并命名要连接到的已发现外围设备：

```
    [myCentralManager connectPeripheral:peripheral options:nil];
```

If the connection request is successful, the central manager calls the `centralManager:didConnectPeripheral:` method of its delegate object. Before you start interacting with the peripheral, you set its delegate to ensure that the delegate receives the appropriate callbacks:
如果连接请求成功，则中央管理器调用其委托对象的 `centralManager:didConnectPeripheral:` 方法。在开始与外围设备交互之前，设置其委托以确保委托接收适当的回调：

| `- (void)centralManager:(CBCentralManager *)central`  |
| ----------------------------------------------------- |
| `  didConnectPeripheral:(CBPeripheral *)peripheral {` |
| ` `                                                   |
| `    NSLog(@"Peripheral connected");`                 |
| `    peripheral.delegate = self;`                     |
| `    ...`                                             |



## Discovering the Services of a Peripheral That You’re Connected To 发现您所连接的外围设备的服务

After you have established a connection to a peripheral, you can explore its data. The first step in exploring what a peripheral has to offer is discovering its available services. Because there are size restrictions on the amount of data a peripheral can advertise, you may discover that a peripheral has more services than what it advertises (in its advertising packets). You can discover all of the services that a peripheral offers by calling the peripheral’s `discoverServices:` method, like this:
建立到外围设备的连接后，可以浏览其数据。探索外设所提供的功能的第一步是发现其可用的服务。由于外围设备可以通告的数据量有大小限制，因此您可能会发现外围设备的服务比它所通告的（在其通告数据包中）更多。您可以通过调用外设的 `discoverServices:` 方法来发现外设提供的所有服务，如下所示：

```
    [peripheral discoverServices:nil];
```



**Note:** In a real app, you typically do not pass in `nil` as the parameter, because doing so returns *all* the services available on a peripheral device. Because a peripheral may contain many more services than you are interested in, discovering all of them may waste battery life and be an unnecessary use of time. Instead, you typically specify the UUIDs of the services that you already know you are interested in discovering, as shown in [Explore a Peripheral’s Data Wisely](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW6).
注意：在真实的应用中，您通常不会传入 `nil` 作为参数，因为这样做会返回外围设备上可用的所有服务。由于外围设备可能包含比您感兴趣的更多的服务，因此发现所有这些服务可能会浪费电池寿命，并且是不必要的时间使用。相反，您通常指定您已经知道您有兴趣发现的服务的UUID，如明智地探索外围设备的数据中所示。



When the specified services are discovered, the peripheral (the `CBPeripheral` object you’re connected to) calls the `peripheral:didDiscoverServices:` method of its delegate object. Core Bluetooth creates an array of `CBService` objects—one for each service that is discovered on the peripheral. As the following shows, you can implement this delegate method to access the array of discovered services:
当发现指定的服务时，外围设备（您连接到的 `CBPeripheral` 对象）调用其委托对象的 `peripheral:didDiscoverServices:` 方法。核心蓝牙创建了一个由 `CBService` 个对象组成的数组-每个对象对应于在外围设备上发现的每个服务。如下所示，您可以实现此委托方法来访问已发现服务的数组：

| `- (void)peripheral:(CBPeripheral *)peripheral`         |
| ------------------------------------------------------- |
| `didDiscoverServices:(NSError *)error {`                |
| ` `                                                     |
| `    for (CBService *service in peripheral.services) {` |
| `        NSLog(@"Discovered service %@", service);`     |
| `        ...`                                           |
| `    }`                                                 |
| `    ...`                                               |



## Discovering the Characteristics of a Service 发现服务的特征

When you find a service that you are interested in, the next step in exploring what a peripheral has to offer is discovering all of the service’s characteristics. Discovering all of the characteristics of a service is as simple as calling the peripheral’s `discoverCharacteristics:forService:` method, specifying the appropriate service, like this:
当您找到感兴趣的服务时，探索外围设备所能提供的服务的下一步是发现服务的所有特征。发现服务的所有特征就像调用外围设备的 `discoverCharacteristics:forService:` 方法一样简单，指定适当的服务，如下所示：

| `    NSLog(@"Discovering characteristics for service %@", interestingService);` |
| ------------------------------------------------------------ |
| `    [peripheral discoverCharacteristics:nil forService:interestingService];` |



**Note:** In a real app, you typically do not pass in `nil` as the first parameter, because doing so returns *all* the characteristics of a peripheral’s service. Because a peripheral’s service may contain many more characteristics than you are interested in, discovering all of them may waste battery life and be an unnecessary use of time. Instead, you typically specify the UUIDs of the characteristics that you already know you are interested in discovering.
注意：在一个真实的应用中，您通常不会将 `nil` 作为第一个参数传入，因为这样做会返回外设服务的所有特征。由于外设服务可能包含比您感兴趣的更多的特性，因此发现所有这些特性可能会浪费电池寿命，并且是不必要的时间使用。相反，您通常指定您已经知道您有兴趣发现的特征的UUID。



The peripheral calls the `peripheral:didDiscoverCharacteristicsForService:error:` method of its delegate object when the characteristics of the specified service are discovered. Core Bluetooth creates an array of `CBCharacteristic` objects—one for each characteristic that is discovered. The following example shows how you can implement this delegate method to simply log every characteristic that is discovered:
当发现指定服务的特征时，外围设备调用其委托对象的 `peripheral:didDiscoverCharacteristicsForService:error:` 方法。核心蓝牙创建了一个由 `CBCharacteristic` 个对象组成的数组，每个对象对应一个被发现的特征。下面的示例显示了如何实现此委托方法以简单地记录发现的每个特征：

| `- (void)peripheral:(CBPeripheral *)peripheral`              |
| ------------------------------------------------------------ |
| `didDiscoverCharacteristicsForService:(CBService *)service`  |
| `             error:(NSError *)error {`                      |
| ` `                                                          |
| `    for (CBCharacteristic *characteristic in service.characteristics) {` |
| `        NSLog(@"Discovered characteristic %@", characteristic);` |
| `        ...`                                                |
| `    }`                                                      |
| `    ...`                                                    |



## Retrieving the Value of a Characteristic 检索特征的值

A characteristic contains a single value that represents information about a peripheral’s service. For example, a temperature measurement characteristic of a health thermometer service may have a value that indicates a temperature in Celsius. You can retrieve the value of a characteristic by reading it directly or by subscribing to it.
特征包含一个表示外围设备服务信息的值。例如，健康温度计服务的温度测量特性可以具有指示以摄氏度为单位的温度的值。您可以通过直接阅读或订阅来检索特征的值。



### Reading the Value of a Characteristic 阅读特征的值

After you have found a characteristic of a service that you are interested in, you can read the characteristic’s value by calling the peripheral’s `readValueForCharacteristic:` method, specifying the appropriate characteristic, like this:
找到感兴趣的服务特性后，可以通过调用外围设备的 `readValueForCharacteristic:` 方法来读取特性的值，指定适当的特性，如下所示：

| `    NSLog(@"Reading value for characteristic %@", interestingCharacteristic);` |
| ------------------------------------------------------------ |
| `    [peripheral readValueForCharacteristic:interestingCharacteristic];` |

When you attempt to read the value of a characteristic, the peripheral calls the `peripheral:didUpdateValueForCharacteristic:error:` method of its delegate object to retrieve the value. If the value is successfully retrieved, you can access it through the characteristic’s value property, like this:
当您尝试读取特性的值时，外围设备调用其委托对象的 `peripheral:didUpdateValueForCharacteristic:error:` 方法来检索该值。如果成功检索到值，则可以通过特征的value属性访问它，如下所示：

| `- (void)peripheral:(CBPeripheral *)peripheral`              |
| ------------------------------------------------------------ |
| `didUpdateValueForCharacteristic:(CBCharacteristic *)characteristic` |
| `             error:(NSError *)error {`                      |
| ` `                                                          |
| `    NSData *data = characteristic.value;`                   |
| `    // parse the data as needed`                            |
| `    ...`                                                    |



**Note:** Not all characteristics are readable. You can determine whether a characteristic is readable by checking if its `properties` attribute includes the `CBCharacteristicPropertyRead` constant. If you try to read a value of a characteristic that is not readable, the `peripheral:didUpdateValueForCharacteristic:error:` delegate method returns a suitable error.
注：并非所有特征都可读。您可以通过检查特性的 `properties` 属性是否包含 `CBCharacteristicPropertyRead` 常量来确定其是否可读。如果你试图读取一个不可读的特征值， `peripheral:didUpdateValueForCharacteristic:error:` delegate方法会返回一个合适的错误。





### Subscribing to a Characteristic’s Value 订阅特性的值

Though reading the value of a characteristic using the `readValueForCharacteristic:` method can be effective for static values, it is not the most efficient way to retrieve a dynamic value. Retrieve characteristic values that change over time—for instance, your heart rate—by subscribing to them. When you subscribe to a characteristic’s value, you receive a notification from the peripheral when the value changes.
虽然使用 `readValueForCharacteristic:` 方法阅读特性的值对静态值有效，但它不是检索动态值的最有效方法。通过订阅这些特征值，您可以获得随时间变化的特征值，例如您的心率。当您订阅特性的值时，当值更改时，您会收到来自外围设备的通知。

You subscribe to the value of a characteristic that you are interested in by calling the peripheral’s `setNotifyValue:forCharacteristic:` method, specifying the first parameter as `YES`, like this:
您可以通过调用外围设备的 `setNotifyValue:forCharacteristic:` 方法来订阅您感兴趣的特性的值，并将第一个参数指定为 `YES` ，如下所示：

```
    [peripheral setNotifyValue:YES forCharacteristic:interestingCharacteristic];
```

When you subscribe to (or unsubscribe from) a characteristic’s value, the peripheral calls the `peripheral:didUpdateNotificationStateForCharacteristic:error:` method of its delegate object. If the subscription request fails for any reason, you can implement this delegate method to access the cause of the error, as the following example shows:
当您订阅（或取消订阅）一个特性的值时，外围设备会调用其委托对象的 `peripheral:didUpdateNotificationStateForCharacteristic:error:` 方法。如果订阅请求由于任何原因失败，则可以实现此委托方法以访问错误的原因，如下面的示例所示：

| `- (void)peripheral:(CBPeripheral *)peripheral`              |
| ------------------------------------------------------------ |
| `didUpdateNotificationStateForCharacteristic:(CBCharacteristic *)characteristic` |
| `             error:(NSError *)error {`                      |
| ` `                                                          |
| `    if (error) {`                                           |
| `        NSLog(@"Error changing notification state: %@",`    |
| `           [error localizedDescription]);`                  |
| `    }`                                                      |
| `    ...`                                                    |



**Note:** Not all characteristics offer subscription. You can determine if a characteristic offers subscription by checking if its `properties` attribute includes either of the `CBCharacteristicPropertyNotify` or `CBCharacteristicPropertyIndicate` constants.
注：并非所有特征都提供订阅。您可以通过检查特性的 `properties` 属性是否包含 `CBCharacteristicPropertyNotify` 或 `CBCharacteristicPropertyIndicate` 常量来确定其是否提供订阅。



After you have successfully subscribed to a characteristic’s value, the peripheral device notifies your app when the value has changed. Each time the value changes, the peripheral calls the `peripheral:didUpdateValueForCharacteristic:error:` method of its delegate object. To retrieve the updated value, you can implement this method in the same way as described above in [Reading the Value of a Characteristic](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW12).
成功订阅特征值后，外围设备会在值发生更改时通知您的应用。每次该值更改时，外围设备都会调用其委托对象的 `peripheral:didUpdateValueForCharacteristic:error:` 方法。要检索更新的值，可以按照与上面阅读特征值中所述相同的方式实现此方法。



## Writing the Value of a Characteristic 写一个特征的价值

Sometimes it makes sense to write the value of a characteristic. For example, if your app interacts with a Bluetooth low energy digital thermostat, you may want to provide the thermostat with a value at which to set the room’s temperature. If a characteristic’s value is writeable, you can write its value with data (an instance of `NSData`) by calling the peripheral’s `writeValue:forCharacteristic:type:` method, like this:
有时写一个特征的值是有意义的。例如，如果您的应用与蓝牙低功耗数字恒温器交互，您可能希望为恒温器提供一个用于设置房间温度的值。如果一个特征的值是可写的，你可以通过调用外围设备的 `writeValue:forCharacteristic:type:` 方法来用数据（ `NSData` 的实例）写它的值，如下所示：

| `    NSLog(@"Writing value for characteristic %@", interestingCharacteristic);` |
| ------------------------------------------------------------ |
| `    [peripheral writeValue:dataToWrite forCharacteristic:interestingCharacteristic` |
| `        type:CBCharacteristicWriteWithResponse];`           |

When you write the value of a characteristic, you specify what type of write you want to perform. In the example above, the write type is `CBCharacteristicWriteWithResponse`, which instructs the peripheral to let your app know whether or not the write succeeds by calling the `peripheral:didWriteValueForCharacteristic:error:` method of its delegate object. You implement this delegate method to handle the error condition, as the following example shows:
当你写一个特征的值时，你指定你想要执行的写类型。在上面的示例中，写入类型为 `CBCharacteristicWriteWithResponse` ，它指示外围设备通过调用其委托对象的 `peripheral:didWriteValueForCharacteristic:error:` 方法来让您的应用知道写入是否成功。实现此委托方法以处理错误条件，如下例所示：

| `- (void)peripheral:(CBPeripheral *)peripheral`              |
| ------------------------------------------------------------ |
| `didWriteValueForCharacteristic:(CBCharacteristic *)characteristic` |
| `             error:(NSError *)error {`                      |
| ` `                                                          |
| `    if (error) {`                                           |
| `        NSLog(@"Error writing characteristic value: %@",`   |
| `            [error localizedDescription]);`                 |
| `    }`                                                      |
| `    ...`                                                    |

If instead you specify the write type as `CBCharacteristicWriteWithoutResponse`, the write operation is performed as best-effort, and delivery is neither guaranteed nor reported. The peripheral does not call any delegate method. For more information about the write types that are supported in the Core Bluetooth framework, see the `CBCharacteristicWriteType` enumeration in *[CBPeripheral Class Reference](https://developer.apple.com/documentation/corebluetooth/cbperipheral)*.
相反，如果您将写入类型指定为 `CBCharacteristicWriteWithoutResponse` ，则写入操作将以最佳方式执行，并且既不保证也不报告传输。外围设备不调用任何委托方法。有关Core Bluetooth框架中支持的写入类型的详细信息，请参阅CBPeripheral Class Reference中的 `CBCharacteristicWriteType` 枚举。



**Note:** Characteristics may support only certain types of writes, or none at all. You determine what type of writes, if any, a characteristic supports by checking its `properties` attribute for one of the `CBCharacteristicPropertyWriteWithoutResponse` or `CBCharacteristicPropertyWrite` constants.
注意：特性可能只支持某些类型的写入，或者根本不支持。通过检查特性的 `properties` 属性中的 `CBCharacteristicPropertyWriteWithoutResponse` 或 `CBCharacteristicPropertyWrite` 常量之一来确定特性支持的写入类型（如果有的话）。