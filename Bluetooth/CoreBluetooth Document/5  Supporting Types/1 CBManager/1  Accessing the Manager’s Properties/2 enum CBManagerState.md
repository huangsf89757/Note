Enumeration 枚举

# CBManagerState

The possible states of a Core Bluetooth manager.
核心蓝牙管理器的可能状态。

iOS 10.0+ ｜ iPadOS 10.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 10.0+ ｜ visionOS 1.0+ ｜ watchOS 3.0+ 

```
enum CBManagerState
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#topics)

### [Manager States 管理员状态](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#Manager-States)

#### [`case poweredOff`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/poweredoff)

A state that indicates Bluetooth is currently powered off.
指示蓝牙当前已关闭的状态。



#### [`case poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/poweredon)

A state that indicates Bluetooth is currently powered on and available to use.
指示蓝牙当前已通电并可供使用的状态。



#### [`case resetting`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/resetting)

A state that indicates the connection with the system service was momentarily lost.
指示与系统服务的连接暂时丢失的状态。



#### [`case unauthorized`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/unauthorized)

A state that indicates the application isn’t authorized to use the Bluetooth low energy role.
一种状态，指示应用程序未被授权使用蓝牙低功耗角色。



#### [`case unknown`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/unknown)

The manager’s state is unknown.
经理的状态尚不清楚。



#### [`case unsupported`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/unsupported)

A state that indicates this device doesn’t support the Bluetooth low energy central or client role.
指示此设备不支持蓝牙低功耗中心或客户端角色的状态。



### [Initializers](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### RawRepresentable Implementations

原始可代表的实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#see-also)

### [Accessing the Manager’s Properties 删除管理员的属性](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate#Accessing-the-Managers-Properties)

[`var state: CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanager/state)

The current state of the manager.
管理器的当前状态。
