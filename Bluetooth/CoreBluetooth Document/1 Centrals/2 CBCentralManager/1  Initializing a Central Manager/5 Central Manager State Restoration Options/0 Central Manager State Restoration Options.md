API Collection API 集合

# Central Manager State Restoration Options 

Keys used to pass state restoration options to the central manager initializer.
用于将状态还原选项传递给中央管理器初始值设定项的密钥。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/central-manager-state-restoration-options#topics)

### [State Restoration Options 状态恢复选项](https://developer.apple.com/documentation/corebluetooth/central-manager-state-restoration-options#State-Restoration-Options)

#### [`let CBCentralManagerRestoredStatePeripheralsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstateperipheralskey)

An array of peripherals for use when restoring the state of a central manager.
用于恢复中央管理器状态的外围设备阵列。



#### [`let CBCentralManagerRestoredStateScanServicesKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanserviceskey)

An array of service IDs for use when restoring state.
还原状态时使用的服务 ID 数组。



#### [`let CBCentralManagerRestoredStateScanOptionsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanoptionskey)

A dictionary of peripheral scan options for use when restoring state.
用于恢复状态的外围设备扫描选项的字典。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/central-manager-state-restoration-options#see-also)

### [Initializing a Central Manager 初始化中央管理器](https://developer.apple.com/documentation/corebluetooth/central-manager-state-restoration-options#Initializing-a-Central-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init())

Initializes the central manager without a delegate.
在没有委托的情况下初始化中央管理器。

[`convenience init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:))

Initializes the central manager with a specified delegate and dispatch queue.
使用指定的委派和调度队列初始化中央管理器。

[`init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:options:))

Initializes the central manager with specified delegate, dispatch queue, and initialization options.
使用指定的委托、调度队列和初始化选项初始化中央管理器。



Central Manager Initialization Options
Central Manager 初始化选项

Keys used to pass options when initializing a central manager.
用于在初始化中央管理器时传递选项的键。
