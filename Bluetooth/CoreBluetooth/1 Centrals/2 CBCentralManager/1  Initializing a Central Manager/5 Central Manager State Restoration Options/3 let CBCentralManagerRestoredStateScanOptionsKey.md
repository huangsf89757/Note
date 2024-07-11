Global Variable 全局变量

# CBCentralManagerRestoredStateScanOptionsKey

A dictionary of peripheral scan options for use when restoring state.
用于恢复状态的外围设备扫描选项的字典。

iOS 7.0+ ｜  iOS的7.0 + ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜  视觉操作系统 1.0+ ｜ watchOS 2.0+ 

```
let CBCentralManagerRestoredStateScanOptionsKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanoptionskey#Discussion)

The value associated with this key is an [`NSDictionary`](https://developer.apple.com/documentation/foundation/nsdictionary). The dictionary contains all of the peripheral scan options in use by the central manager when the system terminated the app.
与此键关联的值是 `NSDictionary` .该字典包含系统终止应用程序时中央管理器使用的所有外围设备扫描选项。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanoptionskey#see-also)

### [State Restoration Options 状态恢复选项](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanoptionskey#State-Restoration-Options)

[`let CBCentralManagerRestoredStatePeripheralsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstateperipheralskey)

An array of peripherals for use when restoring the state of a central manager.
用于恢复中央管理器状态的外围设备阵列。

[`let CBCentralManagerRestoredStateScanServicesKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanserviceskey)

An array of service IDs for use when restoring state.
还原状态时使用的服务 ID 数组。
