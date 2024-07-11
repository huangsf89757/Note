Instance Method Instance 方法

# centralManager(_:didConnect:) 

Tells the delegate that the central manager connected to a peripheral.
告知委托中央管理器已连接到外围设备。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func centralManager(
    _ central: CBCentralManager,
    didConnect peripheral: CBPeripheral
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:)#parameters)

- `central`

  The central manager that provides this information. 提供此信息的中央管理器。

- `peripheral`

  The now-connected peripheral. 现在连接的外围设备。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:)#Discussion)

The manager invokes this method when a call to [`connect(_:options:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)) succeeds. You typically implement this method to set the peripheral’s delegate and discover its services.
当调用 `connect(_:options:)` 成功时，管理器调用此方法。通常实现此方法以设置外围设备的委托并发现其服务。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅核心蓝牙编程指南。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:)#see-also)

### [Monitoring Connections with Peripherals 监视与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:)#Monitoring-Connections-with-Peripherals)

[`func centralManager(CBCentralManager, didDisconnectPeripheral: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:))

Tells the delegate that the central manager disconnected from a peripheral.
告知委托中央管理器已断开与外围设备的连接。

**Required 必填**

[`func centralManager(CBCentralManager, didFailToConnect: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:))

Tells the delegate the central manager failed to create a connection with a peripheral.
告知代理中央管理器未能与外围设备建立连接。

[`func centralManager(CBCentralManager, connectionEventDidOccur: CBConnectionEvent, for: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:))

Tells the delegate that a connection event occurred which matches the registered options.
告知委托发生了与已注册选项匹配的连接事件。

**Required 必填**
