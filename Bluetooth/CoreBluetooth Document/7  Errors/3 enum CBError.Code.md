Enumeration 枚举

# CBError.Code

The codes for errors that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误代码。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
enum Code
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#topics)

### [Error Codes 错误代码](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#Error-Codes)

#### [`case unknown`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/unknown)

An unknown error occurred.
发生未知错误。



#### [`case invalidParameters`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/invalidparameters)

The specified parameters are invalid.
指定的参数无效。



#### [`case invalidHandle`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/invalidhandle)

The specified attribute handle is invalid.
指定的属性句柄无效。



#### [`case notConnected`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/notconnected)

The device isn’t currently connected.
设备当前未连接。



#### [`case outOfSpace`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/outofspace)

The device has run out of space to complete the intended operation.
器械空间不足，无法完成预期操作。



#### [`case operationCancelled`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/operationcancelled)

The error represents a canceled operation.
该错误表示已取消的操作。



#### [`case connectionTimeout`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/connectiontimeout)

The connection timed out.
连接超时。



#### [`case peripheralDisconnected`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/peripheraldisconnected)

The peripheral disconnected.
外围设备已断开连接。



#### [`case uuidNotAllowed`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/uuidnotallowed)

The specified UUID isn’t permitted.
不允许指定的UUID。



#### [`case alreadyAdvertising`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/alreadyadvertising)

The peripheral is already advertising.
外围设备已经在做广告了。



#### [`case connectionFailed`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/connectionfailed)

The connection failed. 

连接失败。



#### [`case connectionLimitReached`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/connectionlimitreached)

The device already has the maximum number of connections.
设备已达到最大连接数。



#### [`case operationNotSupported`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/operationnotsupported)

The operation isn’t supported.
不支持该操作。



#### [`static var unknownDevice: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/unknowndevice)

The device is unknown. 

器械未知。



#### [`case unkownDevice`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/unkowndevice)

A misspelled version of the unknown device error code.
未知设备错误代码的拼写错误版本。

`Deprecated 弃用`



### [Enumeration Cases 枚举案例](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#Enumeration-Cases)

#### [`case encryptionTimedOut`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/encryptiontimedout)

#### [`case leGattExceededBackgroundNotificationLimit`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/legattexceededbackgroundnotificationlimit)

#### [`case leGattNearBackgroundNotificationLimit`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/legattnearbackgroundnotificationlimit)

#### [`case peerRemovedPairingInformation`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/peerremovedpairinginformation)

#### [`case tooManyLEPairedDevices`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/toomanylepaireddevices)



### [Initializers](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### RawRepresentable Implementations

原始可代表的实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#see-also)

### [Errors 错误](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code#Errors)

[`struct CBError`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct)

An error that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误。

[`let CBErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cberrordomain)

The domain for Core Bluetooth errors.
核心蓝牙错误的域。

[`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).

[`let CBATTErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cbatterrordomain)

The domain for Core Bluetooth ATT errors.
核心蓝牙ATT错误的域。

[`enum Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code)

The possible errors returned by a GATT server (a remote peripheral) during Bluetooth low energy ATT transactions.
蓝牙低功耗ATT事务期间GATT服务器（远程外设）可能返回的错误。

[`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。
