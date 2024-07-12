Enumeration 列举

# CBConnectionEvent 

A change to the connection state of a peer.
对等方连接状态的更改。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
enum CBConnectionEvent
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#topics)

### [Events 事件](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#Events)

#### [`case peerConnected`](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent/peerconnected)

The peer has connected to the local device.
对等体已连接到本地设备。



#### [`case peerDisconnected`](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent/peerdisconnected)

The peer has disconnected from the local device.
对等方已断开与本地设备的连接。



### [Initializers 初始值设定项](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#Default-Implementations)

#### Equatable Implementations

等式实现



#### RawRepresentable Implementations

RawRepresentable 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#see-also)

### [Receiving Connection Events 接收连接事件](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent#Receiving-Connection-Events)

[`func registerForConnectionEvents(options: [CBConnectionEventMatchingOption : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:))

Register for an event notification when the central manager makes a connection matching the given options.
当中央管理器建立与给定选项匹配的连接时，注册事件通知。

Peripheral Connection Options
外设连接选项

Keys used to pass options when connecting to a peripheral.
用于在连接到外围设备时传递选项的键。

[`struct CBConnectionEventMatchingOption`](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption)

A set of options to use when registering for connection events.
注册连接事件时要使用的一组选项。