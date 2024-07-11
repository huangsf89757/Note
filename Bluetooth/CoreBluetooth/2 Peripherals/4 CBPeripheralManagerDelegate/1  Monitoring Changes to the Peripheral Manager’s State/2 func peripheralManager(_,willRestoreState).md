Instance Method Instance 方法

# peripheralManager(_:willRestoreState:) 

Tells the delegate the system is about to restore the peripheral manager.
告知委托系统即将恢复外围管理器。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    willRestoreState dict: [String : Any]
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:)#parameters)

- `peripheral`

  The peripheral manager undergoing state restoration. 

  正在进行状态还原的外设管理器。

- `dict`

  A dictionary that contains information about the peripheral manager, which the system preserved when the app terminated. For the available keys to this dictionary, see [Peripheral Manager State Restoration Options](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-state-restoration-options).

  包含有关外围设备管理器的信息的字典，系统在应用程序终止时保留这些信息。有关此字典的可用键，请参阅 Peripheral Manager 状态还原选项。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:)#Discussion)

For apps that opt in to the state preservation and restoration feature, Core Bluetooth invokes this method when relaunching your app into the background to complete some Bluetooth-related task. Use this method to synchronize the state of your app with the state of the Bluetooth system.
对于选择加入状态保留和恢复功能的应用，Core Bluetooth 会在将应用重新启动到后台以完成某些与蓝牙相关的任务时调用此方法。使用此方法将应用的状态与蓝牙系统的状态同步。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:)#see-also)

### [Monitoring Changes to the Peripheral Manager’s State 监视对外设管理器状态的更改](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:)#Monitoring-Changes-to-the-Peripheral-Managers-State)

[`func peripheralManagerDidUpdateState(CBPeripheralManager)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:))

Tells the delegate the peripheral manager’s state updated.
告知委托外围设备管理器的状态已更新。

**Required 必填**



Peripheral Manager State Restoration Options
外设管理器状态恢复选项

Keys used to specify options when restoring the state of a peripheral manager.
用于在恢复外设管理器状态时指定选项的键。
