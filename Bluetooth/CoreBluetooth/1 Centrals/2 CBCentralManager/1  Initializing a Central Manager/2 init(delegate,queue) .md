Initializer

# init(delegate:queue:) 

Initializes the central manager with a specified delegate and dispatch queue.
使用指定的委托和分派队列对中央管理器进行初始化。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
convenience init(
    delegate: (any CBCentralManagerDelegate)?,
    queue: dispatch_queue_t?
)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:)#parameters)

- `delegate`

  The delegate that receives central events. 接收中心事件的委托。

- `queue`

  The dispatch queue used to dispatch the central role events. If the value is `nil`, the central manager dispatches central role events using the main queue. 用于分派中心角色事件的分派队列。如果值为 `nil` ，则中央管理器使用主队列分派中央角色事件。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:)#return-value)

Returns a newly initialized central manager.
返回新初始化的中央管理器。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:)#discussion)

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅Core Bluetooth Programming Guide。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:)#see-also)

### [Initializing a Central Manager 初始化中央管理器](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:)#Initializing-a-Central-Manager)

[`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init())

Initializes the central manager without a delegate.
在没有委派的情况下访问中央管理器。

[`init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:options:))

Initializes the central manager with specified delegate, dispatch queue, and initialization options.
使用指定的委托、分派队列和初始化选项重新配置中央管理器。



Central Manager Initialization Options
中央管理器选项

Keys used to pass options when initializing a central manager.
初始化中央管理器时用于传递选项的键。



Central Manager State Restoration Options
中央管理器状态恢复选项

Keys used to pass state restoration options to the central manager initializer.
用于将状态恢复选项传递给中央管理器初始化程序的键。
