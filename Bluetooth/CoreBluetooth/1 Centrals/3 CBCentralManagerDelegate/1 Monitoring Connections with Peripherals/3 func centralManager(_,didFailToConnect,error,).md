Instance Method Instance 方法

# centralManager(_:didFailToConnect:error:) 

Tells the delegate the central manager failed to create a connection with a peripheral.
告知代理中央管理器未能与外围设备建立连接。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func centralManager(
    _ central: CBCentralManager,
    didFailToConnect peripheral: CBPeripheral,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:)#parameters)

- `central`

  The central manager that provides this information. 提供此信息的中央管理器。

- `peripheral`

  The peripheral that failed to connect. 连接失败的外围设备。

- `error`

  The cause of the failure, or `nil` if no error occurred. 失败的原因，或者 `nil` 是否未发生错误。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:)#Discussion)

The manager invokes this method when a connection initiated with the [`connect(_:options:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)) method fails to complete. Because connection attempts don’t time out, a failed connection usually indicates a transient issue, in which case you may attempt connecting to the peripheral again.
当使用该 `connect(_:options:)` 方法启动的连接无法完成时，管理器将调用此方法。由于连接尝试不会超时，因此连接失败通常表示暂时性问题，在这种情况下，您可以尝试再次连接到外围设备。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:)#see-also)

### [Monitoring Connections with Peripherals 监视与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:)#Monitoring-Connections-with-Peripherals)

[`func centralManager(CBCentralManager, didConnect: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:))

Tells the delegate that the central manager connected to a peripheral.
告知委托中央管理器已连接到外围设备。

[`func centralManager(CBCentralManager, didDisconnectPeripheral: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:))

Tells the delegate that the central manager disconnected from a peripheral.
告知委托中央管理器已断开与外围设备的连接。

**Required 必填**

[`func centralManager(CBCentralManager, connectionEventDidOccur: CBConnectionEvent, for: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:))

Tells the delegate that a connection event occurred which matches the registered options.
告知委托发生了与已注册选项匹配的连接事件。

**Required 必填**
