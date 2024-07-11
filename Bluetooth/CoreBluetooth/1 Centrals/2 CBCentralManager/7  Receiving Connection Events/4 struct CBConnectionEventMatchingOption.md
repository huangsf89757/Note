Structure 结构

# CBConnectionEventMatchingOption

A set of options to use when registering for connection events.
注册连接事件时要使用的一组选项。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.0+macOS 10.10+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
struct CBConnectionEventMatchingOption
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#topics)

### [Creating a Matching Option Instance 创建匹配选项实例](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#Creating-a-Matching-Option-Instance)

#### [`init(rawValue: String)`](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption/init(rawvalue:))

Creates a matching option from the provided raw value.
根据提供的原始值创建匹配选项。



### [Matching Options 匹配选项](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#Matching-Options)

#### [`static let peripheralUUIDs: CBConnectionEventMatchingOption`](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption/peripheraluuids)

An array of UUID objects that represents peripherals to match.
表示要匹配的外围设备的 UUID 对象数组。



#### [`static let serviceUUIDs: CBConnectionEventMatchingOption`](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption/serviceuuids)

An array that represents service identifiers to match.
一个数组，表示要匹配的服务标识符。



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#Default-Implementations)

#### Equatable Implementations

等式实现



#### _SwiftNewtypeWrapper Implementations

_SwiftNewtypeWrapper实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#conforms-to)

- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#see-also)

### [Receiving Connection Events 接收连接事件](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption#Receiving-Connection-Events)

[`func registerForConnectionEvents(options: [CBConnectionEventMatchingOption : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:))

Register for an event notification when the central manager makes a connection matching the given options.

当中央管理器建立与给定选项匹配的连接时，注册事件通知。

Peripheral Connection Options

Keys used to pass options when connecting to a peripheral.
用于在连接到外围设备时传递选项的键。

[`enum CBConnectionEvent`](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent)

A change to the connection state of a peer.
对等方连接状态的更改。