API Collection API 集合

# Peripheral Manager Initialization Options 

Keys used to specify options when creating a peripheral manager.
用于在创建外设管理器时指定选项的键。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-initialization-options#topics)

### [Initialization Options 初始化选项](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-initialization-options#Initialization-Options)

#### [`let CBPeripheralManagerOptionShowPowerAlertKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionshowpoweralertkey)

A Boolean value specifying whether the system should warn if Bluetooth is in the powered-off state when instantiating the peripheral manager.
一个 Boolean 值，该值指定在实例化外围设备管理器时，如果蓝牙处于关机状态，系统是否应发出警告。



#### [`let CBPeripheralManagerOptionRestoreIdentifierKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionrestoreidentifierkey)

A unique identifier (UID) with which to instantiate the peripheral manager.
用于实例化外设管理器的唯一标识符 （UID）。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-initialization-options#see-also)

### [Initializing a Peripheral Manager 初始化外设管理器](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-initialization-options#Initializing-a-Peripheral-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init())

Initializes the peripheral manager without a delegate.
在没有委托的情况下初始化外设管理器。

[`convenience init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:))

Initializes the peripheral manager with a specified delegate and dispatch queue.
使用指定的委托和调度队列初始化外设管理器。

[`init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:))

Initializes the peripheral manager with a specified delegate, dispatch queue, and initialization options.
使用指定的委托、调度队列和初始化选项初始化外设管理器。

[`var delegate: (any CBPeripheralManagerDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate)

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。
