Class 类

# CBDescriptor

An object that provides further information about a remote peripheral’s characteristic.
提供有关远程外围设备特性的进一步信息的对象。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
class CBDescriptor
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#overview)

[`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor) and its subclass [`CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor) represent a descriptor of a peripheral’s characteristic. In partcular, [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor) objects represent the descriptors of a remote peripheral’s characteristic. Descriptors provide further information about a characteristic’s value. For example, they may describe the value in human-readable form and describe how to format the value for presentation purposes. Characteristic descriptors also indicate whether a characteristic’s value indicates or notifies a client (a central) when the value of the characteristic changes.
`CBDescriptor` 及其子类 `CBMutableDescriptor` 表示外围设备的特性的描述符。具体地， `CBDescriptor` 对象表示远程外围设备的特征的描述符。描述符提供关于特征值的进一步信息。例如，它们可以以人类可读的形式描述值，并描述如何格式化值以用于表示目的。特征描述符还指示特征的值在特征的值改变时是否指示或通知客户端（中心）。

[`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) details six predefined descriptors and their corresponding value types. [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor) lists the predefined descriptors and the [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) constants that represent them.
`CBUUID` 详细介绍了六个预定义的描述符及其对应的值类型。 `CBDescriptor` 列出了预定义的描述符和表示它们的 `CBUUID` 常量。

| Descriptor type 描述符类型                         | Descriptor constant 描述子常数                               |
| :------------------------------------------------- | :----------------------------------------------------------- |
| Characteristic extended properties 特征扩展性质    | [`CBUUIDCharacteristicExtendedPropertiesString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicextendedpropertiesstring) |
| Characteristic user description 特征用户描述       | [`CBUUIDCharacteristicUserDescriptionString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicuserdescriptionstring) |
| Client characteristic configuration 客户端特性配置 | [`CBUUIDClientCharacteristicConfigurationString`](https://developer.apple.com/documentation/corebluetooth/cbuuidclientcharacteristicconfigurationstring) |
| Server characteristic configuration 服务器特性配置 | [`CBUUIDServerCharacteristicConfigurationString`](https://developer.apple.com/documentation/corebluetooth/cbuuidservercharacteristicconfigurationstring) |
| Characteristic format 特征格式                     | [`CBUUIDCharacteristicFormatString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicformatstring) |
| Characteristic aggregate format 特征聚合格式       | [`CBUUIDCharacteristicAggregateFormatString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicaggregateformatstring) |



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#topics)

### [Identifying a Descriptor 标识描述符](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#Identifying-a-Descriptor)

#### [`var characteristic: CBCharacteristic?`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor/characteristic)

The characteristic to which this descriptor belongs.
此描述符所属的特性。



### [Accessing Descriptor Data 描述符数据](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#Accessing-Descriptor-Data)

#### [`var value: Any?`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor/value)

The value of the descriptor.
描述符的值。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#inherits-from)

- [`CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)



### [Inherited By 继承](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#inherited-by)

- [`CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#see-also)

### [Services 服务](https://developer.apple.com/documentation/corebluetooth/cbdescriptor#Services)

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

[`class CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor)

An object that provides additional information about a local peripheral’s characteristic.
提供有关本地外设特性的附加信息的对象。
