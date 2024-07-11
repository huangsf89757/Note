Enumeration 列举

# CBPeripheralManagerState CBPeripheralManager状态

Values that represent the current state of the peripheral manager.
表示外围管理器的当前状态的值。

iOS 6.0–10.0Deprecated 荒废的iPadOS 6.0–10.0Deprecated 荒废的Mac Catalyst 13.1–13.1Deprecated 荒废的macOS 10.9–10.13Deprecated 荒废的tvOS 9.0–10.0Deprecated 荒废的visionOS 1.0–1.0Deprecated 荒废的watchOS 2.0–3.0Deprecated 荒废的

```
enum CBPeripheralManagerState
```

`Deprecated 荒废的`

Use [`CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate) instead. 请改用 `CBManagerState` 。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#topics)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Constants)

#### [`case unknown`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/unknown)

A manager state that indicates the current state of the peripheral manager is unknown.
指示外围管理器的当前状态未知的管理器状态。



#### [`case resetting`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/resetting)

A manager state that indicates the connection with the system service was momentarily lost.
指示与系统服务的连接暂时丢失的管理器状态。



#### [`case unsupported`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/unsupported)

A manager state that indicates the platform doesn’t support the Bluetooth low energy peripheral/server role.
指示平台不支持低功耗蓝牙外围设备/服务器角色的管理器状态。



#### [`case unauthorized`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/unauthorized)

A manager state that indicates the app isn’t authorized to use the Bluetooth low energy peripheral/server role.
指示应用无权使用低功耗蓝牙外围设备/服务器角色的管理器状态。



#### [`case poweredOff`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredoff)

A manager state that indicates Bluetooth is currently powered off.
指示蓝牙当前已关闭电源的管理器状态。



#### [`case poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredon)

A manager state that indicates Bluetooth is currently powered on and is available to use.
指示蓝牙当前已打开电源并可供使用的管理器状态。



### [Initializers 初始值设定项](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Default-Implementations)

#### Equatable Implementations

等式实现



#### RawRepresentable Implementations

RawRepresentable 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#see-also)

### [Deprecated 荒废的](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate#Deprecated)

[`enum CBCentralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate)

Values that represent the current state of a central manager object.
表示中央管理器对象的当前状态的值。

Deprecated 荒废的



Deprecated Constants 已弃用的常量

This document describes the constants found in the Core Bluetooth framework.
本文档介绍核心蓝牙框架中的常量。