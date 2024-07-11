Initializer 初始 化

# init(delegate:queue:options:) 

Initializes the peripheral manager with a specified delegate, dispatch queue, and initialization options.
使用指定的委托、调度队列和初始化选项初始化外设管理器。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+

```
init(
    delegate: (any CBPeripheralManagerDelegate)?,
    queue: dispatch_queue_t?,
    options: [String : Any]? = nil
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:)#parameters)

- `delegate`

  The delegate to receive the peripheral role events. 

  接收外围角色事件的委托。

- `queue`

  The dispatch queue for dispatching the peripheral role events. If the value is `nil`, the peripheral manager dispatches peripheral role events using the main queue. 

  用于调度外围角色事件的调度队列。如果值为 `nil` ，则外设管理器使用主队列调度外设角色事件。

- `options`

  An optional dictionary containing initialization options for a peripheral manager. For available options, see [Peripheral Manager Initialization Options](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-initialization-options). 

  包含外设管理器初始化选项的可选字典。有关可用选项，请参阅外设管理器初始化选项。

  

## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:)#return-value)

Returns a newly initialized peripheral manager.
返回新初始化的外设管理器。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:)#Discussion)

This method is the designated initializer for the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class.
此方法是 `CBPeripheralManager` 类的指定初始值设定项。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:)#see-also)

### [Initializing a Peripheral Manager 初始化外设管理器](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:)#Initializing-a-Peripheral-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init())

Initializes the peripheral manager without a delegate.
在没有委托的情况下初始化外设管理器。

[`convenience init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:))

Initializes the peripheral manager with a specified delegate and dispatch queue.
使用指定的委托和调度队列初始化外设管理器。

[`var delegate: (any CBPeripheralManagerDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate)

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。



Peripheral Manager Initialization Options
外设管理器初始化选项

Keys used to specify options when creating a peripheral manager.
用于在创建外设管理器时指定选项的键。
