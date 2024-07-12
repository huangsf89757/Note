Instance Property Instance 属性

# ancsAuthorized 

A Boolean value that indicates if the remote device has authorization to receive data over ANCS protocol.
一个 Boolean 值，该值指示远程设备是否有权通过 ANCS 协议接收数据。

iOS 13.0+ ｜ iPadOS 13.0+ ｜ Mac Catalyst 13.1+ ｜ tvOS 13.0+ ｜ visionOS 1.0+ ｜ watchOS 6.0+ 

```
var ancsAuthorized: Bool { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/ancsauthorized#Discussion)

If this value is [`false`](https://developer.apple.com/documentation/swift/false), a user authorization sets this value to [`true`](https://developer.apple.com/documentation/swift/true), which results in a call to the delegate’s [`centralManager(_:didUpdateANCSAuthorizationFor:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didupdateancsauthorizationfor:)) method.
如果此值为 `false` ，则用户授权将 `centralManager(_:didUpdateANCSAuthorizationFor:)` 此值设置为 `true` ，这将导致调用委托的方法。
