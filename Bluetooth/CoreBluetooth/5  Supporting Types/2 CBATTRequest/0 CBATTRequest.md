Class 类

# CBATTRequest 

A request that uses the Attribute Protocol (ATT).
使用属性协议（ATT）的请求。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
class CBATTRequest
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbattrequest#overview)

The [`CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest) class represents Attribute Protocol (ATT) read and write requests from remote central devices (represented by [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral) objects). Remote centrals use these ATT requests to read and write characteristic values on local peripherals (represented by [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) objects). Local peripherals, on the other hand, use the properties of [`CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest) objects to respond to the read and write requests appropriately, using the [`respond(to:withResult:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class.
`CBATTRequest` 类表示来自远程中央设备（由 `CBCentral` 对象表示）的属性协议（ATT）读写请求。远程中心使用这些ATT请求来读取和写入本地外围设备（由 `CBPeripheralManager` 对象表示）上的特征值。另一方面，本地外围设备使用 `CBATTRequest` 对象的属性来适当地响应读写请求，使用 `CBPeripheralManager` 类的 `respond(to:withResult:)` 方法。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbattrequest#topics)

### [Requesting to Read and Write Characteristic Values 请求读写特征值](https://developer.apple.com/documentation/corebluetooth/cbattrequest#Requesting-to-Read-and-Write-Characteristic-Values)

#### [`var central: CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/central)

The remote central device that originated the request.
发起请求的远程中心设备。



#### [`var characteristic: CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/characteristic)

The characteristic to read or write the value of.
读取或写入值的特性。



#### [`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/value)

The data that the central reads from or writes to the peripheral.
中心设备从外围设备读取或向外围设备写入的数据。



#### [`var offset: Int`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/offset)

The zero-based index of the first byte for the read or write request.
读或写请求的第一个字节的从零开始的索引。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbattrequest#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbattrequest#inherits-from)

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbattrequest#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbattrequest#see-also)

### [Supporting Types 支持类型](https://developer.apple.com/documentation/corebluetooth/cbattrequest#Supporting-Types)

[`class CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager)

The abstract base class that manages central and peripheral objects.
管理中心对象和外围对象的抽象基类。

[`class CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer)

An object that represents a remote device.
表示远程设备的对象。

[`class CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid)

A universally unique identifier, as defined by Bluetooth standards.
一种通用的唯一标识符，由蓝牙标准定义。
