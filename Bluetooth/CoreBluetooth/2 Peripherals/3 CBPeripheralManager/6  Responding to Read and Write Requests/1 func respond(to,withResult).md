Instance Method Instance 方法

# respond(to:withResult:) 

Responds to a read or write request from a connected central.
响应来自连接中心的读取或写入请求。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func respond(
    to request: CBATTRequest,
    withResult result: CBATTError.Code
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)#parameters)

- `request`

  The read or write request received from the connected central. For more information about read and write requests, see [`CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest). 

  从连接的中央接收的读取或写入请求。有关读取和写入请求的详细信息，请参见 `CBATTRequest` 。

- `result`

  The result of attempting to fulfill the request. For a list of possible results, see [Deprecated Constants](https://developer.apple.com/documentation/corebluetooth/deprecated-constants). 

  尝试满足请求的结果。有关可能结果的列表，请参阅已弃用的常量。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)#Discussion)

When the peripheral manager receives a request from a connected central to read or write a characteristic’s value, it calls the [`peripheralManager(_:didReceiveRead:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:)) or [`peripheralManager(_:didReceiveWrite:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)) method of its delegate object. To respond to the corresponding read or write request, you call this method whenever you recevie one of these delegate method callbacks.
当外设管理器收到来自连接的中心读取或写入特征值的请求时，它会调用其委托对象的 `peripheralManager(_:didReceiveRead:)` or `peripheralManager(_:didReceiveWrite:)` 方法。若要响应相应的读取或写入请求，请在收到这些委托方法回调之一时调用此方法。
