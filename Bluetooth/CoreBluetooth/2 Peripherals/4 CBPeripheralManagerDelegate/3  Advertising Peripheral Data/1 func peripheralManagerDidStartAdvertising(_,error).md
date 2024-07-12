Instance Method Instance 方法

# peripheralManagerDidStartAdvertising(_:error:) 

Tells the delegate the peripheral manager started advertising the local peripheral device’s data.
告诉代理外围设备管理器开始播发本地外围设备的数据。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheralManagerDidStartAdvertising(
    _ peripheral: CBPeripheralManager,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidstartadvertising(_:error:)#parameters)

- `peripheral`

  The peripheral manager that is starting advertising.

  开始投放广告的外围管理器。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidstartadvertising(_:error:)#Discussion)

Core Bluetooth calls this method when your app calls the [`startAdvertising(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)) method to advertise the local peripheral device’s data. If successful, the `error` parameter is `nil`. If a problem prevents advertising the data, the `error` parameter returns the cause of the failure.
当应用调用该 `startAdvertising(_:)` 方法以通告本地外围设备的数据时，Core Bluetooth 会调用此方法。如果成功，则参数 `error` 为 `nil` 。如果问题阻止播发数据，则参数 `error` 将返回失败的原因。
