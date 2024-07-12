# Best Practices for Setting Up Your Local Device as a Peripheral 将本地设备设置为外围设备的最佳做法

As with many central-side transactions, the Core Bluetooth framework give you control over implementing most aspects of the peripheral role. This chapter provides guidelines and best practices for harnessing this level of control in a responsible way.
与许多中心端事务一样，Core Bluetooth框架允许您控制实现外围角色的大多数方面。本章提供了以负责任的方式利用这一级别的控制的指导方针和最佳实践。



## Advertising Considerations 广告注意事项

Advertising peripheral data is an important part of setting up your local device to implement the peripheral role. The following sections assist you in doing so in an appropriate way.
通告外设数据是设置本地设备以实现外设角色的重要部分。以下各节将帮助您以适当的方式执行此操作。



### Respect the Limits of Advertising Data 尊重广告数据的限制

You advertise your peripheral’s data by passing in a dictionary of advertising data to the `startAdvertising:` method of the `CBPeripheralManager` class, as described in [Advertising Your Services](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW5). When you create an advertising dictionary, keep in mind that there are limits to what, as well as how much, you can advertise.
通过将广告数据字典传递给 `CBPeripheralManager` 类的 `startAdvertising:` 方法来广告外围设备的数据，如广告您的服务中所述。当你创建一个广告词典时，请记住，你可以做广告的内容和数量是有限制的。

Although advertising packets in general can hold a variety of information about the peripheral device, you may advertise only your device’s local name and the UUIDs of any services you want to advertise. That is, when you create your advertising dictionary, you may specify only the following two keys: `CBAdvertisementDataLocalNameKey` and `CBAdvertisementDataServiceUUIDsKey`. You receive an error if you specify any other keys.
虽然广告数据包通常可以包含有关外围设备的各种信息，但您可以仅广告设备的本地名称和要广告的任何服务的UUID。也就是说，在创建广告词典时，您只能指定以下两个键： `CBAdvertisementDataLocalNameKey` 和 `CBAdvertisementDataServiceUUIDsKey` 。如果指定任何其他键，则会收到错误。

There are also limits as to how much space you can use when advertising data. When your app is in the foreground, it can use up to 28 bytes of space in the initial advertisement data for any combination of the two supported advertising data keys. If this space is used up, there are an additional 10 bytes of space in the scan response that can be used only for the local name. Any service UUIDs that do not fit in the allotted space are added to a special “overflow” area; they can be discovered only by an iOS device that is explicitly scanning for them. While your app is in the background, the local name is not advertised and all service UUIDs are place in the overflow area.
广告数据时可以使用的空间也有限制。当您的应用处于前台时，它可以在初始广告数据中使用最多28字节的空间，用于两个受支持的广告数据键的任意组合。如果此空间用完，则扫描响应中还有10个字节的额外空间，仅可用于本地名称。任何不适合分配空间的服务UUID都将被添加到一个特殊的“溢出”区域;它们只能被显式扫描它们的iOS设备发现。当您的应用处于后台时，不会通告本地名称，并且所有服务UUID都位于溢出区域。



**Note:** These sizes do not include the 2 bytes of header information that are required for each new data type. The exact format of advertising and response data is defined in the Bluetooth 4.0 specification, Volume 3, Part C, Section 11.
注意：这些大小不包括每个新数据类型所需的2字节的标头信息。广告和响应数据的确切格式在蓝牙4.0规范第3卷C部分第11节中定义。



To help you stay within these space constraints, limit the service UUIDs you advertise to those that identify your primary services.
为了帮助您保持在这些空间限制之内，请将广告的服务UUID限制为标识您的主要服务的UUID。



### Advertise Data Only When You Need To 仅在需要时验证数据

Since advertising peripheral data uses your local device’s radio (and thus your device’s battery), advertise only when you want other devices to connect to you. Once connected, these devices can explore and interact the peripheral’s data directly, without the need for any advertising packets. Therefore, to minimize radio usage, increase app performance, and preserve your device’s battery, stop advertising when it is no longer necessary to facilitate any intended Bluetooth low energy transaction. To stop advertising on your local peripheral, simply call the `stopAdvertising` method of the `CBPeripheralManager` class, like this:
由于通告外围设备数据会使用本地设备的无线电（因此也会使用设备的电池），因此仅当您希望其他设备连接到您时才进行通告。一旦连接，这些设备就可以直接探索和交互外围设备的数据，而不需要任何广告数据包。因此，为了最大限度地减少无线电使用，提高应用性能，并保护设备的电池，请在不再需要进行任何预期的蓝牙低功耗交易时停止广告。要停止在本地外围设备上发布广告，只需调用 `CBPeripheralManager` 类的 `stopAdvertising` 方法，如下所示：

```
    [myPeripheralManager stopAdvertising];
```



#### Let the User Decide When to Advertise 让用户决定何时进行认证

Knowing when to advertise is often something only the user can know. For example, it doesn’t make sense to have your app advertise services on your device when you know there aren’t any other Bluetooth low energy devices nearby. Since your app is often unaware of what other devices are nearby, provide in your app’s user interface (UI) a way for the user to decide when to advertise.
知道什么时候做广告通常只有用户才知道。例如，当您知道附近没有任何其他低功耗蓝牙设备时，让您的应用在您的设备上宣传服务是没有意义的。由于您的应用通常不知道附近有哪些其他设备，因此请在应用的用户界面（UI）中提供一种方式，让用户决定何时投放广告。



## Configuring Your Characteristics 配置您的特征

When you create a mutable characteristic, you set its properties, value, and permissions. These settings determine how connected centrals access and interact with the characteristic’s value. Although you may decide to configure the properties and permissions of your characteristics differently based on the needs of your app, the following sections provide some guidance when you need to perform the following two tasks:
当您创建一个可变特性时，您需要设置它的属性、值和权限。这些设置确定连接的中心体如何访问特征值以及如何与特征值交互。尽管您可能会根据应用的需要决定以不同方式配置特性的属性和权限，但以下各节提供了您需要执行以下两项任务时的一些指导：

- Allow connected centrals to subscribe to your characteristics
  允许连接的中心订阅您的特性
- Protect sensitive characteristic values from being accessed by unpaired centrals
  保护敏感的特征值不被未配对的中心访问



### Configure Your Characteristics to Support Notifications 配置您的特性以支持SSL

As described in [Subscribe to Characteristic Values That Change Often](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW7), it is recommended that centrals subscribe to characteristic values (of a remote peripheral’s service) that change often. When possible, encourage this practice by allowing connected centrals to subscribe to your characteristics’ values.
如订阅经常更改的特征值中所述，建议中心设备订阅经常更改的特征值（远程外围设备的服务）。如果可能的话，鼓励这种做法，允许连接的中心订阅你的特征的价值观。

When you create a mutable characteristic, configure it to support subscriptions by setting the characteristic’s properties with the `CBCharacteristicPropertyNotify` constant, like this:
当你创建一个可变特征时，通过使用 `CBCharacteristicPropertyNotify` 常量设置特征的属性来配置它以支持订阅，如下所示：

| `    myCharacteristic = [[CBMutableCharacteristic alloc]`    |
| ------------------------------------------------------------ |
| `        initWithType:myCharacteristicUUID`                  |
| `        properties:CBCharacteristicPropertyRead | CBCharacteristicPropertyNotify` |
| `        value:nil permissions:CBAttributePermissionsReadable];` |

In this example, the characteristic’s value is readable, and it can be subscribed to by a connected central.
在此示例中，特征的值是可读的，并且可以由连接的中心订阅。



### Require a Paired Connection to Access Sensitive Data 需要配对连接才能访问敏感数据

Depending on the use case, you may want to vend a service that has one or more characteristic whose value needs to be secure. For example, imagine that you want to vend a social media profile service. This service may have characteristics whose values represent a member’s profile information, such as first name, last name, and email address. More than likely, you want to allow only trusted devices to retrieve a member’s email address.
根据用例，您可能希望出售具有一个或多个特征的服务，这些特征的值需要是安全的。例如，假设您想要出售社交媒体配置文件服务。此服务可能具有其值表示成员的配置文件信息（如名字、姓氏和电子邮件地址）的特征。更有可能的是，您希望只允许受信任的设备检索成员的电子邮件地址。

You can ensure that only trusted devices have access to sensitive characteristic values by setting the appropriate characteristic properties and permissions. To continue the example above, to allow only trusted devices to retrieve a member’s email address, set the appropriate characteristic’s properties and permissions, like this:
通过设置适当的特征属性和权限，可以确保只有受信任的设备才能访问敏感特征值。要继续上面的示例，仅允许受信任的设备检索成员的电子邮件地址，请设置相应特征的属性和权限，如下所示：

| `    emailCharacteristic = [[CBMutableCharacteristic alloc]` |
| ------------------------------------------------------------ |
| `        initWithType:emailCharacteristicUUID`               |
| `        properties:CBCharacteristicPropertyRead`            |
| `        | CBCharacteristicPropertyNotifyEncryptionRequired` |
| `        value:nil permissions:CBAttributePermissionsReadEncryptionRequired];` |

In this example, the characteristic is configured to allow only trusted devices to read or subscribe to its value. When a connected, remote central tries to read or subscribe to this characteristic’s value, Core Bluetooth tries to pair your local peripheral with the central to create a secure connection.
在该示例中，特性被配置为仅允许可信设备读取或订阅其值。当连接的远程中心设备尝试读取或订阅此特征值时，Core Bluetooth会尝试将您的本地外设与中心设备配对，以创建安全连接。

For example, if the central and the peripheral are iOS devices, both devices receive an alert indicating that the other device would like to pair. The alert on the central device contains a code that you must enter into a text field on the peripheral device’s alert to complete the pairing process.
例如，如果中心设备和外围设备都是iOS设备，则两个设备都接收到指示另一设备想要配对的警报。中央设备上的警报包含一个代码，您必须在外围设备警报的文本字段中输入该代码才能完成配对过程。

After the pairing process is complete, the peripheral considers the paired central a trusted device and allows the central access to its encrypted characteristic values.
在配对过程完成之后，外围设备将配对的中心设备视为可信设备，并允许中心设备访问其加密的特征值。