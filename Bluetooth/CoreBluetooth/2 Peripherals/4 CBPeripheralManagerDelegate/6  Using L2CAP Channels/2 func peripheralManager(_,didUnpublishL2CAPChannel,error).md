Instance Method Instance 方法

# peripheralManager(_:didUnpublishL2CAPChannel:error:) 

Tells the delegate that the peripheral manager removed a published service from the local system.
告知代理外围设备管理器从本地系统中删除了已发布的服务。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    didUnpublishL2CAPChannel PSM: CBL2CAPPSM,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:)#parameters)

- `peripheral`

  The peripheral manager that stopped publishing. 

  停止发布的外围管理器。

- `PSM`

  The Protocol/Service Multiplexer (PSM) of the channel that was unpublished. 

  未发布的通道的协议/服务多路复用器 （PSM）。

- `error`

  The error that occurred, or `nil` if no error occurred. 

  发生的错误，或者 `nil` 如果未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:)#Discussion)

The peripheral manager calls this method after you call [`unpublishL2CAPChannel(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:)).
外设管理器在您调用 `unpublishL2CAPChannel(_:)` 后调用此方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:)#see-also)

### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:)#Using-L2CAP-Channels)

[`func peripheralManager(CBPeripheralManager, didPublishL2CAPChannel: CBL2CAPPSM, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:))

Tells the delegate that the peripheral manager created a listener for incoming L2CAP channel connections.
告知委托外围设备管理器为传入的 L2CAP 通道连接创建了一个侦听器。

[`func peripheralManager(CBPeripheralManager, didOpen: CBL2CAPChannel?, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:))

Tells the delegate that the peripheral manager opened an L2CAP channel.
告知委托外围设备管理器打开了 L2CAP 通道。
