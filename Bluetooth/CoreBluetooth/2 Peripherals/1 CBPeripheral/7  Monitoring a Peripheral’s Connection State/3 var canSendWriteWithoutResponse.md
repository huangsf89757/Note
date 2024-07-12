Instance Property Instance 属性

# canSendWriteWithoutResponse

A Boolean value that indicates whether the remote device can send a write without a response.
一个 Boolean 值，该值指示远程设备是否可以在没有响应的情况下发送写入。

iOS 11.0+ ｜ iPadOS 11.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 11.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
var canSendWriteWithoutResponse: Bool { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/cansendwritewithoutresponse#Discussion)

If this value is [`false`](https://developer.apple.com/documentation/swift/false), flushing all current writes sets the value to [`true`](https://developer.apple.com/documentation/swift/true). This also results in a call to the delegate’s [`peripheralIsReady(toSendWriteWithoutResponse:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:)).
如果此值为 `false` ，则刷新所有当前写入会将该值设置为 `true` 。这也会导致调用委托的 `peripheralIsReady(toSendWriteWithoutResponse:)` .



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/cansendwritewithoutresponse#see-also)

### [Monitoring a Peripheral’s Connection State 监视外设的连接状态](https://developer.apple.com/documentation/corebluetooth/cbperipheral/cansendwritewithoutresponse#Monitoring-a-Peripherals-Connection-State)

[`var state: CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/state)

The connection state of the peripheral.
外围设备的连接状态。

[`enum CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate)

Values representing the connection state of a peripheral.
表示外围设备连接状态的值。
