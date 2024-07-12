Instance Method Instance 方法

# peripheralManager(_:didReceiveWrite:) 

Tells the delegate that a local peripheral device received an Attribute Protocol (ATT) write request for a characteristic with a dynamic value.
告知委托本地外围设备收到了具有动态值的特征的属性协议 （ATT） 写入请求。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    didReceiveWrite requests: [CBATTRequest]
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)#parameters)

- `peripheral`

  The peripheral manager that received the request. 接收请求的外围管理器。

- `requests`

  A list of one or more [`CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest) objects, each representing a request to write the value of a characteristic. 一个或多个 `CBATTRequest` 对象的列表，每个对象都表示写入特征值的请求。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)#Discussion)

In the same way that you respond to a read request, each time you receive this callback, call the [`respond(to:withResult:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class exactly once. If the `requests` parameter contains multiple requests, treat them as you would a single request—if you can’t fulfill an individual request, you shouldn’t fulfill any of them. Instead, call the [`respond(to:withResult:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)) method immediately, and provide a result that indicates the cause of the failure.
与响应读取请求的方式相同，每次收到此回调时，都要调用 `CBPeripheralManager` 该类 `respond(to:withResult:)` 的方法一次。如果 `requests` 参数包含多个请求，请像对待单个请求一样对待它们 - 如果您无法满足单个请求，则不应满足其中任何一个请求。相反，请立即调用该 `respond(to:withResult:)` 方法，并提供指示失败原因的结果。

When you respond to a write request, note that the first parameter of the [`respond(to:withResult:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)) method expects a single [`CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest) object, even though you received an array of them from the [`peripheralManager(_:didReceiveWrite:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)) method. To respond properly, pass in the first request of the `requests` array.
当您响应写入请求时，请注意， `respond(to:withResult:)` 该方法的第一个参数需要单个 `CBATTRequest` 对象，即使您从 `peripheralManager(_:didReceiveWrite:)` 该方法收到了一个对象的数组。若要正确响应，请传入 `requests` 数组的第一个请求。

## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)#see-also)

### [Receiving Read and Write Requests 接收读写请求](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)#Receiving-Read-and-Write-Requests)

[`func peripheralManager(CBPeripheralManager, didReceiveRead: CBATTRequest)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:))

Tells the delegate that a local peripheral received an Attribute Protocol (ATT) read request for a characteristic with a dynamic value.
告知委托本地外设收到了具有动态值的特征的属性协议 （ATT） 读取请求。
