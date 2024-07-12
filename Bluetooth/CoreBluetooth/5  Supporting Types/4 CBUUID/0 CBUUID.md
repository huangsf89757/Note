Class 类

# CBUUID

A universally unique identifier, as defined by Bluetooth standards.
一种通用的唯一标识符，由蓝牙标准定义。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
class CBUUID
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbuuid#overview)

Instances of the [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) class represent the 128-bit universally unique identifiers (UUIDs) of attributes used in Bluetooth low energy communication, such as a peripheral’s services, characteristics, and descriptors. This class provides a number of factory methods for dealing with long UUIDs when developing your app. For example, instead of passing around the string representation of a 128-bit Bluetooth low energy attribute in your code, you can create a [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object that represents it, and pass that around instead.
`CBUUID` 类的标识符表示蓝牙低功耗通信中使用的属性的128位通用唯一标识符（UUID），例如外围设备的服务、特性和描述符。此类提供了许多工厂方法，用于在开发应用时处理长UUID。例如，您可以创建一个表示128位蓝牙低功耗属性的 `CBUUID` 对象，然后将其传递给其他对象，而不是在代码中传递该属性的字符串表示。

The Bluetooth Special Interest Group (SIG) publishes a list of commonly-used UUIDs, many of which are 16- or 32-bits for convenience. The [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) class provides methods that automatically transform these predefined shorter UUIDs into their 128-bit equivalent UUIDs. When you create a [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object from a predefined 16- or 32-bit UUID, Core Bluetooth pre-fills the rest of the 128-bit UUID with the Bluetooth base UUID, as defined in the Bluetooth 4.0 specification, Volume 3, Part F, Section 3.2.1.
Bluetooth Special Interest Group（SIG）发布了一个常用UUID列表，其中许多是16位或32位的。 `CBUUID` 类提供了自动将这些预定义的较短UUID转换为它们的128位等效UUID的方法。当您从预定义的16位或32位UUID创建 `CBUUID` 对象时，Core Bluetooth会使用Bluetooth Base UUID预填充128位UUID的其余部分，如Bluetooth 4.0规范第3卷F部分第3.2.1节中所定义。

In addition to providing methods for creating [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects, this class defines constants that represent the UUIDs of the Bluetooth-defined characteristic descriptors, as defined in the Bluetooth 4.0 specification, Volume 3, Part G, Section 3.3.3.
除了提供创建 `CBUUID` 对象的方法外，这个类还定义了表示蓝牙定义的特征描述符的UUID的常量，如蓝牙4.0规范第3卷G部分第3.3.3节中定义的。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbuuid#topics)

### [Creating New CBUUID Objects 创建新的CBUUID对象](https://developer.apple.com/documentation/corebluetooth/cbuuid#Creating-New-CBUUID-Objects)

#### [`init(string: String)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID string.
从16位、32位或128位UUID字符串创建Core Bluetooth UUID对象。



#### [`init(data: Data)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID data container.
从16位、32位或128位UUID数据容器创建Core Bluetooth UUID对象。



#### [`init(cfuuid: CFUUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry)

Creates a Core Bluetooth UUID object from a Core Foundation UUID object.
从Core Foundation UUID对象创建Core Bluetooth UUID对象。

`Deprecated 弃用`



#### [`init(nsuuid: UUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob)

Creates a Core Bluetooth UUID object from a Foundation UUID object.
从Foundation UUID对象创建Core Bluetooth UUID对象。



### [Inspecting CBUUID Properties 检查CBUUID属性](https://developer.apple.com/documentation/corebluetooth/cbuuid#Inspecting-CBUUID-Properties)

#### [`var data: Data`](https://developer.apple.com/documentation/corebluetooth/cbuuid/data)

The data of the UUID.
UUID的数据。



#### [`var uuidString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuid/uuidstring)

The UUID represented as a string.
表示为字符串的UUID。



### [UUID Constants UUID常量](https://developer.apple.com/documentation/corebluetooth/cbuuid#UUID-Constants)

#### Characteristic Descriptors

特征描述符

Values that represent the UUIDs of the characteristic descriptors.
值，表示特征描述符的UUID。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbuuid#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbuuid#inherits-from)

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbuuid#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSCopying`](https://developer.apple.com/documentation/foundation/nscopying)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbuuid#see-also)

### [Supporting Types 支持类型](https://developer.apple.com/documentation/corebluetooth/cbuuid#Supporting-Types)

[`class CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager)

The abstract base class that manages central and peripheral objects.
管理中心对象和外围对象的抽象基类。

[`class CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest)

A request that uses the Attribute Protocol (ATT).
使用属性协议（ATT）的请求。

[`class CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer)

An object that represents a remote device.
表示远程设备的对象。
