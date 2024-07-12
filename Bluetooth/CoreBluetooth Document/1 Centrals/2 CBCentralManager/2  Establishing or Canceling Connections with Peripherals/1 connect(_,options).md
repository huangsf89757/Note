Instance Method Instance 方法

# connect(_:options:) 

Establishes a local connection to a peripheral.
建立与外围设备的本地连接。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ ｜ 

```
func connect(
    _ peripheral: CBPeripheral,
    options: [String : Any]? = nil
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)#parameters)

- `peripheral`

  The peripheral to which the central is attempting to connect. 中央试图连接的外围设备。

- `options`

  A dictionary to customize the behavior of the connection. For available options, see [Peripheral Connection Options](https://developer.apple.com/documentation/corebluetooth/peripheral-connection-options). 用于自定义连接行为的字典。有关可用选项，请参阅外围设备连接选项。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)#Discussion)

After successfully establishing a local connection to a peripheral, the central manager object calls the [`centralManager(_:didConnect:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:)) method of its delegate object. If the connection attempt fails, the central manager object calls the [`centralManager(_:didFailToConnect:error:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:)) method of its delegate object instead. Attempts to connect to a peripheral don’t time out. To explicitly cancel a pending connection to a peripheral, call the [`cancelPeripheralConnection(_:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)) method. Deallocating `peripheral` also implicitly calls [`cancelPeripheralConnection(_:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:)).
成功建立与外围设备的本地连接后，中央管理器对象将调用其委托对象 `centralManager(_:didConnect:)` 的方法。如果连接尝试失败，则中央管理器对象将改为调用其委托对象 `centralManager(_:didFailToConnect:error:)` 的方法。尝试连接到外围设备不会超时。若要显式取消与外围设备的挂起连接，请调用该 `cancelPeripheralConnection(_:)` 方法。解除分配 `peripheral` 也隐式调用 `cancelPeripheralConnection(_:)` .



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)#see-also)

### [Establishing or Canceling Connections with Peripherals 建立或取消与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)#Establishing-or-Canceling-Connections-with-Peripherals)



Peripheral Connection Options
外设连接选项

Keys used to pass options when connecting to a peripheral.
用于在连接到外围设备时传递选项的键。

[`func cancelPeripheralConnection(CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:))

Cancels an active or pending local connection to a peripheral.
取消与外围设备的活动或挂起的本地连接。
