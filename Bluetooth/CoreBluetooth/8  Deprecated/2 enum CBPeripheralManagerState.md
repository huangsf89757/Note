Enumeration 枚举

# CBPeripheralManagerState 

Values that represent the current state of the peripheral manager.
表示外围设备管理器当前状态的值。

iOS 6.0–10.0 iOS 6.0-10.0Deprecated 弃用iPadOS 6.0–10.0 iPadOS 6.0-10.0Deprecated 弃用Mac Catalyst 13.1–13.1 Mac Catalyst 13.1-13.1Deprecated 弃用macOS 10.9–10.13 macOS 10.9-10.13Deprecated 弃用tvOS 9.0–10.0 tvOS 9.0-10.0Deprecated 弃用visionOS 1.0–1.0 visionOS 1.0-1.0Deprecated 弃用watchOS 2.0–3.0 watchOS 2.0-3.0Deprecated 弃用

```
enum CBPeripheralManagerState
```

Deprecated 弃用

Use [`CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate) instead. 使用 `CBManagerState` 代替。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#topics)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Constants)

#### [`case unknown`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/unknown)

A manager state that indicates the current state of the peripheral manager is unknown.
指示外围设备管理器的当前状态的管理器状态是未知的。



#### [`case resetting`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/resetting)

A manager state that indicates the connection with the system service was momentarily lost.
指示与系统服务的连接暂时丢失的管理器状态。



#### [`case unsupported`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/unsupported)

A manager state that indicates the platform doesn’t support the Bluetooth low energy peripheral/server role.
指示平台不支持蓝牙低功耗外设/服务器角色的管理器状态。



#### [`case unauthorized`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/unauthorized)

A manager state that indicates the app isn’t authorized to use the Bluetooth low energy peripheral/server role.
一种管理器状态，指示应用未被授权使用低功耗蓝牙外设/服务器角色。



#### [`case poweredOff`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredoff)

A manager state that indicates Bluetooth is currently powered off.
指示蓝牙当前已关闭电源的管理器状态。



#### [`case poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredon)

A manager state that indicates Bluetooth is currently powered on and is available to use.
一种管理器状态，指示蓝牙当前已通电并可供使用。



### [Initializers](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### RawRepresentable Implementations

原始可代表的实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#see-also)

### [Deprecated 弃用](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Deprecated)

[`enum CBCentralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate)

Values that represent the current state of a central manager object.
表示中央管理器对象的当前状态的。

Deprecated 弃用



Deprecated Constants 不推荐的常量

This document describes the constants found in the Core Bluetooth framework.
本文档描述了Core Bluetooth框架中的常量。
