Global Variable 全局变量

# CBPeripheralManagerOptionRestoreIdentifierKey

A unique identifier (UID) with which to instantiate the peripheral manager.
用于实例化外设管理器的唯一标识符 （UID）。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
let CBPeripheralManagerOptionRestoreIdentifierKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionrestoreidentifierkey#Discussion)

The value associated with this key is an [`NSString`](https://developer.apple.com/documentation/foundation/nsstring).
与此键关联的值是 `NSString` .

The system uses this UID to identify a specific peripheral manager. As a result, the UID must remain the same for subsequent executions of the app for successful restoration of the peripheral manager.
系统使用此 UID 来标识特定的外设管理器。因此，对于应用的后续执行，UID 必须保持不变，才能成功恢复外围设备管理器。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionrestoreidentifierkey#see-also)

### [Initialization Options 初始化选项](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionrestoreidentifierkey#Initialization-Options)

[`let CBPeripheralManagerOptionShowPowerAlertKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionshowpoweralertkey)

A Boolean value specifying whether the system should warn if Bluetooth is in the powered-off state when instantiating the peripheral manager.
一个 Boolean 值，该值指定在实例化外围设备管理器时，如果蓝牙处于关机状态，系统是否应发出警告。
