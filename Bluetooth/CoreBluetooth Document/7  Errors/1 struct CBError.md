Structure 结构

# CBError

An error that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
struct CBError
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#topics)

### [Inspecting Error Properties 检查错误属性](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Inspecting-Error-Properties)

#### [`static var errorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/errordomain-4v966)

Default domain of the error.
错误的默认域。



#### [`var localizedDescription: String`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/localizeddescription)

Retrieve the localized description for this error.
请检查此错误的本地化说明。



### [Error Codes 错误代码](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Error-Codes)

#### [`static var unknown: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/unknown)

An unknown error occurred.
发生未知错误。



#### [`static var invalidParameters: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/invalidparameters)

The specified parameters are invalid.
指定的参数无效。



#### [`static var invalidHandle: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/invalidhandle)

The specified attribute handle is invalid.
指定的属性句柄无效。



#### [`static var notConnected: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/notconnected)

The device isn’t currently connected.
设备当前未连接。



#### [`static var outOfSpace: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/outofspace)

The device has run out of space to complete the intended operation.
器械空间不足，无法完成预期操作。



#### [`static var operationCancelled: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/operationcancelled)

The error represents a canceled operation.
该错误表示已取消的操作。



#### [`static var connectionTimeout: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/connectiontimeout)

The connection timed out.
连接超时。



#### [`static var peripheralDisconnected: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/peripheraldisconnected)

The peripheral disconnected.
外围设备已断开连接。



#### [`static var uuidNotAllowed: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/uuidnotallowed)

The specified UUID isn’t permitted.
不允许指定的UUID。



#### [`static var alreadyAdvertising: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/alreadyadvertising)

The peripheral is already advertising.

外围设备已经在做广告了。



#### [`static var connectionFailed: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/connectionfailed)

The connection failed. 

连接失败。



#### [`static var connectionLimitReached: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/connectionlimitreached)

The device already has the maximum number of connections.
设备已达到最大连接数。



#### [`static var operationNotSupported: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/operationnotsupported)

The operation isn’t supported.
不支持该操作。



#### [`static var unknownDevice: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/unknowndevice)

The device is unknown. 

器械未知。



#### [`static var unkownDevice: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/unkowndevice)

A misspelled version of the unknown device error code.
未知设备错误代码的拼写错误版本。

`Deprecated 弃用`



### [Testing Error Inequality 测试误差不等式](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Testing-Error-Inequality)

#### [`static func != (Self, Self) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/!=(_:_:))

Returns a Boolean value indicating whether two values are not equal.
返回一个布尔值，指示两个值是否不相等。



### [Type Properties 类型属性](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Type-Properties)

#### [`static var encryptionTimedOut: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/encryptiontimedout)

#### [`static var leGattExceededBackgroundNotificationLimit: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/legattexceededbackgroundnotificationlimit)

#### [`static var leGattNearBackgroundNotificationLimit: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/legattnearbackgroundnotificationlimit)

#### [`static var peerRemovedPairingInformation: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/peerremovedpairinginformation)

#### [`static var tooManyLEPairedDevices: CBError.Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/toomanylepaireddevices)



### [Enumerations 枚举](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Enumerations)

#### [`enum Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code)

The codes for errors that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误代码。



### [Type Properties 类型属性](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Type-Properties)

#### [`static var errorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/errordomain-nh3m)

The domain of the error.
错误的域。



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Default-Implementations)

#### CustomNSError Implementations

CustomNSError实现



#### Equatable Implementations

Equatable实现



#### Error Implementations 

错误实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#conforms-to)

- [`CustomNSError`](https://developer.apple.com/documentation/foundation/customnserror)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Error`](https://developer.apple.com/documentation/Swift/Error)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#see-also)

### [Errors 错误](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct#Errors)

[`let CBErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cberrordomain)

The domain for Core Bluetooth errors.
核心蓝牙错误的域。

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
