Instance Method Instance 方法

# maximumWriteValueLength(for:) 

The maximum amount of data, in bytes, you can send to a characteristic in a single write type.
可以发送到单个写入类型特征的最大数据量（以字节为单位）。

iOS 9.0+ iOS的9.0 +iPadOS 9.0+Mac Catalyst 13.1+macOS 10.12+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func maximumWriteValueLength(for type: CBCharacteristicWriteType) -> Int
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:)#parameters)

- `type`

  The characteristic write type to inspect. 

  要检查的特征写入类型。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:)#see-also)

### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:)#Writing-Characteristic-and-Descriptor-Values)

[`func writeValue(Data, for: CBCharacteristic, type: CBCharacteristicWriteType)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:))

Writes the value of a characteristic.
写入特征的值。

[`func writeValue(Data, for: CBDescriptor)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:))

Writes the value of a characteristic descriptor.
写入特征描述符的值。

[`enum CBCharacteristicWriteType`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype)

Values representing the possible write types to a characteristic’s value.
表示特征值的可能写入类型的值。
