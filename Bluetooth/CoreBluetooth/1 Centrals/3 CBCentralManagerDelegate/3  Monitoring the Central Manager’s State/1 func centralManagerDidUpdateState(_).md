Instance Method Instance 方法

# centralManagerDidUpdateState(_:) 

Tells the delegate the central manager’s state updated.
告知委托中央经理的状态已更新。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func centralManagerDidUpdateState(_ central: CBCentralManager)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)#parameters)

- `central`

  The central manager whose state has changed. 状态已更改的中央管理器。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)#Discussion)

You implement this required method to ensure that the central device supports Bluetooth low energy and that it’s available to use. You should issue commands to the central manager only when the central manager’s [`state`](https://developer.apple.com/documentation/corebluetooth/cbmanager/state) indicates it’s powered on. A state with a value lower than [`CBManagerState.poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/poweredon) implies that scanning has stopped, which in turn disconnects any previously-connected peripherals. If the state moves below [`CBManagerState.poweredOff`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/poweredoff), all [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) objects obtained from this central manager become invalid; you must retrieve or discover these peripherals again. For a complete list of possible states, see [`CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate).
您可以实现此必需方法，以确保中央设备支持低功耗蓝牙，并且可以使用。仅当中央管理器 `state` 指示其已打开电源时，才应向中央管理器发出命令。值小于 `CBManagerState.poweredOn` 的状态表示扫描已停止，这反过来又会断开任何以前连接的外围设备。如果状态低于 `CBManagerState.poweredOff` ，则从该中央管理器获取的所有 `CBPeripheral` 对象都将无效;您必须再次检索或发现这些外围设备。有关可能状态的完整列表，请参见 `CBManagerState` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)#see-also)

### [Monitoring the Central Manager’s State 监视中央管理器的状态](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)#Monitoring-the-Central-Managers-State)

[`func centralManager(CBCentralManager, willRestoreState: [String : Any\])`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:willrestorestate:))

Tells the delegate the system is about to restore the central manager, as part of relaunching the app into the background.
告知委托系统即将还原中央管理器，作为将应用程序重新启动到后台的一部分。
