Instance Method Instance 方法

# peripheralManager(_:didReceiveRead:) 

Tells the delegate that a local peripheral received an Attribute Protocol (ATT) read request for a characteristic with a dynamic value.
告知委托本地外设收到了具有动态值的特征的属性协议 （ATT） 读取请求。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    didReceiveRead request: CBATTRequest
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:)#parameters)

- `peripheral`

  The peripheral manager that received the request. 

  接收请求的外围管理器。

- `request`

  A [`CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest) object that represents a request to read a characteristic’s value. 

  一个 `CBATTRequest` 对象，表示读取特征值的请求。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:)#Discussion)

When you receive this callback, call the [`respond(to:withResult:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class exactly once to respond to the read request.
收到此回调时，请调用 `CBPeripheralManager` 该类 `respond(to:withResult:)` 的方法正好一次以响应读取请求。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:)#see-also)

### [Receiving Read and Write Requests 接收读写请求](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:)#Receiving-Read-and-Write-Requests)

[`func peripheralManager(CBPeripheralManager, didReceiveWrite: [CBATTRequest\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:))

Tells the delegate that a local peripheral device received an Attribute Protocol (ATT) write request for a characteristic with a dynamic value.
告知委托本地外围设备收到了具有动态值的特征的属性协议 （ATT） 写入请求。
