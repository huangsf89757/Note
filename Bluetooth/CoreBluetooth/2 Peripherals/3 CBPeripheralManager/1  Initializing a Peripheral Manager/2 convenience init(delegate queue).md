Initializer 初始 化

# init(delegate:queue:) 

Initializes the peripheral manager with a specified delegate and dispatch queue.
使用指定的委托和调度队列初始化外设管理器。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ 

```
convenience init(
    delegate: (any CBPeripheralManagerDelegate)?,
    queue: dispatch_queue_t?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:)#parameters)

- `delegate`

  The delegate to receive the peripheral role events. 

  接收外围角色事件的委托。

- `queue`

  The dispatch queue for dispatching the peripheral role events. If the value is `nil`, the peripheral manager dispatches peripheral role events using the main queue. 

  用于调度外围角色事件的调度队列。如果值为 `nil` ，则外设管理器使用主队列调度外设角色事件。

  

## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:)#return-value)

Returns a newly initialized peripheral manager.
返回新初始化的外设管理器。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:)#discussion)

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅核心蓝牙编程指南。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:)#see-also)

### [Initializing a Peripheral Manager 初始化外设管理器](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:)#Initializing-a-Peripheral-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init())

Initializes the peripheral manager without a delegate.
在没有委托的情况下初始化外设管理器。

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
