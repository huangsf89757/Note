Instance Method Instance 方法

# cancelPeripheralConnection(_:) 

Cancels an active or pending local connection to a peripheral.
取消与外围设备的活动或挂起的本地连接。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func cancelPeripheralConnection(_ peripheral: CBPeripheral)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)#parameters)

- `peripheral`

  The peripheral to which the central manager is either trying to connect or has already connected. 中央管理器正在尝试连接或已连接的外围设备。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)#Discussion)

This method is nonblocking, and any [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class commands that are still pending to `peripheral` may not complete. Because other apps may still have a connection to the peripheral, canceling a local connection doesn’t guarantee that the underlying physical link is immediately disconnected. From the app’s perspective, however, the peripheral is effectively disconnected, and the central manager object calls the [`centralManager(_:didDisconnectPeripheral:error:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:)) method of its delegate object.
此方法是非阻塞的，任何仍处于待处理状态 `peripheral` 的 `CBPeripheral` 类命令可能无法完成。由于其他应用可能仍与外围设备有连接，因此取消本地连接并不能保证基础物理链接会立即断开连接。但是，从应用的角度来看，外围设备实际上是断开连接的，中央管理器对象调用其委托对象 `centralManager(_:didDisconnectPeripheral:error:)` 的方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)#see-also)

### [Establishing or Canceling Connections with Peripherals 建立或取消与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)#Establishing-or-Canceling-Connections-with-Peripherals)

[`func connect(CBPeripheral, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:))

Establishes a local connection to a peripheral.
建立与外围设备的本地连接。



Peripheral Connection Options
外设连接选项

Keys used to pass options when connecting to a peripheral.
用于在连接到外围设备时传递选项的键。
