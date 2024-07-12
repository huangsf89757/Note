Structure 结构

# CBATTError CBATError错误

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
struct CBATTError
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#topics)

### [Inspecting Error Properties 检查错误属性](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Inspecting-Error-Properties)

#### [`static var errorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/errordomain-43w9o)

Default domain of the error.
错误的默认域。



#### [`var localizedDescription: String`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/localizeddescription)

Retrieve the localized description for this error.
请检查此错误的本地化说明。



### [Error Codes 错误代码](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Error-Codes)

#### [`static var success: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/success)

The ATT command or request successfully completed.
ATT命令或请求已成功完成。



#### [`static var invalidHandle: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/invalidhandle)

The attribute handle is invalid on this peripheral.
属性句柄在此外围设备上无效。



#### [`static var readNotPermitted: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/readnotpermitted)

The permissions prohibit reading the attribute’s value.
权限禁止阅读属性的值。



#### [`static var writeNotPermitted: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/writenotpermitted)

The permissions prohibit writing the attribute’s value.
权限禁止写入属性的值。



#### [`static var invalidPdu: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/invalidpdu)

The attribute Protocol Data Unit (PDU) is invalid.
属性协议数据单元（PDU）无效。



#### [`static var insufficientAuthentication: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/insufficientauthentication)

Reading or writing the attribute’s value failed for lack of authentication.
由于缺乏身份验证，阅读或写入属性值失败。



#### [`static var requestNotSupported: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/requestnotsupported)

The attribute server doesn’t support the request received from the client.

属性服务器不支持从客户端接收的请求。



#### [`static var invalidOffset: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/invalidoffset)

The specified offset value was past the end of the attribute’s value.
指定的偏移量值超过了属性值的结尾。



#### [`static var insufficientAuthorization: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/insufficientauthorization)

Reading or writing the attribute’s value failed for lack of authorization.
由于缺乏授权，阅读或写入属性值失败。



#### [`static var prepareQueueFull: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/preparequeuefull)

The prepare queue is full, as a result of there being too many write requests in the queue.
由于队列中的写入请求太多，准备队列已满。



#### [`static var attributeNotFound: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/attributenotfound)

The attribute wasn’t found within the specified attribute handle range.
在指定的属性句柄范围内找不到该属性。



#### [`static var attributeNotLong: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/attributenotlong)

The ATT read blob request can’t read or write the attribute.
ATT读取blob请求无法读取或写入属性。



#### [`static var insufficientEncryptionKeySize: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/insufficientencryptionkeysize)

The encryption key size used for encrypting this link is insufficient.
用于加密此链接的加密密钥大小不足。



#### [`static var invalidAttributeValueLength: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/invalidattributevaluelength)

The length of the attribute’s value is invalid for the intended operation.
属性值的长度对于预期的操作无效。



#### [`static var unlikelyError: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/unlikelyerror)

The ATT request encountered an unlikely error and wasn’t completed.
ATT请求遇到了一个不太可能的错误，并且没有完成。



#### [`static var insufficientEncryption: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/insufficientencryption)

Reading or writing the attribute’s value failed for lack of encryption.
由于缺少加密，阅读或写入属性值失败。



#### [`static var unsupportedGroupType: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/unsupportedgrouptype)

The attribute type isn’t a supported grouping attribute as defined by a higher-layer specification.
属性类型不是由高层规范定义的受支持的分组属性。



#### [`static var insufficientResources: CBATTError.Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/insufficientresources)

Resources are insufficient to complete the ATT request.
资源不足以完成ATT请求。



### [Testing Error Inequality 测试误差不等式](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Testing-Error-Inequality)

#### [`static func != (Self, Self) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/!=(_:_:))

Returns a Boolean value indicating whether two values are not equal.
返回一个布尔值，指示两个值是否不相等。



### [Enumerations 枚举](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Enumerations)

#### [`enum Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code)

The possible errors returned by a GATT server (a remote peripheral) during Bluetooth low energy ATT transactions.
蓝牙低功耗ATT事务期间GATT服务器（远程外设）可能返回的错误。



### [Type Properties 类型属性](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Type-Properties)

#### [`static var errorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/errordomain-60uli)

The domain of the error.
错误的域。



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Default-Implementations)

#### CustomNSError Implementations

CustomNSError实现



#### Equatable Implementations

Equatable实现



#### Error Implementations 

错误实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#conforms-to)

- [`CustomNSError`](https://developer.apple.com/documentation/foundation/customnserror)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Error`](https://developer.apple.com/documentation/Swift/Error)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#see-also)

### [Errors 错误](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct#Errors)

[`struct CBError`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct)

An error that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误。

[`let CBErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cberrordomain)

The domain for Core Bluetooth errors.
核心蓝牙错误的域。

[`enum Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code)

The codes for errors that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误代码。

[`let CBATTErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cbatterrordomain)

The domain for Core Bluetooth ATT errors.
核心蓝牙ATT错误的域。

[`enum Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code)

The possible errors returned by a GATT server (a remote peripheral) during Bluetooth low energy ATT transactions.
蓝牙低功耗ATT事务期间GATT服务器（远程外设）可能返回的错误。
