Global Variable 全局变量

# CBCentralManagerRestoredStateScanServicesKey

An array of service IDs for use when restoring state.
还原状态时使用的服务 ID 数组。

iOS 7.0+ ｜  iOS的7.0 + ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜  视觉操作系统 1.0+ ｜ watchOS 2.0+ 

```
let CBCentralManagerRestoredStateScanServicesKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanserviceskey#Discussion)

The value associated with this key is an [`NSArray`](https://developer.apple.com/documentation/foundation/nsarray) of service UUIDs (represented by [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects) containing all the services the central manager was scanning for at the time the system terminated the app.
与此键关联的值是一个 `NSArray` 服务 UUID（由 `CBUUID` 对象表示），其中包含中央管理器在系统终止应用时正在扫描的所有服务。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanserviceskey#see-also)

### [State Restoration Options 状态恢复选项](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanserviceskey#State-Restoration-Options)

[`let CBCentralManagerRestoredStatePeripheralsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstateperipheralskey)

An array of peripherals for use when restoring the state of a central manager.
用于恢复中央管理器状态的外围设备阵列。

[`let CBCentralManagerRestoredStateScanOptionsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerrestoredstatescanoptionskey)

A dictionary of peripheral scan options for use when restoring state.
用于恢复状态的外围设备扫描选项的字典。
