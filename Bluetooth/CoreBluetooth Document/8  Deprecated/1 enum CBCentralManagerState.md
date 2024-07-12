Enumeration 枚举

# CBCentralManagerState

Values that represent the current state of a central manager object.
表示中央管理器对象的当前状态的。

iOS 5.0–10.0`Deprecated` | iPadOS 5.0–10.0`Deprecated` | Mac Catalyst 13.1–13.1`Deprecated` | macOS 10.7–10.13`Deprecated` | tvOS 9.0–10.0`Deprecated` | visionOS 1.0–1.0`Deprecated` | watchOS 2.0–3.0`Deprecated`

```
enum CBCentralManagerState
```

`Deprecated 弃用`

Use [`CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate) instead. 使用 `CBManagerState` 代替。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#topics)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#Constants)

#### [`case poweredOff`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/poweredoff)

A state that indicates Bluetooth is currently powered off.
指示蓝牙当前已关闭的状态。



#### [`case poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/poweredon)

A state that indicates Bluetooth is currently powered on and available to use.
指示蓝牙当前已通电并可供使用的状态。



#### [`case resetting`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/resetting)

A state that indicates the connection with the system service was momentarily lost.
指示与系统服务的连接暂时丢失的状态。



#### [`case unauthorized`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/unauthorized)

A state that indicates the application isn’t authorized to use the Bluetooth low energy role.
一种状态，指示应用程序未被授权使用蓝牙低功耗角色。



#### [`case unknown`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/unknown)

The manager’s state is unknown.
经理的状态尚不清楚。



#### [`case unsupported`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/unsupported)

A state that indicates this device doesn’t support the Bluetooth low energy central or client role.
指示此设备不支持蓝牙低功耗中心或客户端角色的状态。



### [Initializers](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### RawRepresentable Implementations

原始可代表的实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#see-also)

### [Deprecated 弃用](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate#Deprecated)

[`enum CBPeripheralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate)

Values that represent the current state of the peripheral manager.
表示外围设备管理器当前状态的值。

Deprecated 弃用



Deprecated Constants 不推荐的常量

This document describes the constants found in the Core Bluetooth framework.
本文档描述了Core Bluetooth框架中的常量。
