Instance Property 实例属性

# identifier 标识符

The UUID associated with the peer.
与对等方关联的UUID。

iOS 7.0+iPadOS 7.0+Mac Catalyst 13.1+macOS 10.13+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var identifier: UUID { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbpeer/identifier#Discussion)

The value of this property represents the unique identifier of the peer. The first time a local manager encounters a peer, the system assigns the peer a UUID, represented by a new [`UUID`](https://developer.apple.com/documentation/foundation/uuid) object. Peers use [`UUID`](https://developer.apple.com/documentation/foundation/uuid) instances to identify themselves, instead of by the [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects that identify a peripheral’s services, characteristics, and descriptors.
此属性的值表示对等方的唯一标识符。本地管理器第一次遇到对等体时，系统会为对等体分配一个UUID，由一个新的 `UUID` 对象表示。对等体使用 `UUID` 实例来标识自己，而不是使用 `CBUUID` 对象来标识外围设备的服务、特征和描述符。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅Core Bluetooth Programming Guide。
