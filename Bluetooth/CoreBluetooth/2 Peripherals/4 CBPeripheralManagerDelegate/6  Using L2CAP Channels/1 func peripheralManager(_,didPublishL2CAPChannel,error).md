Instance Method Instance 方法

# peripheralManager(_:didPublishL2CAPChannel:error:) 

Tells the delegate that the peripheral manager created a listener for incoming L2CAP channel connections.
告知委托外围设备管理器为传入的 L2CAP 通道连接创建了一个侦听器。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    didPublishL2CAPChannel PSM: CBL2CAPPSM,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:)#parameters)

- `peripheral`

  The peripheral manager that published the channel. 

  发布频道的外围管理器。

- `PSM`

  The Protocol/Service Multiplexer (PSM) of the published channel. 

  已发布通道的协议/业务多路复用器 （PSM）。

- `error`

  The error that prevented publishing, or `nil` if no error occurred. 

  阻止发布的错误，或者 `nil` 如果未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:)#Discussion)

The peripheral manager calls this method after you call [`publishL2CAPChannel(withEncryption:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:)). The `PSM` parameter contains the PSM assigned for the published channel.
外设管理器在您调用 `publishL2CAPChannel(withEncryption:)` 后调用此方法。该 `PSM` 参数包含为已发布通道分配的 PSM。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:)#see-also)

### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:)#Using-L2CAP-Channels)

[`func peripheralManager(CBPeripheralManager, didUnpublishL2CAPChannel: CBL2CAPPSM, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:))

Tells the delegate that the peripheral manager removed a published service from the local system.
告知代理外围设备管理器从本地系统中删除了已发布的服务。

[`func peripheralManager(CBPeripheralManager, didOpen: CBL2CAPChannel?, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:))

Tells the delegate that the peripheral manager opened an L2CAP channel.
告知委托外围设备管理器打开了 L2CAP 通道。
