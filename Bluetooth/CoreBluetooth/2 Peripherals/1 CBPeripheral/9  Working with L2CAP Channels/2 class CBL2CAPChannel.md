Class 类

# CBL2CAPChannel 

A live L2CAP connection to a remote device.
与远程设备的实时 L2CAP 连接。

iOS 11.0+ iOS的11.0 +iPadOS 11.0+ iPadOS 11.0+ 操作系统Mac Catalyst 13.1+macOS 10.13+tvOS 11.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
class CBL2CAPChannel
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#topics)

### [Accessing Streams 访问流](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#Accessing-Streams)

#### [`var inputStream: InputStream!`](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel/inputstream)

The stream used for reading data from the remote peer.
用于从远程对等体读取数据的流。



#### [`var outputStream: OutputStream!`](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel/outputstream)

The stream used for writing data to the peer.
用于将数据写入对等体的流。



### [Accessing the Peer 访问对等节点](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#Accessing-the-Peer)

#### [`var peer: CBPeer!`](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel/peer)

The peer connected to the channel.
连接到通道的对等体。



### [Accessing the Protocol/Service Multiplexer 访问协议/业务多路复用器](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#Accessing-the-ProtocolService-Multiplexer)

#### [`var psm: CBL2CAPPSM`](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel/psm)

The PSM of the channel.
通道的 PSM。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#inherits-from)

- #### [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)

  

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#see-also)

### [Working with L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel#Working-with-L2CAP-Channels)

[`func openL2CAPChannel(CBL2CAPPSM)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/openl2capchannel(_:))

Attempts to open an L2CAP channel to the peripheral using the supplied Protocol/Service Multiplexer (PSM).
尝试使用随附的协议/服务多路复用器 （PSM） 打开通往外设的 L2CAP 通道。

[`typealias CBL2CAPPSM`](https://developer.apple.com/documentation/corebluetooth/cbl2cappsm)

The type of PSM identifiers.
PSM 标识符的类型。