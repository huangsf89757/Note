Class 类

# CBMutableService

A service with writeable property values.
具有可写属性值的服务。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
class CBMutableService
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#overview)

The [`CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice) class adds write access to all of the properties in the [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice) class it inherits from. You use this class to create a service or an included service on a local peripheral device (represented by a [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) object). After creating a service, you can add it to the peripheral’s local database using the [`add(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class. After you add a service to the peripheral’s local database, Core Bluetooth caches the service and you can no longer make changes to it.
`CBMutableService` 类将写入权限添加到它继承的 `CBService` 类中的所有属性。您可以使用此类在本地外围设备（由 `CBPeripheralManager` 对象表示）上创建服务或包含的服务。创建服务后，您可以使用 `CBPeripheralManager` 类的 `add(_:)` 方法将其添加到外围设备的本地数据库。将服务添加到外设的本地数据库后，Core Bluetooth会缓存该服务，您无法再对其进行更改。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#topics)

### [Creating a Mutable Service 创建可变服务](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#Creating-a-Mutable-Service)

#### [`init(type: CBUUID, primary: Bool)`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/init(type:primary:))

Creates a newly initialized mutable service specified by UUID and service type.
创建一个由UUID和服务类型指定的新初始化的可变服务。



### [Managing a Mutable Service 管理可变服务](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#Managing-a-Mutable-Service)

#### [`var characteristics: [CBCharacteristic\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/characteristics)

A list of characteristics of a service.
服务的特性列表。



#### [`var includedServices: [CBService\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/includedservices)

A list of included services.
包含的服务列表。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#inherits-from)

- [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#see-also)

### [Services 服务](https://developer.apple.com/documentation/corebluetooth/cbmutableservice#Services)

[`class CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)

A collection of data and associated behaviors that accomplish a function or feature of a device.
完成设备功能或特性的数据和相关行为的集合。

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
