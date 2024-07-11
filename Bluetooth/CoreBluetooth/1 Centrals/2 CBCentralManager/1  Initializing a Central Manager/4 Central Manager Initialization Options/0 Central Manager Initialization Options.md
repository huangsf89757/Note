API Collection API集合

# Central Manager Initialization Options 中央管理器选项

Keys used to pass options when initializing a central manager.
初始化中央管理器时用于传递选项的键。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/central-manager-initialization-options#topics)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/central-manager-initialization-options#Constants)

#### [`let CBCentralManagerOptionShowPowerAlertKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionshowpoweralertkey)

A Boolean value that specifies whether the system warns the user if the app instantiates the central manager when Bluetooth service isn’t available.
一个布尔值，指定当蓝牙服务不可用时，如果应用实例化中央管理器，系统是否警告用户。



#### [`let CBCentralManagerOptionRestoreIdentifierKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionrestoreidentifierkey)

A string containing a unique identifier (UID) for the central manager to instantiate.
一个字符串，包含中央管理器要实例化的唯一标识符（UID）。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/central-manager-initialization-options#see-also)

### [Initializing a Central Manager 初始化中央管理器](https://developer.apple.com/documentation/corebluetooth/central-manager-initialization-options#Initializing-a-Central-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init())

Initializes the central manager without a delegate.
在没有委派的情况下访问中央管理器。

[`convenience init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:))

Initializes the central manager with a specified delegate and dispatch queue.
使用指定的委托和分派队列对中央管理器进行初始化。

[`init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:options:))

Initializes the central manager with specified delegate, dispatch queue, and initialization options.
使用指定的委托、分派队列和初始化选项重新配置中央管理器。



Central Manager State Restoration Options
中央管理器状态恢复选项

Keys used to pass state restoration options to the central manager initializer.
用于将状态恢复选项传递给中央管理器初始化程序的键。
