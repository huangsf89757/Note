Instance Method Instance 方法

# unpublishL2CAPChannel(_:) 

Removes a published service from the local system.
从本地系统中删除已发布的服务。

iOS 11.0+ iOS的11.0 +iPadOS 11.0+ iPadOS 11.0+ 操作系统Mac Catalyst 13.1+macOS 10.14+tvOS 11.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
func unpublishL2CAPChannel(_ PSM: CBL2CAPPSM)
```

## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:)#parameters)

- `PSM`

  The Protocol and Service Multiplexer (PSM) to remove from the system. 
  
  要从系统中删除的协议和服务多路复用器 （PSM）。
  
  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:)#Discussion)

After you make this call, the peripheral manager accepts no new connections for this PSM, and closes any existing L2CAP channels using this PSM.
进行此调用后，外设管理器不接受此 PSM 的新连接，并使用此 PSM 关闭任何现有的 L2CAP 通道。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:)#see-also)

### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:)#Using-L2CAP-Channels)

[`func publishL2CAPChannel(withEncryption: Bool)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:))

Creates a listener for incoming L2CAP channel connections.
为传入的 L2CAP 通道连接创建侦听器。
