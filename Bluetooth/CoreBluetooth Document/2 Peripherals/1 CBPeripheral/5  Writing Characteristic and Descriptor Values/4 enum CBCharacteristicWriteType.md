Enumeration 列举

# CBCharacteristicWriteType

Values representing the possible write types to a characteristic’s value.
表示特征值的可能写入类型的值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
enum CBCharacteristicWriteType
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#overview)

Characteristic write types have corresponding restrictions on the length of the data that you can write to a characteristic’s value. For the [`CBCharacteristicWriteType.withResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/withresponse) write type’s restrictions, see the Bluetooth 4.0 specification, Volume 3, Part G, Sections 4.9.3–4. For the [`CBCharacteristicWriteType.withoutResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/withoutresponse) write type restrictions, see the Bluetooth 4.0 specification, Volume 3, Part G, Sections 4.9.1–2.
特征写入类型对可以写入特征值的数据长度具有相应的限制。有关 `CBCharacteristicWriteType.withResponse` 写入类型的限制，请参阅蓝牙 4.0 规范，第 3 卷，G 部分，第 4.9.3–4 节。有关 `CBCharacteristicWriteType.withoutResponse` 写入类型限制，请参阅蓝牙 4.0 规范，第 3 卷，G 部分，第 4.9.1–2 节。

> Tip 提示
>
> When you write with a response, you can write a characteristic value that’s longer than permitted when you write without a response.
> 使用响应写入时，可以写入的特征值比在没有响应的情况下写入时允许的长度长。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#topics)

### [Write Types 写入类型](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#Write-Types)

#### [`case withResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/withresponse)

Write a characteristic value, with a response from the peripheral to indicate whether the write was successful.
写入一个特征值，并带有来自外设的响应，以指示写入是否成功。



#### [`case withoutResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/withoutresponse)

Write a characteristic value, without any response from the peripheral to indicate whether the write was successful.
写入一个特征值，而外设没有任何响应，以指示写入是否成功。



### [Initializers 初始值设定项](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#Default-Implementations)

#### Equatable Implementations

等式实现



#### RawRepresentable Implementations

RawRepresentable 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#see-also)

### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype#Writing-Characteristic-and-Descriptor-Values)

[`func writeValue(Data, for: CBCharacteristic, type: CBCharacteristicWriteType)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:))

Writes the value of a characteristic.
写入特征的值。

[`func writeValue(Data, for: CBDescriptor)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:))

Writes the value of a characteristic descriptor.
写入特征描述符的值。

[`func maximumWriteValueLength(for: CBCharacteristicWriteType) -> Int`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:))

The maximum amount of data, in bytes, you can send to a characteristic in a single write type.
可以发送到单个写入类型特征的最大数据量（以字节为单位）。