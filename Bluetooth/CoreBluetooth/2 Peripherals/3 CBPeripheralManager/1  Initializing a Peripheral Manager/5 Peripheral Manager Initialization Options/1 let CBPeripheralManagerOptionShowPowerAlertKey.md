Global Variable 全局变量

# CBPeripheralManagerOptionShowPowerAlertKey

A Boolean value specifying whether the system should warn if Bluetooth is in the powered-off state when instantiating the peripheral manager.
一个 Boolean 值，该值指定在实例化外围设备管理器时，如果蓝牙处于关机状态，系统是否应发出警告。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
let CBPeripheralManagerOptionShowPowerAlertKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionshowpoweralertkey#Discussion)

The value for this key is an [`NSNumber`](https://developer.apple.com/documentation/foundation/nsnumber). If the key isn’t specified, the default value is [`false`](https://developer.apple.com/documentation/swift/false).
此键的值为 `NSNumber` .如果未指定键，则默认值为 `false` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionshowpoweralertkey#see-also)

### [Initialization Options 初始化选项](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionshowpoweralertkey#Initialization-Options)

[`let CBPeripheralManagerOptionRestoreIdentifierKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanageroptionrestoreidentifierkey)

A unique identifier (UID) with which to instantiate the peripheral manager.
用于实例化外设管理器的唯一标识符 （UID）。
