Global Variable 全局变量

# CBCentralManagerOptionShowPowerAlertKey

A Boolean value that specifies whether the system warns the user if the app instantiates the central manager when Bluetooth service isn’t available.
一个布尔值，指定当蓝牙服务不可用时，如果应用实例化中央管理器，系统是否警告用户。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ ｜ 

```
let CBCentralManagerOptionShowPowerAlertKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionshowpoweralertkey#Discussion)

The value for this key is an [`NSNumber`](https://developer.apple.com/documentation/foundation/nsnumber) object. If the key isn’t specified, the default value is [`true`](https://developer.apple.com/documentation/swift/true).
这个键的值是一个 `NSNumber` 对象。如果未指定键，则默认值为 `true` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionshowpoweralertkey#see-also)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionshowpoweralertkey#Constants)

[`let CBCentralManagerOptionRestoreIdentifierKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanageroptionrestoreidentifierkey)

A string containing a unique identifier (UID) for the central manager to instantiate.
一个字符串，包含中央管理器要实例化的唯一标识符（UID）。
