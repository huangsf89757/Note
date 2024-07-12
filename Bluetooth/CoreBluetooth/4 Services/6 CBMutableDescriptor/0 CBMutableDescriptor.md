Class 类

# CBMutableDescriptor

An object that provides additional information about a local peripheral’s characteristic.
提供有关本地外设特性的附加信息的对象。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
class CBMutableDescriptor
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#overview)

You use the [`CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor) class to create a local characteristic descriptor. After you create a descriptor and associate it with a local characteristic, you can publish it to the peripheral’s local database using the [`add(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class. This also publishes the characteristic and local service to which the descriptor belongs. After you publish a local descriptor, Core Bluetooth caches the descriptor and you can no longer make changes to it.
您可以使用 `CBMutableDescriptor` 类来创建局部特征描述符。创建描述符并将其与本地特性关联后，可以使用 `CBPeripheralManager` 类的 `add(_:)` 方法将其发布到外围设备的本地数据库。这也会发布描述符所属的特征和本地服务。发布本地描述符后，Core Bluetooth会缓存该描述符，您无法再对其进行更改。

[`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) details predefined descriptor types and their corresponding value types. That said, only two of these are currently supported when creating local, mutable descriptors: the characteristic user description descriptor and the characteristic format descriptor. [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) declares these as the constants [`CBUUIDCharacteristicUserDescriptionString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicuserdescriptionstring) and [`CBUUIDCharacteristicFormatString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicformatstring), respectively. The system automatically creates the extended properties descriptor and the client configuration descriptor, depending on the properties of the characteristic to which the descriptor belongs.
`CBUUID` 详细说明了预定义的描述符类型及其对应的值类型。也就是说，在创建本地可变描述符时，目前只支持其中两个：特征用户描述符和特征格式描述符。 `CBUUID` 分别将它们声明为常量 `CBUUIDCharacteristicUserDescriptionString` 和 `CBUUIDCharacteristicFormatString` 。系统根据描述符所属的特征的属性自动创建扩展属性描述符和客户端配置描述符。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#topics)

### [Creating a Mutable Descriptor 创建可变描述符](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#Creating-a-Mutable-Descriptor)

#### [`init(type: CBUUID, value: Any?)`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor/init(type:value:))

Creates a mutable descriptor with a specified value.
创建具有指定值的可变描述符。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#inherits-from)

- [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#see-also)

### [Services 服务](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor#Services)

[`class CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)

A collection of data and associated behaviors that accomplish a function or feature of a device.
完成设备功能或特性的数据和相关行为的集合。

[`class CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice)

A service with writeable property values.
具有可写属性值的服务。

[`class CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic)

A characteristic of a remote peripheral’s service.
远程外设服务的一种特性。

[`class CBMutableCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic)

A characteristic of a local peripheral’s service.
本地外围设备服务的特征。

[`class CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)

An object that provides further information about a remote peripheral’s characteristic.
提供有关远程外围设备特性的进一步信息的对象。
