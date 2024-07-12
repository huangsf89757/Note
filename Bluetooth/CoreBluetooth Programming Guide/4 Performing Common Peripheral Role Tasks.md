# Performing Common Peripheral Role Tasks 执行常见外围设备角色任务

In the last chapter, you learned how to perform the most common types of Bluetooth low energy tasks from the central side. In this chapter, you learn how to use the Core Bluetooth framework to perform the most common types of Bluetooth low energy tasks from the peripheral side. The code-based examples that follow will assist you in developing your app to implement the peripheral role on your local device. Specifically, you will learn how to:
在上一章中，您学习了如何从中央端执行最常见类型的蓝牙低功耗任务。在本章中，您将学习如何使用Core Bluetooth框架从外设端执行最常见类型的低功耗蓝牙任务。以下基于代码的示例将帮助您开发应用，以便在本地设备上实现外围设备角色。具体来说，您将学习如何：

- Start up a peripheral manager object
  启动外设管理器对象
- Set up services and characteristics on your local peripheral
  在本地外围设备上设置服务和特性
- Publish your services and characteristics to your device’s local database
  将您的服务和特征发布到设备的本地数据库
- Advertise your services 推广您的服务
- Respond to read and write requests from a connected central
  响应来自连接的中心的读写请求
- Send updated characteristic values to subscribed centrals
  将更新的特征值发送到订阅的中心

The code examples that you find in this chapter are simple and abstract; you may need to make appropriate changes to incorporate them into your real-world app. More advanced topics related to implementing the peripheral role on your local device—including tips, tricks, and best practices—are covered in the later chapters, [Core Bluetooth Background Processing for iOS Apps](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW1) and [Best Practices for Setting Up Your Local Device as a Peripheral](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral.html#//apple_ref/doc/uid/TP40013257-CH5-SW1).
本章中的代码示例既简单又抽象;您可能需要进行适当的更改，才能将其整合到实际应用中。与在本地设备上实现外设角色相关的更高级主题（包括提示、技巧和最佳实践）将在后面的章节《iOS应用的核心蓝牙后台处理》和《将本地设备设置为外设的最佳实践》中介绍。



## Starting Up a Peripheral Manager 启动外设管理器

The first step in implementing the peripheral role on your local device is to allocate and initialize a peripheral manager instance (represented by a `CBPeripheralManager` object). Start up your peripheral manager by calling the `initWithDelegate:queue:options:` method of the `CBPeripheralManager` class, like this:
在本地设备上实现外设角色的第一步是分配和初始化外设管理器实例（由 `CBPeripheralManager` 对象表示）。通过调用 `CBPeripheralManager` 类的 `initWithDelegate:queue:options:` 方法启动外设管理器，如下所示：

| `    myPeripheralManager =`                                  |
| ------------------------------------------------------------ |
| `        [[CBPeripheralManager alloc] initWithDelegate:self queue:nil options:nil];` |

In this example, `self` is set as the delegate to receive any peripheral role events. When you specify the dispatch queue as `nil`, the peripheral manager dispatches peripheral role events using the main queue.
在此示例中， `self` 被设置为接收任何外围角色事件的委托。当您将分派队列指定为 `nil` 时，外围设备管理器将使用主队列分派外围设备角色事件。

When you create a peripheral manager, the peripheral manager calls the `peripheralManagerDidUpdateState:` method of its delegate object. You must implement this delegate method to ensure that Bluetooth low energy is supported and available to use on the local peripheral device. For more information about how to implement this delegate method, see *[CBPeripheralManagerDelegate Protocol Reference](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate)*.
创建外围设备管理器时，外围设备管理器调用其委托对象的 `peripheralManagerDidUpdateState:` 方法。您必须实现此委托方法，以确保支持低功耗蓝牙并可在本地外围设备上使用。有关如何实现此委托方法的更多信息，请参见CBPeripheralManagerDelegate协议参考。



## Setting Up Your Services and Characteristics 设置您的服务和特性

As shown in [Figure 1-7](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothOverview/CoreBluetoothOverview.html#//apple_ref/doc/uid/TP40013257-CH2-SW18), a local peripheral’s database of services and characteristics is organized in a tree-like manner. You must organize them in this tree-like manner to set up your services and characteristics on your local peripheral. Your first step in carrying out these tasks is understanding how services and characteristics are identified.
如图1-7所示，本地外设的服务和特性数据库是以树状方式组织的。您必须以这种树状方式组织它们，以便在本地外围设备上设置服务和特性。执行这些任务的第一步是了解如何识别服务和特征。



### Services and Characteristics Are Identified by UUIDs 服务和特征由UUID标识

The services and characteristics of a peripheral are identified by 128-bit Bluetooth-specific UUIDs, which are represented in the Core Bluetooth framework by `CBUUID` objects. Though not all UUIDs that identify a service or characteristic are predefined by the Bluetooth Special Interest Group (SIG), Bluetooth SIG has defined and published a number of commonly used UUIDs that have been shortened to 16-bits for convenience. For example, Bluetooth SIG has predefined the 16-bit UUID that identifies a heart rate service as 180D. This UUID is shortened from its equivalent 128-bit UUID, 0000180D-0000-1000-8000-00805F9B34FB, which is based on the Bluetooth base UUID that is defined in the Bluetooth 4.0 specification, Volume 3, Part F, Section 3.2.1.
外设的服务和特性由128位蓝牙特定的UUID标识，在核心蓝牙框架中由 `CBUUID` 对象表示。虽然并非所有标识服务或特性的UUID都是由蓝牙特别兴趣组（SIG）预定义的，但蓝牙SIG已经定义并发布了许多常用的UUID，为了方便起见，这些UUID已缩短为16位。例如，蓝牙SIG已经预定义了16位UUID，将心率服务标识为180 D。此UUID是从其等效的128位UUID 0000180 D-0000-1000-8000- 00805 F9 B34 FB缩短而来的，后者基于蓝牙4.0规范第3卷F部分第3.2.1节中定义的蓝牙基础UUID。

The `CBUUID` class provides factory methods that make it much easier to deal with long UUIDs when developing your app. For example, instead of passing around the string representation of the heart rate service’s 128-bit UUID in your code, you can simply use the `UUIDWithString` method to create a `CBUUID` object from the service’s predefined 16-bit UUID, like this:
`CBUUID` 类提供了工厂方法，使开发应用时更容易处理长UUID。例如，您可以简单地使用 `UUIDWithString` 方法从服务的预定义16位UUID创建 `CBUUID` 对象，而不是在代码中传递心率服务的128位UUID的字符串表示，如下所示：

```
    CBUUID *heartRateServiceUUID = [CBUUID UUIDWithString: @"180D"];
```

When you create a `CBUUID` object from a predefined 16-bit UUID, Core Bluetooth pre-fills the rest of 128-bit UUID with the Bluetooth base UUID.
当您从预定义的16位UUID创建 `CBUUID` 对象时，Core Bluetooth会使用Bluetooth Base UUID预填充128位UUID的其余部分。



### Create Your Own UUIDs for Custom Services and Characteristics 为自定义服务和特性创建自己的UUID

You may have services and characteristics that are not identified by predefined Bluetooth UUIDs. If you do, you need to generate your own 128-bit UUIDs to identify them.
您可能拥有预定义的蓝牙UUID无法识别的服务和特性。如果这样做，您需要生成自己的128位UUID来标识它们。

Use the command-line utility `uuidgen` to easily generate 128-bit UUIDs. To get started, open a window in Terminal. Next, for each service and characteristic that you need to identify with a UUID, type `uuidgen` on the command line to receive a unique 128-bit value in the form of an ASCII string that is punctuated by hyphens, as in the following example:
使用命令行工具 `uuidgen` 轻松生成128位UUID。要开始使用，请在终端中打开一个窗口。接下来，对于需要使用UUID标识的每个服务和特征，在命令行上键入 `uuidgen` 以接收以ASCII字符串形式的唯一128位值，该字符串由连字符标点，如以下示例所示：

| `$ uuidgen`                            |
| -------------------------------------- |
| `71DA3FD1-7E10-41C1-B16F-4430B506CDE7` |

You can then use this UUID to create a `CBUUID` object using the `UUIDWithString` method, like this:
然后，您可以使用此UUID使用 `UUIDWithString` 方法创建 `CBUUID` 对象，如下所示：

| `    CBUUID *myCustomServiceUUID =`                          |
| ------------------------------------------------------------ |
| `        [CBUUID UUIDWithString:@"71DA3FD1-7E10-41C1-B16F-4430B506CDE7"];` |



### Build Your Tree of Services and Characteristics 构建您的服务和特征树

After you have the UUIDs of your services and characteristics (represented by `CBUUID` objects), you can create mutable services and characteristics and organize them in the tree-like manner described above. For example, if you have the UUID of a characteristic, you can create a mutable characteristic by calling the `initWithType:properties:value:permissions:` method of the `CBMutableCharacteristic` class, like this:
在获得服务和特征的UUID（由 `CBUUID` 对象表示）之后，您可以创建可变的服务和特征，并以上述类似树的方式组织它们。例如，如果你有一个特征的UUID，你可以通过调用 `CBMutableCharacteristic` 类的 `initWithType:properties:value:permissions:` 方法来创建一个可变特征，如下所示：

| `    myCharacteristic =`                                     |
| ------------------------------------------------------------ |
| `        [[CBMutableCharacteristic alloc] initWithType:myCharacteristicUUID` |
| `         properties:CBCharacteristicPropertyRead`           |
| `         value:myValue permissions:CBAttributePermissionsReadable];` |

When you create a mutable characteristic, you set its properties, value, and permissions. The properties and permissions you set determine, among other things, whether the value of the characteristic is readable or writeable, and whether a connected central can subscribe to the characteristic’s value. In this example, the value of the characteristic is set to be readable by a connected central. For more information about the range of supported properties and permissions of mutable characteristics, see *[CBMutableCharacteristic Class Reference](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic)*.
当您创建一个可变特性时，您需要设置它的属性、值和权限。您设置的属性和权限决定了特征的值是可读还是可写，以及连接的中心是否可以订阅特征的值。在该示例中，特征的值被设置为可由连接的中心读取。有关可变特征的受支持属性和权限范围的更多信息，请参见CBMutableCharacteristic类参考。



**Note:** If you specify a value for the characteristic, the value is cached and its properties and permissions are set to be readable. Therefore, if you need the value of a characteristic to be writeable, or if you expect the value to change during the lifetime of the published service to which the characteristic belongs, you must specify the value to be `nil`. Following this approach ensures that the value is treated dynamically and requested by the peripheral manager whenever the peripheral manager receives a read or write request from a connected central.
注意：如果您为特性指定了值，则会缓存该值，并将其属性和权限设置为可读。因此，如果您需要特性的值是可写的，或者如果您希望该值在特性所属的已发布服务的生存期内发生更改，则必须将该值指定为 `nil` 。遵循这种方法可确保动态处理该值，并在外围设备管理器从连接的中心设备接收到读或写请求时由外围设备管理器请求该值。



Now that you have created a mutable characteristic, you can create a mutable service to associate the characteristic with. To do so, call the `initWithType:primary:` method of the `CBMutableService` class, as shown here:
既然您已经创建了一个可变特征，那么您就可以创建一个可变服务来关联该特征。为此，请调用 `CBMutableService` 类的 `initWithType:primary:` 方法，如下所示：

```
    myService = [[CBMutableService alloc] initWithType:myServiceUUID primary:YES];
```

In this example, the second parameter is set to `YES`, indicating that the service is primary as opposed to secondary. A *primary service* describes the primary functionality of a device and can be included (referenced) by another service. A *secondary service* describes a service that is relevant only in the context of another service that has referenced it. For example, the primary service of a heart rate monitor may be to expose heart rate data from the monitor’s heart rate sensor, whereas a secondary service may be to expose the sensor’s battery data.
在此示例中，第二参数被设置为 `YES` ，指示服务是主要的而不是次要的。主要服务描述了设备的主要功能，并且可以被另一个服务包括（引用）。次要服务描述仅在引用它的另一服务的上下文中相关的服务。例如，心率监测器的主要服务可以是暴露来自监测器的心率传感器的心率数据，而次要服务可以是暴露传感器的电池数据。

After you create a service, you can associate the characteristic with it by setting the service’s array of characteristics, like this:
创建服务后，可以通过设置服务的特征数组将特征与服务关联起来，如下所示：

```
    myService.characteristics = @[myCharacteristic];
```



## Publishing Your Services and Characteristics 发布您的服务和特征

After you have built your tree of services and characteristics, the next step in implementing the peripheral role on your local device is publishing them to the device’s database of services and characteristics. This task is easy to perform using the Core Bluetooth framework. You call the `addService:` method of the `CBPeripheralManager` class, like this:
构建服务和特征树后，在本地设备上实现外围设备角色的下一步是将它们发布到设备的服务和特征数据库。使用Core Bluetooth框架可以轻松执行此任务。调用 `CBPeripheralManager` 类的 `addService:` 方法，如下所示：

```
    [myPeripheralManager addService:myService];
```

When you call this method to publish your services, the peripheral manager calls the `peripheralManager:didAddService:error:` method of its delegate object. If an error occurs and your services can’t be published, implement this delegate method to access the cause of the error, as the following example shows:
当您调用此方法来发布服务时，外围设备管理器将调用其委托对象的 `peripheralManager:didAddService:error:` 方法。如果发生错误并且无法发布服务，请实现此委托方法以访问错误的原因，如以下示例所示：

| `- (void)peripheralManager:(CBPeripheralManager *)peripheral` |
| ------------------------------------------------------------ |
| `            didAddService:(CBService *)service`             |
| `                    error:(NSError *)error {`               |
| ` `                                                          |
| `    if (error) {`                                           |
| `        NSLog(@"Error publishing service: %@", [error localizedDescription]);` |
| `    }`                                                      |
| `    ...`                                                    |



**Note:** After you publish a service and any of its associated characteristics to the peripheral’s database, the service is cached and you can no longer make changes to it.
注意：将服务及其任何关联特征发布到外围设备的数据库后，服务将被缓存，您不能再对其进行更改。





## Advertising Your Services 为您的服务做广告

When you have published your services and characteristics to your device’s database of services and characteristics, you are ready to start advertising some of them to any centrals that may be listening. As the following example shows, you can advertise some of your services by calling the `startAdvertising:` method of the `CBPeripheralManager` class, passing in a dictionary (an instance of `NSDictionary`) of advertisement data:
当您将服务和特性发布到设备的服务和特性数据库中时，您就可以开始向可能正在监听的任何中心发布其中一些服务和特性。如以下示例所示，您可以通过调用 `CBPeripheralManager` 类的 `startAdvertising:` 方法，传入广告数据的字典（ `NSDictionary` 的实例）来广告您的某些服务：

| `    [myPeripheralManager startAdvertising:@{ CBAdvertisementDataServiceUUIDsKey :` |
| ------------------------------------------------------------ |
| `        @[myFirstService.UUID, mySecondService.UUID] }];`   |

In this example, the only key in the dictionary, `CBAdvertisementDataServiceUUIDsKey`, expects as a value an array (an instance of `NSArray`) of `CBUUID` objects that represent the UUIDs of the services you want to advertise. The possible keys that you may specify in a dictionary of advertisement data are detailed in the constants described in `Advertisement Data Retrieval Keys` in *[CBCentralManagerDelegate Protocol Reference](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate)*. That said, only two of the keys are supported for peripheral manager objects: `CBAdvertisementDataLocalNameKey` and `CBAdvertisementDataServiceUUIDsKey`.
在本例中，字典中唯一的键 `CBAdvertisementDataServiceUUIDsKey` 需要一个由 `CBUUID` 对象组成的数组（ `NSArray` 的一个实例）作为值，这些对象表示您要通告的服务的UUID。在CBCentralManagerDelegate Protocol Reference中的 `Advertisement Data Retrieval Keys` 中描述的常量中详细说明了您可能在广告数据字典中指定的可能键。也就是说，外围设备管理器对象只支持两个键： `CBAdvertisementDataLocalNameKey` 和 `CBAdvertisementDataServiceUUIDsKey` 。

When you start advertising some of the data on your local peripheral, the peripheral manager calls the `peripheralManagerDidStartAdvertising:error:` method of its delegate object. If an error occurs and your services can’t be advertised, implement this delegate method to access the cause of the error, like this:
当您开始在本地外围设备上通告某些数据时，外围设备管理器将调用其委托对象的 `peripheralManagerDidStartAdvertising:error:` 方法。如果发生错误，并且您的服务无法被广告，则实现此委托方法以访问错误的原因，如下所示：

| `- (void)peripheralManagerDidStartAdvertising:(CBPeripheralManager *)peripheral` |
| ------------------------------------------------------------ |
| `                                       error:(NSError *)error {` |
| ` `                                                          |
| `    if (error) {`                                           |
| `        NSLog(@"Error advertising: %@", [error localizedDescription]);` |
| `    }`                                                      |
| `    ...`                                                    |



**Note:** Data advertising is done on a “best effort” basis, because space is limited and there may be multiple apps advertising simultaneously. For more information, see the discussion of the `startAdvertising:` method in *[CBPeripheralManager Class Reference](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)*.
注意：数据广告是在“尽力”的基础上进行的，因为空间有限，可能会有多个应用程序同时进行广告。有关更多信息，请参见CBPeripheralManager类参考中对 `startAdvertising:` 方法的讨论。

Advertising behavior is also affected when your app is in the background. This topic is discussed in the next chapter, [Core Bluetooth Background Processing for iOS Apps](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW1).
当您的应用处于后台时，广告行为也会受到影响。此主题将在下一章“iOS应用的核心蓝牙后台处理”中讨论。



Once you begin advertising data, remote centrals can discover and initiate a connection with you.
一旦您开始通告数据，远程中心就可以发现并启动与您的连接。



## Responding to Read and Write Requests from a Central 响应来自中心的读和写请求

After you are connected to one or more remote centrals, you may begin receiving read or write requests from them. When you do, be sure to respond to those requests in an appropriate manner. The following examples describe how to handle such requests.
连接到一个或多个远程中心后，您可以开始接收来自它们的读或写请求。当你这样做时，一定要以适当的方式回应这些请求。下面的示例描述如何处理此类请求。

When a connected central requests to read the value of one of your characteristics, the peripheral manager calls the `peripheralManager:didReceiveReadRequest:` method of its delegate object. The delegate method delivers the request to you in the form of a `CBATTRequest` object, which has a number of properties that you can use to fulfill the request.
当连接的中心请求读取您的某个特征的值时，外围设备管理器将调用其委托对象的 `peripheralManager:didReceiveReadRequest:` 方法。delegate方法以 `CBATTRequest` 对象的形式将请求传递给您，该对象具有许多可用于完成请求的属性。

For example, when you receive a simple request to read the value of a characteristic, the properties of the `CBATTRequest` object you receive from the delegate method can be used to make sure that the characteristic in your device’s database matches the one that the remote central specified in the original read request. You can begin to implement this delegate method, like this:
例如，当您收到读取特征值的简单请求时，从委托方法接收的 `CBATTRequest` 对象的属性可用于确保设备数据库中的特征与远程中心在原始读取请求中指定的特征相匹配。你可以开始实现这个委托方法，像这样：

| `- (void)peripheralManager:(CBPeripheralManager *)peripheral` |
| ------------------------------------------------------------ |
| `    didReceiveReadRequest:(CBATTRequest *)request {`        |
| ` `                                                          |
| `    if ([request.characteristic.UUID isEqual:myCharacteristic.UUID]) {` |
| `        ...`                                                |

If the characteristics’ UUIDs match, the next step is to make sure that the read request isn’t asking to read from an index position that is outside the bounds of your characteristic’s value. As the following example shows, you can use a `CBATTRequest` object’s `offset` property to ensure the read request isn’t attempting to read outside the proper bounds:
如果特征的UUID匹配，下一步是确保读请求没有要求从特征值范围之外的索引位置读取。如下面的示例所示，您可以使用 `CBATTRequest` 对象的 `offset` 属性来确保读取请求不会尝试在适当的边界之外进行读取：

| `    if (request.offset > myCharacteristic.value.length) {` |
| ----------------------------------------------------------- |
| `        [myPeripheralManager respondToRequest:request`     |
| `            withResult:CBATTErrorInvalidOffset];`          |
| `        return;`                                           |
| `    }`                                                     |

Assuming the request’s offset is verified, now set the value of the request’s characteristic property (whose value by default is `nil`) to the value of the characteristic you created on your local peripheral, taking into account the offset of the read request:
假设请求的偏移量已验证，现在将请求的characteristic属性的值（默认值为 `nil` ）设置为您在本地外围设备上创建的characteristic的值，同时考虑读取请求的偏移量：

| `    request.value = [myCharacteristic.value`               |
| ----------------------------------------------------------- |
| `        subdataWithRange:NSMakeRange(request.offset,`      |
| `        myCharacteristic.value.length - request.offset)];` |

After you set the value, respond to the remote central to indicate that the request was successfully fulfilled. Do so by calling the `respondToRequest:withResult:` method of the `CBPeripheralManager` class, passing back the request (whose value you updated) and the result of the request, like this:
设置该值后，请响应远程中心以指示请求已成功完成。通过调用 `CBPeripheralManager` 类的 `respondToRequest:withResult:` 方法，返回请求（其值已更新）和请求的结果，如下所示：

| `    [myPeripheralManager respondToRequest:request withResult:CBATTErrorSuccess];` |
| ------------------------------------------------------------ |
| `    ...`                                                    |

Call the `respondToRequest:withResult:` method exactly once each time the `peripheralManager:didReceiveReadRequest:` delegate method is called.
每次调用 `peripheralManager:didReceiveReadRequest:` 委托方法时，只调用 `respondToRequest:withResult:` 方法一次。



**Note:** If the characteristics’ UUIDs do not match, or if the read can not be completed for any other reason, you would not attempt to fulfill the request. Instead, you would call the `respondToRequest:withResult:` method immediately and provide a result that indicated the cause of the failure. For a list of the possible results you may specify, see the `CBATTError Constants` enumeration in *[Core Bluetooth Constants Reference](https://developer.apple.com/documentation/corebluetooth/core_bluetooth_constants)*.
注意：如果特征的UUID不匹配，或者由于任何其他原因无法完成读取，则不会尝试完成请求。相反，您应该立即调用 `respondToRequest:withResult:` 方法，并提供一个指示失败原因的结果。有关您可能指定的可能结果的列表，请参见Core Bluetooth Constants Reference中的 `CBATTError Constants` 枚举。



Handling write requests from a connected central is also straightforward. When a connected central sends a request to write the value of one or more of your characteristics, the peripheral manager calls the `peripheralManager:didReceiveWriteRequests:` method of its delegate object. This time, the delegate method delivers the requests to you in the form of an array containing one or more `CBATTRequest` objects, each representing a write request. After you have ensured that a write request can be fulfilled, you can write the characteristic’s value, like this:
处理来自连接的中心的写入请求也很简单。当连接的中心设备发送写入一个或多个特性值的请求时，外围设备管理器将调用其委托对象的 `peripheralManager:didReceiveWriteRequests:` 方法。这一次，delegate方法以数组的形式将请求传递给您，该数组包含一个或多个 `CBATTRequest` 对象，每个对象代表一个写请求。在确保写入请求可以完成后，您可以写入特征的值，如下所示：

```
    myCharacteristic.value = request.value;
```

Although the above example does not demonstrate this, be sure to take into account the request’s offset property when writing the value of your characteristic.
尽管上面的示例没有说明这一点，但在写入特征值时请务必考虑请求的偏移量属性。

Just as you respond to a read request, call the `respondToRequest:withResult:` method exactly once each time the `peripheralManager:didReceiveWriteRequests:` delegate method is called. That said, the first parameter of the `respondToRequest:withResult:` method expects a single `CBATTRequest` object, even though you may have received an array containing more than one of them from the `peripheralManager:didReceiveWriteRequests:` delegate method. You should pass in the first request of the array, like this:
就像你响应一个读请求一样，每次调用 `peripheralManager:didReceiveWriteRequests:` 委托方法时，只调用一次 `respondToRequest:withResult:` 方法。也就是说， `respondToRequest:withResult:` 方法的第一个参数需要一个 `CBATTRequest` 对象，即使您可能从 `peripheralManager:didReceiveWriteRequests:` 委托方法接收到一个包含多个对象的数组。你应该传入数组的第一个请求，像这样：

| `    [myPeripheralManager respondToRequest:[requests objectAtIndex:0]` |
| ------------------------------------------------------------ |
| `        withResult:CBATTErrorSuccess];`                     |



**Note:** Treat multiple requests as you would a single request—if any individual request cannot be fulfilled, you should not fulfill any of them. Instead, call the `respondToRequest:withResult:` method immediately and provide a result that indicates the cause of the failure.
注意：将多个请求视为单个请求-如果任何单个请求无法满足，则不应满足其中任何一个请求。相反，请立即调用 `respondToRequest:withResult:` 方法并提供一个指示失败原因的结果。





## Sending Updated Characteristic Values to Subscribed Centrals 将更新的特征值发送到订阅的中心

Often, connected centrals will subscribe to one or more of your characteristic values, as described in [Subscribing to a Characteristic’s Value](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW16). When they do, you are responsible for sending them notifications when the value of characteristic they subscribed to changes. The following examples describe how.
连接的中心节点通常会订阅一个或多个特征值，如订阅特征值中所述。当他们这样做时，您负责在他们订阅的特征值发生变化时向他们发送通知。下面的例子描述了如何。

When a connected central subscribes to the value of one of your characteristics, the peripheral manager calls the `peripheralManager:central:didSubscribeToCharacteristic:` method of its delegate object:
当连接的中心设备订阅您的某个特征的值时，外围设备管理器将调用其委托对象的 `peripheralManager:central:didSubscribeToCharacteristic:` 方法：

| `- (void)peripheralManager:(CBPeripheralManager *)peripheral` |
| ------------------------------------------------------------ |
| `                  central:(CBCentral *)central`             |
| `didSubscribeToCharacteristic:(CBCharacteristic *)characteristic {` |
| ` `                                                          |
| `    NSLog(@"Central subscribed to characteristic %@", characteristic);` |
| `    ...`                                                    |

Use the above delegate method as a cue to start sending the central updated values.
使用上面的delegate方法作为开始发送中心更新值的提示。

Next, get the updated value of the characteristic and send it to the central by calling the `updateValue:forCharacteristic:onSubscribedCentrals:` method of the `CBPeripheralManager` class.
接下来，获取特征的更新值，并通过调用 `CBPeripheralManager` 类的 `updateValue:forCharacteristic:onSubscribedCentrals:` 方法将其发送到中心。

| `    NSData *updatedValue = // fetch the characteristic's new value` |
| ------------------------------------------------------------ |
| `    BOOL didSendValue = [myPeripheralManager updateValue:updatedValue` |
| `        forCharacteristic:characteristic onSubscribedCentrals:nil];` |

When you call this method to send updated characteristic values to subscribed centrals, you can specify which centrals you want to update in the last parameter. As in the above example, if you specify `nil`, all connected and subscribed centrals are updated (and any connected centrals that have not subscribed are ignored).
当您调用此方法将更新的特征值发送到订阅的中心时，可以在最后一个参数中指定要更新的中心。与上面的示例一样，如果指定 `nil` ，则将更新所有已连接和已订阅的中心节点（并且忽略任何尚未订阅的已连接中心节点）。

The `updateValue:forCharacteristic:onSubscribedCentrals:` method returns a Boolean value that indicates whether the update was successfully sent to the subscribed centrals. If the underlying queue that is used to transmit the updated value is full, the method returns `NO`. The peripheral manager then calls the `peripheralManagerIsReadyToUpdateSubscribers:` method of its delegate object when more space in the transmit queue becomes available. You can then implement this delegate method to resend the value, again using the `updateValue:forCharacteristic:onSubscribedCentrals:` method.
`updateValue:forCharacteristic:onSubscribedCentrals:` 方法返回一个布尔值，该值指示更新是否已成功发送到订阅的中心。如果用于传输更新值的底层队列已满，则该方法返回 `NO` 。然后，当传输队列中有更多的空间可用时，外围设备管理器调用其委托对象的 `peripheralManagerIsReadyToUpdateSubscribers:` 方法。然后，您可以实现此委托方法以重新发送值，同样使用 `updateValue:forCharacteristic:onSubscribedCentrals:` 方法。



**Note:** Use notifications to send a single packet of data to subscribed centrals. That is, when you update a subscribed central, you should send the entire updated value in a single notification, by calling the `updateValue:forCharacteristic:onSubscribedCentrals:` method only once.
注意：使用通知将单个数据包发送到订阅的中心。也就是说，当您更新订阅的中心时，您应该通过仅调用一次 `updateValue:forCharacteristic:onSubscribedCentrals:` 方法，在单个通知中发送整个更新的值。

Depending on the size of your characteristic’s value, not all of the data may be transmitted by the notification. If this happens, the situation should be handled on the central side through a call to the `readValueForCharacteristic:` method of the `CBPeripheral` class, which can retrieve the entire value.
根据您的特征值的大小，并非所有数据都可以通过通知传输。如果发生这种情况，应该在中心端通过调用 `CBPeripheral` 类的 `readValueForCharacteristic:` 方法来处理这种情况，该方法可以检索整个值。