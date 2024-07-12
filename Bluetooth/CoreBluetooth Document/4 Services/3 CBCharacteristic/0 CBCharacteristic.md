Class 类

# CBCharacteristic

A characteristic of a remote peripheral’s service.
远程外设服务的一种特性。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
class CBCharacteristic
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#overview)

[`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic) and its subclass [`CBMutableCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic) represent further information about a peripheral’s service. In particular, [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic) objects represent the characteristics of a remote peripheral’s service. A characteristic contains a single value and any number of descriptors describing that value. The properties of a characteristic determine how you can use a characteristic’s value, and how you access the descriptors.
`CBCharacteristic` 及其子类 `CBMutableCharacteristic` 表示关于外围设备的服务的进一步信息。特别地， `CBCharacteristic` 对象表示远程外围设备的服务的特征。一个特征包含一个值和任意数量的描述该值的描述符。特性的属性决定了如何使用特性的值，以及如何访问描述符。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#topics)

### [Identifying a Characteristic 识别一个特征](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#Identifying-a-Characteristic)

#### [`var service: CBService?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/service)

The service to which this characteristic belongs.
此特性所属的服务。



### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#Accessing-Characteristic-Data)

#### [`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value)

The value of the characteristic.
特性的值。



#### [`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors)

A list of the descriptors discovered in this characteristic.
在此特征中发现的描述符的列表。



#### [`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties)

The properties of the characteristic.
特性的属性。



#### [`struct CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties)

Values that represent the possible properties of a characteristic.
表示特性的可能属性的值。



#### [`var isNotifying: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying)

A Boolean value that indicates whether the characteristic is currently notifying a subscribed central of its value.
一个布尔值，指示特征当前是否正在向订阅中心通知其值。



#### [`var isBroadcasted: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted)

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#inherits-from)

- [`CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)



### [Inherited By 继承](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#inherited-by)

- [`CBMutableCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#see-also)

### [Services 服务](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic#Services)

[`class CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)

A collection of data and associated behaviors that accomplish a function or feature of a device.
完成设备功能或特性的数据和相关行为的集合。

[`class CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice)

A service with writeable property values.
具有可写属性值的服务。

[`class CBMutableCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic)

A characteristic of a local peripheral’s service.
本地外围设备服务的特征。

[`class CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)

An object that provides further information about a remote peripheral’s characteristic.
提供有关远程外围设备特性的进一步信息的对象。

[`class CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor)

An object that provides additional information about a local peripheral’s characteristic.
提供有关本地外设特性的附加信息的对象。
