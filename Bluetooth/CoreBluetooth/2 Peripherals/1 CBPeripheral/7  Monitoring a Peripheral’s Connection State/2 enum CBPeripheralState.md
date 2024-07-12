Enumeration 列举

# CBPeripheralState

Values representing the connection state of a peripheral.
表示外围设备连接状态的值。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
enum CBPeripheralState
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#topics)

### [Peripheral States 外围状态](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#Peripheral-States)

#### [`case disconnected`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate/disconnected)

The peripheral isn’t connected to the central manager.
外围设备未连接到中央管理器。



#### [`case connecting`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate/connecting)

The peripheral is in the process of connecting to the central manager.
外围设备正在连接到中央管理器。



#### [`case connected`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate/connected)

The peripheral is connected to the central manager.
外围设备连接到中央管理器。



#### [`case disconnecting`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate/disconnecting)

The peripheral is disconnecting from the central manager.
外围设备与中央管理器断开连接。



### [Initializers 初始值设定项](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#Default-Implementations)

#### Equatable Implementations

等式实现



#### RawRepresentable Implementations

RawRepresentable 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#see-also)

### [Monitoring a Peripheral’s Connection State 监视外设的连接状态](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate#Monitoring-a-Peripherals-Connection-State)

[`var state: CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/state)

The connection state of the peripheral.
外围设备的连接状态。

[`var canSendWriteWithoutResponse: Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/cansendwritewithoutresponse)

A Boolean value that indicates whether the remote device can send a write without a response.
一个 Boolean 值，该值指示远程设备是否可以在没有响应的情况下发送写入。