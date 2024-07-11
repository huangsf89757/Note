Instance Method Instance 方法

# openL2CAPChannel(_:) 

Attempts to open an L2CAP channel to the peripheral using the supplied Protocol/Service Multiplexer (PSM).
尝试使用随附的协议/服务多路复用器 （PSM） 打开通往外设的 L2CAP 通道。

iOS 11.0+ iOS的11.0 +iPadOS 11.0+ iPadOS 11.0+ 操作系统Mac Catalyst 13.1+macOS 10.14+tvOS 11.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
func openL2CAPChannel(_ PSM: CBL2CAPPSM)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/openl2capchannel(_:)#parameters)

- `PSM`

  The PSM of the channel to open. 要打开的通道的 PSM。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/openl2capchannel(_:)#see-also)

### [Working with L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheral/openl2capchannel(_:)#Working-with-L2CAP-Channels)

[`class CBL2CAPChannel`](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel)

A live L2CAP connection to a remote device.
与远程设备的实时 L2CAP 连接。

[`typealias CBL2CAPPSM`](https://developer.apple.com/documentation/corebluetooth/cbl2cappsm)

The type of PSM identifiers.
PSM 标识符的类型。
