Instance Method Instance 方法

# peripheralManagerDidUpdateState(_:) 

Tells the delegate the peripheral manager’s state updated.
告知委托外围设备管理器的状态已更新。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func peripheralManagerDidUpdateState(_ peripheral: CBPeripheralManager)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:)#parameters)

- `peripheral`

  The peripheral manager whose state has changed. 

  状态已更改的外围管理器。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:)#Discussion)

You implement this required method to ensure that Bluetooth low energy is available to use on the local peripheral device.
您可以实现此必需的方法，以确保低功耗蓝牙可用于本地外围设备。

Issue commands to the peripheral manager only when the peripheral manager is in the powered-on state, as indicated by the [`CBPeripheralManagerState.poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredon) constant. A state with a value lower than [`CBPeripheralManagerState.poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredon) implies that advertising has stopped and that any connected centrals have been disconnected. If the state moves below [`CBPeripheralManagerState.poweredOff`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredoff), advertising has stopped you must explicitly restart it. In addition, the powered off state clears the local database; in this case you must explicitly re-add all services. For a complete list and discussion of the possible values representing the state of the peripheral manager, see the [`CBPeripheralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate) enumeration in [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager).
仅当外设管理器处于开机状态时，才向外设管理器发出命令，如 `CBPeripheralManagerState.poweredOn` 常量所示。值低于以下值的状态 `CBPeripheralManagerState.poweredOn` 表示广告已停止，并且任何连接的中心都已断开连接。如果状态低于 `CBPeripheralManagerState.poweredOff` ，广告已停止，则必须显式重新启动它。此外，关闭电源状态会清除本地数据库;在这种情况下，必须显式重新添加所有服务。有关表示外设管理器状态的可能值的完整列表和讨论，请参见 `CBPeripheralManagerState` 中的 `CBPeripheralManager` 枚举。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅核心蓝牙编程指南。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:)#see-also)

### [Monitoring Changes to the Peripheral Manager’s State 监视对外设管理器状态的更改](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:)#Monitoring-Changes-to-the-Peripheral-Managers-State)

[`func peripheralManager(CBPeripheralManager, willRestoreState: [String : Any\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:))

Tells the delegate the system is about to restore the peripheral manager.
告知委托系统即将恢复外围管理器。



Peripheral Manager State Restoration Options
外设管理器状态恢复选项

Keys used to specify options when restoring the state of a peripheral manager.
用于在恢复外设管理器状态时指定选项的键。
