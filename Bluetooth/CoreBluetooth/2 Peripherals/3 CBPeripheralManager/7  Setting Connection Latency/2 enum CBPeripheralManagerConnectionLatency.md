Enumeration 列举

# CBPeripheralManagerConnectionLatency

Values representing the connection latency of the peripheral manager.
表示外设管理器的连接延迟的值。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
enum CBPeripheralManagerConnectionLatency
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#topics)

### [Latency Values 延迟值](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#Latency-Values)

#### [`case low`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency/low)

A latency setting indicating that prioritizes rapid communication over battery life.
一种延迟设置，指示快速通信优先于电池续航时间。



#### [`case medium`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency/medium)

A latency setting that balances communication frequency and battery life.
一种平衡通信频率和电池续航时间的延迟设置。



#### [`case high`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency/high)

A latency setting that prioritizes extending battery life over rapid communication.
一种延迟设置，优先考虑延长电池续航时间而不是快速通信。



### [Initializers 初始值设定项](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#Default-Implementations)

#### Equatable Implementations

等式实现



#### RawRepresentable Implementations

RawRepresentable 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#see-also)

### [Setting Connection Latency 设置连接延迟](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency#Setting-Connection-Latency)

[`func setDesiredConnectionLatency(CBPeripheralManagerConnectionLatency, for: CBCentral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/setdesiredconnectionlatency(_:for:))

Sets the desired connection latency for an existing connection to a central device.
为与中央设备的现有连接设置所需的连接延迟。
