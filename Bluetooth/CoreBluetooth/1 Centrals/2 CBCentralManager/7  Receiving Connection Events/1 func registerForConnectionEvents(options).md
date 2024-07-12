Instance Method Instance 方法

# registerForConnectionEvents(options:)

Register for an event notification when the central manager makes a connection matching the given options.
当中央管理器建立与给定选项匹配的连接时，注册事件通知。

iOS 13.0+ ｜ iPadOS 13.0+ ｜ Mac Catalyst 13.1+ ｜ tvOS 13.0+ ｜ visionOS 1.0+ ｜ watchOS 6.0+ 

```
func registerForConnectionEvents(options: [CBConnectionEventMatchingOption : Any]? = nil)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:)#parameters)

- `options`

  A dictionary that specifies options for connection events. See [Peripheral Connection Options](https://developer.apple.com/documentation/corebluetooth/peripheral-connection-options) for a list of possible options. 指定连接事件选项的字典。有关可能选项的列表，请参阅外设连接选项。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:)#Discussion)

When the central manager makes a connection that matches the options, it calls the delegate’s [`centralManager(_:connectionEventDidOccur:for:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:)) method.
当中央管理器建立与选项匹配的连接时，它将调用委托 `centralManager(_:connectionEventDidOccur:for:)` 的方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:)#see-also)

### [Receiving Connection Events 接收连接事件](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:)#Receiving-Connection-Events)

Peripheral Connection Options
外设连接选项

Keys used to pass options when connecting to a peripheral.
用于在连接到外围设备时传递选项的键。

[`enum CBConnectionEvent`](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent)

A change to the connection state of a peer.
对等方连接状态的更改。

[`struct CBConnectionEventMatchingOption`](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption)

A set of options to use when registering for connection events.
注册连接事件时要使用的一组选项。
