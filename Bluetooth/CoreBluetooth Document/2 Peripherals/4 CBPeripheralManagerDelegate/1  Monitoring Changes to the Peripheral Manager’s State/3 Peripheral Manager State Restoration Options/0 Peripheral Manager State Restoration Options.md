API Collection API 集合

# Peripheral Manager State Restoration Options 外设管理器状态恢复选项

Keys used to specify options when restoring the state of a peripheral manager.
用于在恢复外设管理器状态时指定选项的键。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-state-restoration-options#topics)

### [State Restoration Dictionary Keys 状态还原字典键](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-state-restoration-options#State-Restoration-Dictionary-Keys)

#### [`let CBPeripheralManagerRestoredStateServicesKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerrestoredstateserviceskey)

An array of restored peripheral services.
一系列已恢复的外围服务。



#### [`let CBPeripheralManagerRestoredStateAdvertisementDataKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerrestoredstateadvertisementdatakey)

A dictionary of restored advertising data.
恢复广告数据的字典。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-state-restoration-options#see-also)

### [Monitoring Changes to the Peripheral Manager’s State 监视对外设管理器状态的更改](https://developer.apple.com/documentation/corebluetooth/peripheral-manager-state-restoration-options#Monitoring-Changes-to-the-Peripheral-Managers-State)

[`func peripheralManagerDidUpdateState(CBPeripheralManager)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:))

Tells the delegate the peripheral manager’s state updated.
告知委托外围设备管理器的状态已更新。

**Required 必填**

[`func peripheralManager(CBPeripheralManager, willRestoreState: [String : Any\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:))

Tells the delegate the system is about to restore the peripheral manager.
告知委托系统即将恢复外围管理器。
