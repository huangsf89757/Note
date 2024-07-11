Instance Property Instance 属性

# state

The connection state of the peripheral.
外围设备的连接状态。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
var state: CBPeripheralState { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/state#Discussion)

This property represents the current connection state of the peripheral. For a list of the possible values, see [`CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate).
此属性表示外围设备的当前连接状态。有关可能值的列表，请参见 `CBPeripheralState` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/state#see-also)

### [Monitoring a Peripheral’s Connection State 监视外设的连接状态](https://developer.apple.com/documentation/corebluetooth/cbperipheral/state#Monitoring-a-Peripherals-Connection-State)

[`enum CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate)

Values representing the connection state of a peripheral.
表示外围设备连接状态的值。

[`var canSendWriteWithoutResponse: Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/cansendwritewithoutresponse)

A Boolean value that indicates whether the remote device can send a write without a response.
一个 Boolean 值，该值指示远程设备是否可以在没有响应的情况下发送写入。
