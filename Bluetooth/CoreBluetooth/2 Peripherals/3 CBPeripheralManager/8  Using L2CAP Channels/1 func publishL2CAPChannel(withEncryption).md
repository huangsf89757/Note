Instance Method Instance 方法

# publishL2CAPChannel(withEncryption:) 

Creates a listener for incoming L2CAP channel connections.
为传入的 L2CAP 通道连接创建侦听器。

iOS 11.0+ iOS的11.0 +iPadOS 11.0+ iPadOS 11.0+ 操作系统Mac Catalyst 13.1+macOS 10.14+tvOS 11.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
func publishL2CAPChannel(withEncryption encryptionRequired: Bool)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:)#parameters)

- `encryptionRequired`

  [`true`](https://developer.apple.com/documentation/swift/true) if the service requires link encryption before a stream can be established. [`false`](https://developer.apple.com/documentation/swift/false) if the service supports use over an unsecured link. 

  `true` 如果服务需要在建立流之前进行链路加密。 `false` 如果服务支持通过不安全的链接使用。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:)#Discussion)

The system determines an unused Protocol and Service Multiplexer (PSM) at the time of publishing, and provides it to your app with [`peripheralManager(_:didPublishL2CAPChannel:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:)). L2CAP channels aren’t discoverable by themselves, so it’s the app’s responsibility to handle PSM discovery on the client.
系统在发布时确定未使用的协议和服务多路复用器 （PSM），并将其提供给应用 `peripheralManager(_:didPublishL2CAPChannel:error:)` 。L2CAP 通道本身不可发现，因此应用负责在客户端上处理 PSM 发现。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:)#see-also)

### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:)#Using-L2CAP-Channels)

[`func unpublishL2CAPChannel(CBL2CAPPSM)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:))

Removes a published service from the local system.
从本地系统中删除已发布的服务。
