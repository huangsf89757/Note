Class 类

# CBManager

The abstract base class that manages central and peripheral objects.
管理中心对象和外围对象的抽象基类。

iOS 10.0+iPadOS 10.0+Mac Catalyst 13.1+macOS 10.13+tvOS 10.0+visionOS 1.0+watchOS 3.0+

```
class CBManager
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmanager#topics)

### [Accessing the Manager’s Properties 删除管理员的属性](https://developer.apple.com/documentation/corebluetooth/cbmanager#Accessing-the-Managers-Properties)

#### [`var state: CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanager/state)

The current state of the manager.
管理器的当前状态。



#### [`enum CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate)

The possible states of a Core Bluetooth manager.
核心蓝牙管理器的可能状态。



### [Determining Authorization State 确定授权状态](https://developer.apple.com/documentation/corebluetooth/cbmanager#Determining-Authorization-State)

#### [`class var authorization: CBManagerAuthorization`](https://developer.apple.com/documentation/corebluetooth/cbmanager/authorization-swift.type.property)

The current authorization status for using Bluetooth.
使用蓝牙的当前授权状态。



#### [`enum CBManagerAuthorization`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization)

The current authorization state of a Core Bluetooth manager.
核心蓝牙管理器的当前授权状态。



### [Deprecated Properties 不推荐的房产](https://developer.apple.com/documentation/corebluetooth/cbmanager#Deprecated-Properties)

#### [`var authorization: CBManagerAuthorization`](https://developer.apple.com/documentation/corebluetooth/cbmanager/authorization-swift.property)

The current authorization status for using Bluetooth.
使用蓝牙的当前授权状态。

`Deprecated 弃用`



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbmanager#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbmanager#inherits-from)

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)



### [Inherited By 继承](https://developer.apple.com/documentation/corebluetooth/cbmanager#inherited-by)

- [`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)
- [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbmanager#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmanager#see-also)

### [Supporting Types 支持类型](https://developer.apple.com/documentation/corebluetooth/cbmanager#Supporting-Types)

[`class CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest)

A request that uses the Attribute Protocol (ATT).
使用属性协议（ATT）的请求。

[`class CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer)

An object that represents a remote device.
表示远程设备的对象。

[`class CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid)

A universally unique identifier, as defined by Bluetooth standards.
一种通用的唯一标识符，由蓝牙标准定义。
