Instance Method Instance 方法

# centralManager(_:didDisconnectPeripheral:error:) 

Tells the delegate that the central manager disconnected from a peripheral.
告知委托中央管理器已断开与外围设备的连接。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func centralManager(
    _ central: CBCentralManager,
    didDisconnectPeripheral peripheral: CBPeripheral,
    error: (any Error)?
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:)#parameters)

- `central`

  The central manager that provides this information. 提供此信息的中央管理器。

- `peripheral`

  The now-disconnected peripheral. 现已断开连接的外围设备。

- `error`

  The cause of the failure, or `nil` if no error occurred. 失败的原因，或者 `nil` 是否未发生错误。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:)#Discussion)

The manager invokes this method when disconnecting a peripheral previously connected with the [`connect(_:options:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)) method. The error parameter contains the reason for the disconnection, unless the disconnect resulted from a call to [`cancelPeripheralConnection(_:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)). After this method executes, the peripheral device’s [`CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate) object receives no further method calls.
当断开以前与该方法连接的 `connect(_:options:)` 外围设备时，管理器将调用此方法。error 参数包含断开连接的原因，除非断开连接是由调用 `cancelPeripheralConnection(_:)` .执行此方法后，外围设备的 `CBPeripheralDelegate` 对象不会收到进一步的方法调用。

All services, characteristics, and characteristic descriptors a peripheral become invalidated after it disconnects.
外围设备断开连接后，所有服务、特征和特征描述符都将失效。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:)#see-also)

### [Monitoring Connections with Peripherals 监视与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:)#Monitoring-Connections-with-Peripherals)

[`func centralManager(CBCentralManager, didConnect: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:))

Tells the delegate that the central manager connected to a peripheral.
告知委托中央管理器已连接到外围设备。

[`func centralManager(CBCentralManager, didFailToConnect: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:))

Tells the delegate the central manager failed to create a connection with a peripheral.
告知代理中央管理器未能与外围设备建立连接。

[`func centralManager(CBCentralManager, connectionEventDidOccur: CBConnectionEvent, for: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:))

Tells the delegate that a connection event occurred which matches the registered options.
告知委托发生了与已注册选项匹配的连接事件。

**Required 必填**
