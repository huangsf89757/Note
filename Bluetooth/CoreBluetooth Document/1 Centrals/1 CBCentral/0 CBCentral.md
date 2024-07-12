Class 类

# CBCentral

A remote device connected to a local app, which is acting as a peripheral.
连接到本地应用程序的远程设备，该应用程序充当外围设备。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
class CBCentral
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbcentral#overview)

The [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral) class represents remote central devices (or *centrals*) that have connected to an app implementing the peripheral role on a local device. Remote centrals use universally unique identifiers (UUIDs), represented by [`NSUUID`](https://developer.apple.com/documentation/foundation/nsuuid) objects, to identify themselves.
`CBCentral` 类表示已连接到在本地设备上实现外围设备角色的应用的远程中心设备（或中心设备）。远程中心使用通用唯一标识符（UUID）（由 `NSUUID` 对象表示）来标识自己。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcentral#topics)

### [Identifying a Remote Central 识别远程中心](https://developer.apple.com/documentation/corebluetooth/cbcentral#Identifying-a-Remote-Central)

#### [`var maximumUpdateValueLength: Int`](https://developer.apple.com/documentation/corebluetooth/cbcentral/maximumupdatevaluelength)

The maximum amount of data, in bytes, that the central can receive in a single notification or indication.
中心节点在单个通知或指示中可以接收的最大数据量（以字节为单位）。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcentral#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbcentral#inherits-from)

- [`CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcentral#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSCopying`](https://developer.apple.com/documentation/foundation/nscopying)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentral#see-also)

### [Centrals 中央设备](https://developer.apple.com/documentation/corebluetooth/cbcentral#Centrals)

#### [`class CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)

An object that scans for, discovers, connects to, and manages peripherals.
扫描、发现、连接和管理外围设备的对象。



#### [`protocol CBCentralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate)

A protocol that provides updates for the discovery and management of peripheral devices.
为发现和管理外围设备提供更新的协议。

