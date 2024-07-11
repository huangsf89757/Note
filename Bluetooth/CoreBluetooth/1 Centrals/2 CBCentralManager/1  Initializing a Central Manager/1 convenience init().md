Initializer

# init() 

Initializes the central manager without a delegate.
在没有委派的情况下访问中央管理器。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
convenience init()
```



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init()#see-also)

### [Initializing a Central Manager 初始化中央管理器](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init()#Initializing-a-Central-Manager)

[`convenience init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:))

Initializes the central manager with a specified delegate and dispatch queue.
使用指定的委托和分派队列对中央管理器进行初始化。

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
