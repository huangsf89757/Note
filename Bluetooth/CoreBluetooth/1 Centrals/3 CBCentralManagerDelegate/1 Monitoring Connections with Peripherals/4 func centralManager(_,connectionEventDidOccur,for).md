Instance Method Instance 方法

# centralManager(_:connectionEventDidOccur:for:) 

Tells the delegate that a connection event occurred which matches the registered options.
告知委托发生了与已注册选项匹配的连接事件。

iOS 13.0+ iOS的 13.0+iPadOS 13.0+Mac Catalyst 13.1+tvOS 13.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 6.0+ watchOS 6.0+ 操作系统

```
optional func centralManager(
    _ central: CBCentralManager,
    connectionEventDidOccur event: CBConnectionEvent,
    for peripheral: CBPeripheral
)
```

**Required 必填**



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:)#Discussion)

The manager calls this method when it observes a connection event that matches the options provided to [`registerForConnectionEvents(options:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:)).
当管理器观察到与提供给 的 `registerForConnectionEvents(options:)` 选项匹配的连接事件时，将调用此方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:)#see-also)

### [Monitoring Connections with Peripherals 监视与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:)#Monitoring-Connections-with-Peripherals)

[`func centralManager(CBCentralManager, didConnect: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:))

Tells the delegate that the central manager connected to a peripheral.
告知委托中央管理器已连接到外围设备。

[`func centralManager(CBCentralManager, didDisconnectPeripheral: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:))

Tells the delegate that the central manager disconnected from a peripheral.
告知委托中央管理器已断开与外围设备的连接。

**Required 必填**

[`func centralManager(CBCentralManager, didFailToConnect: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:))

Tells the delegate the central manager failed to create a connection with a peripheral.
告知代理中央管理器未能与外围设备建立连接。
