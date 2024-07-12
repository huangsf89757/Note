Class 类

# CBService

A collection of data and associated behaviors that accomplish a function or feature of a device.
完成设备功能或特性的数据和相关行为的集合。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
class CBService
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbservice#overview)

[`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice) objects represent services of a remote peripheral. Services are either primary or secondary and may contain multiple characteristics or included services (references to other services).
`CBService` 对象表示远程外围设备的服务。服务可以是主要的，也可以是次要的，可以包含多个特征或包含的服务（对其他服务的引用）。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbservice#topics)

### [Identifying a Service 识别服务](https://developer.apple.com/documentation/corebluetooth/cbservice#Identifying-a-Service)

#### [`var peripheral: CBPeripheral?`](https://developer.apple.com/documentation/corebluetooth/cbservice/peripheral)

The peripheral to which this service belongs.
此服务所属的外围设备。



#### [`var isPrimary: Bool`](https://developer.apple.com/documentation/corebluetooth/cbservice/isprimary)

A Boolean value that indicates whether the type of service is primary or secondary.
一个布尔值，指示服务类型是主服务还是辅助服务。



### [Accessing Service Data 服务数据](https://developer.apple.com/documentation/corebluetooth/cbservice#Accessing-Service-Data)

#### [`var characteristics: [CBCharacteristic\]?`](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics)

A list of characteristics discovered in this service.
在此服务中发现的特征列表。



#### [`var includedServices: [CBService\]?`](https://developer.apple.com/documentation/corebluetooth/cbservice/includedservices)

A list of included services discovered in this service.
在此服务中发现的包含服务的列表。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbservice#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbservice#inherits-from)

- [`CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)



### [Inherited By 继承](https://developer.apple.com/documentation/corebluetooth/cbservice#inherited-by)

- [`CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbservice#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbservice#see-also)

### [Services 服务](https://developer.apple.com/documentation/corebluetooth/cbservice#Services)

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

[`class CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor)

An object that provides additional information about a local peripheral’s characteristic.
提供有关本地外设特性的附加信息的对象。
