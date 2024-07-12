Global Variable 全局变量

# CBCentralManagerOptionRestoreIdentifierKey

A string containing a unique identifier (UID) for the central manager to instantiate.
一个字符串，包含中央管理器要实例化的唯一标识符（UID）。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
let CBCentralManagerOptionRestoreIdentifierKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionrestoreidentifierkey#Discussion)

The value for this key is an [`NSString`](https://developer.apple.com/documentation/foundation/nsstring). The system uses this UID to identify a specific central manager. As a result, the UID must remain the same for subsequent executions of the app to restore the central manager.
此键的值为 `NSString` 。系统使用此UID标识特定的中央管理器。因此，UID必须保持不变，以便后续执行应用程序来恢复中央管理器。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionrestoreidentifierkey#see-also)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionrestoreidentifierkey#Constants)

[`let CBCentralManagerOptionShowPowerAlertKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionshowpoweralertkey)

A Boolean value that specifies whether the system warns the user if the app instantiates the central manager when Bluetooth service isn’t available.
一个布尔值，指定当蓝牙服务不可用时，如果应用实例化中央管理器，系统是否警告用户。
