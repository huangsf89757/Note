Class 类

# CBPeer

An object that represents a remote device.
表示远程设备的对象。

iOS 8.0+iPadOS 8.0+Mac Catalyst 13.1+macOS 10.13+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
class CBPeer
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbpeer#overview)

The [`CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer) class is an abstract base class that defines common behavior for objects representing remote devices. You typically don’t create instances of either [`CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer) or its concrete subclasses. Instead, the system creates them for you during the process of peer discovery.
`CBPeer` 类是一个抽象基类，它定义了表示远程设备的对象的常见行为。你通常不会创建 `CBPeer` 或它的具体子类的实例。相反，系统会在对等点发现过程中为您创建它们。

Your app takes the role of either a central (by creating an instance of [`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)) or a peripheral (by creating an instance of [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)), and interacts through the manager with remote devices in the opposite role. During the process of peer discovery, where a central device scans for peripherals advertising services, the system creates objects from the concrete subclasses of [`CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer) to represent discovered remote devices. The concrete subclasses of [`CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer) are [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) and [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral).
您的应用扮演中心设备（通过创建 `CBCentralManager` 的实例）或外围设备（通过创建 `CBPeripheralManager` 的实例）的角色，并通过管理器与扮演相反角色的远程设备进行交互。在对等体发现的过程期间，其中中央设备扫描外围设备广告服务，系统从 `CBPeer` 的具体子类创建对象以表示所发现的远程设备。 `CBPeer` 的具体子类是 `CBPeripheral` 和 `CBCentral` 。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbpeer#topics)

### [Identifying a Peer 识别对等体](https://developer.apple.com/documentation/corebluetooth/cbpeer#Identifying-a-Peer)

#### [`var identifier: UUID`](https://developer.apple.com/documentation/corebluetooth/cbpeer/identifier)

The UUID associated with the peer.
与对等方关联的UUID。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbpeer#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbpeer#inherits-from)

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)



### [Inherited By 继承](https://developer.apple.com/documentation/corebluetooth/cbpeer#inherited-by)

- [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral)
- [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbpeer#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSCopying`](https://developer.apple.com/documentation/foundation/nscopying)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbpeer#see-also)

### [Supporting Types 支持类型](https://developer.apple.com/documentation/corebluetooth/cbpeer#Supporting-Types)

[`class CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager)

The abstract base class that manages central and peripheral objects.
管理中心对象和外围对象的抽象基类。

[`class CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest)

A request that uses the Attribute Protocol (ATT).
使用属性协议（ATT）的请求。

[`class CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid)

A universally unique identifier, as defined by Bluetooth standards.
一种通用的唯一标识符，由蓝牙标准定义。
