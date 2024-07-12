Enumeration 枚举

# CBATTError.Code

The possible errors returned by a GATT server (a remote peripheral) during Bluetooth low energy ATT transactions.
蓝牙低功耗ATT事务期间GATT服务器（远程外设）可能返回的错误。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.0+macOS 10.10+tvOS 9.0+visionOS 1.0+watchOS 4.0+

```
enum Code
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#overview)

These error constants derive from the Bluetooth ATT error codes, defined in the Bluetooth 4.0 specification. For more information, see the Bluetooth 4.0 specification, Volume 3, Part F, Section 3.4.1.1.
这些错误常量来自蓝牙ATT错误代码，在蓝牙4.0规范中定义。有关详细信息，请参阅蓝牙4.0规范，第3卷，F部分，第3.4.1.1节。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#topics)

### [Error Codes 错误代码](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#Error-Codes)

#### [`case success`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/success)

The ATT command or request successfully completed.
ATT命令或请求已成功完成。



#### [`case invalidHandle`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/invalidhandle)

The attribute handle is invalid on this peripheral.
属性句柄在此外围设备上无效。



#### [`case readNotPermitted`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/readnotpermitted)

The permissions prohibit reading the attribute’s value.
权限禁止阅读属性的值。



#### [`case writeNotPermitted`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/writenotpermitted)

The permissions prohibit writing the attribute’s value.
权限禁止写入属性的值。



#### [`case invalidPdu`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/invalidpdu)

The attribute Protocol Data Unit (PDU) is invalid.
属性协议数据单元（PDU）无效。



#### [`case insufficientAuthentication`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/insufficientauthentication)

Reading or writing the attribute’s value failed for lack of authentication.
由于缺乏身份验证，阅读或写入属性值失败。



#### [`case requestNotSupported`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/requestnotsupported)

The attribute server doesn’t support the request received from the client.
属性服务器不支持从客户端接收的请求。



#### [`case invalidOffset`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/invalidoffset)

The specified offset value was past the end of the attribute’s value.
指定的偏移量值超过了属性值的结尾。



#### [`case insufficientAuthorization`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/insufficientauthorization)

Reading or writing the attribute’s value failed for lack of authorization.
由于缺乏授权，阅读或写入属性值失败。



#### [`case prepareQueueFull`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/preparequeuefull)

The prepare queue is full, as a result of there being too many write requests in the queue.
由于队列中的写入请求太多，准备队列已满。



#### [`case attributeNotFound`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/attributenotfound)

The attribute wasn’t found within the specified attribute handle range.
在指定的属性句柄范围内找不到该属性。



#### [`case attributeNotLong`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/attributenotlong)

The ATT read blob request can’t read or write the attribute.
ATT读取blob请求无法读取或写入属性。



#### [`case insufficientEncryptionKeySize`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/insufficientencryptionkeysize)

The encryption key size used for encrypting this link is insufficient.
用于加密此链接的加密密钥大小不足。



#### [`case invalidAttributeValueLength`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/invalidattributevaluelength)

The length of the attribute’s value is invalid for the intended operation.
属性值的长度对于预期的操作无效。



#### [`case unlikelyError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/unlikelyerror)

The ATT request encountered an unlikely error and wasn’t completed.
ATT请求遇到了一个不太可能的错误，并且没有完成。



#### [`case insufficientEncryption`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/insufficientencryption)

Reading or writing the attribute’s value failed for lack of encryption.
由于缺少加密，阅读或写入属性值失败。



#### [`case unsupportedGroupType`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/unsupportedgrouptype)

The attribute type isn’t a supported grouping attribute as defined by a higher-layer specification.
属性类型不是由高层规范定义的受支持的分组属性。



#### [`case insufficientResources`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/insufficientresources)

Resources are insufficient to complete the ATT request.
资源不足以完成ATT请求。



### [Initializers](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### RawRepresentable Implementations

原始可代表的实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#see-also)

### [Errors 错误](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code#Errors)

[`struct CBError`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct)

An error that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误。

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

[`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。
