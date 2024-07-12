Instance Method Instance 方法

# peripheralManager(_:didAdd:error:) 

Tells the delegate the peripheral manager published a service to the local GATT database.
告知委托外围设备管理器向本地 GATT 数据库发布了服务。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ 

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    didAdd service: CBService,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didadd:error:)#parameters)

- `peripheral`

  The peripheral manager adding the service. 

  添加服务的外围设备管理器。

- `service`

  The service added to the local GATT database. 

  该服务已添加到本地 GATT 数据库。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didadd:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`add(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)) method to publish a service to the local peripheral’s GATT database. If the service published successfully to the local database, the `error` parameter is `nil`. If unsuccessful, the `error` parameter provides the cause of the failure.
当应用调用该 `add(_:)` 方法以将服务发布到本地外围设备的 GATT 数据库时，核心蓝牙会调用此方法。如果服务成功发布到本地数据库，则参数 `error` 为 `nil` 。如果不成功，则参数 `error` 提供失败的原因。
