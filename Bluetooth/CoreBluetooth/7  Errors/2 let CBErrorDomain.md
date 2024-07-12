Global Variable 全局变量

# CBErrorDomain

The domain for Core Bluetooth errors.
核心蓝牙错误的域。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
let CBErrorDomain: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cberrordomain#Discussion)

This value identifies Core Bluetooth errors when used as the [`domain`](https://developer.apple.com/documentation/foundation/nserror/1413924-domain) of an [`NSError`](https://developer.apple.com/documentation/foundation/nserror) instance.
此值在用作 `NSError` 实例的 `domain` 时标识核心蓝牙错误。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cberrordomain#see-also)

### [Errors 错误](https://developer.apple.com/documentation/corebluetooth/cberrordomain#Errors)

[`struct CBError`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct)

An error that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误。

[`enum Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code)

The codes for errors that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误代码。

[`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。

[`let CBATTErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cbatterrordomain)

The domain for Core Bluetooth ATT errors.
核心蓝牙ATT错误的域。

[`enum Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code)

The possible errors returned by a GATT server (a remote peripheral) during Bluetooth low energy ATT transactions.
蓝牙低功耗ATT事务期间GATT服务器（远程外设）可能返回的错误。

[`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。
