Instance Method Instance 方法

# peripheralManager(_:didOpen:error:) 

Tells the delegate that the peripheral manager opened an L2CAP channel.
告知委托外围设备管理器打开了 L2CAP 通道。

iOS 11.0+ ｜ iPadOS 11.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 11.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    didOpen channel: CBL2CAPChannel?,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:)#parameters)

- `peripheral`

  The peripheral manager that opened the channel. 

  打开通道的外围管理器。

- `channel`

  The channel opened by the manager. 

  经理打开的频道。

- `error`

  The error that occurred, or `nil` if no error occurred. 

  发生的错误，或者 `nil` 如果未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:)#Discussion)

The peripheral manager calls this method after you call [`publishL2CAPChannel(withEncryption:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:)).
外设管理器在您调用 `publishL2CAPChannel(withEncryption:)` 后调用此方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:)#see-also)

### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:)#Using-L2CAP-Channels)

[`func peripheralManager(CBPeripheralManager, didPublishL2CAPChannel: CBL2CAPPSM, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:))

Tells the delegate that the peripheral manager created a listener for incoming L2CAP channel connections.
告知委托外围设备管理器为传入的 L2CAP 通道连接创建了一个侦听器。

[`func peripheralManager(CBPeripheralManager, didUnpublishL2CAPChannel: CBL2CAPPSM, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:))

Tells the delegate that the peripheral manager removed a published service from the local system.
告知代理外围设备管理器从本地系统中删除了已发布的服务。
