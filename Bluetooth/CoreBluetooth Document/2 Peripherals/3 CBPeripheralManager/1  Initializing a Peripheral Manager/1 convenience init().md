Initializer 初始 化

# init() 

Initializes the peripheral manager without a delegate.
在没有委托的情况下初始化外设管理器。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
convenience init()
```



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init()#see-also)

### [Initializing a Peripheral Manager 初始化外设管理器](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init()#Initializing-a-Peripheral-Manager)

[`convenience init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:))

Initializes the peripheral manager with a specified delegate and dispatch queue.
使用指定的委托和调度队列初始化外设管理器。

[`init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:))

Initializes the peripheral manager with a specified delegate, dispatch queue, and initialization options.
使用指定的委托、调度队列和初始化选项初始化外设管理器。

[`var delegate: (any CBPeripheralManagerDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate)

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。



Peripheral Manager Initialization Options
外设管理器初始化选项

Keys used to specify options when creating a peripheral manager.
用于在创建外设管理器时指定选项的键。
