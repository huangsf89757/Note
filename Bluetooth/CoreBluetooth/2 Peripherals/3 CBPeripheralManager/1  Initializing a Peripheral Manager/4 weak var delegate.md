Instance Property Instance 属性

# delegate 委托

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
weak var delegate: (any CBPeripheralManagerDelegate)? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate#Discussion)

For information about how to implement your peripheral manager delegate, see [`CBPeripheralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate).
有关如何实现外设管理器委托的信息，请参见 `CBPeripheralManagerDelegate` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate#see-also)

### [Initializing a Peripheral Manager 初始化外设管理器](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate#Initializing-a-Peripheral-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init())

Initializes the peripheral manager without a delegate.
在没有委托的情况下初始化外设管理器。

[`convenience init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:))

Initializes the peripheral manager with a specified delegate and dispatch queue.
使用指定的委托和调度队列初始化外设管理器。

[`init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:))

Initializes the peripheral manager with a specified delegate, dispatch queue, and initialization options.
使用指定的委托、调度队列和初始化选项初始化外设管理器。



Peripheral Manager Initialization Options
外设管理器初始化选项

Keys used to specify options when creating a peripheral manager.
用于在创建外设管理器时指定选项的键。
