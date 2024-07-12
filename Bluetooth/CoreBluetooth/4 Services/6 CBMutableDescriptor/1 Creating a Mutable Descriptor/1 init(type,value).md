Initializer

# init(type:value:) 

Creates a mutable descriptor with a specified value.
创建具有指定值的可变描述符。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+

```
init(
    type UUID: CBUUID,
    value: Any?
)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor/init(type:value:)#parameters)

- `UUID`

  A 128-bit UUID that identifies the characteristic. You must use only one of the two currently supported descriptor types: [`CBUUIDCharacteristicUserDescriptionString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicuserdescriptionstring) or [`CBUUIDCharacteristicFormatString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicformatstring). For more details about these descriptor types, see [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid). 

  标识特征的128位UUID。您只能使用当前支持的两种描述符类型之一： `CBUUIDCharacteristicUserDescriptionString` 或 `CBUUIDCharacteristicFormatString` 。有关这些描述符类型的更多详细信息，请参见 `CBUUID` 。

- `value`

  The descriptor value to cache. You must provide a non-`nil` value. Once published, you can’t update the value dynamically. 

  要缓存的描述符值。您必须提供非 `nil` 值。一旦发布，您就不能动态更新该值。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor/init(type:value:)#return-value)

A newly initialized mutable descriptor.
新初始化的可变描述符。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor/init(type:value:)#Discussion)

The value type of `value` depends on the type of descriptor:
`value` 的值类型取决于描述符的类型：

- The value type of [`CBUUIDCharacteristicUserDescriptionString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicuserdescriptionstring) is a string you use to provide a human-readable description of the characteristic’s value.
  值类型 `CBUUIDCharacteristicUserDescriptionString` 是一个字符串，用于提供特征值的人类可读描述。
- The value type of a [`CBUUIDCharacteristicFormatString`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicformatstring) is an [`NSData`](https://developer.apple.com/documentation/foundation/nsdata) object that you use to specify how to format the characteristic’s value for presentation purposes.
  `CBUUIDCharacteristicFormatString` 的值类型是一个 `NSData` 对象，用于指定如何格式化特性的值以实现表示目的。

If you want to create a local characteristic format descriptor, the descriptor’s value must conform to the attribute value of the characteristic format descriptor as defined in the Bluetooth 4.0 specification, Volume 3, Part G, Section 3.3.3.5.
如果要创建本地特征格式描述符，则描述符的值必须符合蓝牙4.0规范第3卷G部分第3.3.3.5节中定义的特征格式描述符的属性值。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅Core Bluetooth Programming Guide。
