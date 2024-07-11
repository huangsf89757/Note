Global Variable 全局变量

# CBCentralManagerRestoredStatePeripheralsKey

An array of peripherals for use when restoring the state of a central manager.
用于恢复中央管理器状态的外围设备阵列。

iOS 7.0+ ｜  iOS的7.0 + ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜  视觉操作系统 1.0+ ｜ watchOS 2.0+ 

```
let CBCentralManagerRestoredStatePeripheralsKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstateperipheralskey#Discussion)

The value associated with this key is an [`NSArray`](https://developer.apple.com/documentation/foundation/nsarray) of [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) objects. The array contains all of the peripherals connected to the central manager (or had a pending connection) at the time the system terminated the app.
与此键关联的值是 `NSArray` of `CBPeripheral` 对象。该阵列包含在系统终止应用程序时连接到中央管理器（或具有挂起连接）的所有外围设备。

When possible, the system restores all information about a peripheral, including any discovered services, characteristics, characteristic descriptors, and characteristic notification states.
如果可能，系统会还原有关外围设备的所有信息，包括任何发现的服务、特征、特征描述符和特征通知状态。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstateperipheralskey#see-also)

### [State Restoration Options 状态恢复选项](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstateperipheralskey#State-Restoration-Options)

[`let CBCentralManagerRestoredStateScanServicesKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanserviceskey)

An array of service IDs for use when restoring state.
还原状态时使用的服务 ID 数组。

[`let CBCentralManagerRestoredStateScanOptionsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanoptionskey)

A dictionary of peripheral scan options for use when restoring state.
用于恢复状态的外围设备扫描选项的字典。
