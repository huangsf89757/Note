Instance Method Instance 方法

# writeValue(_:for:type:) 

Writes the value of a characteristic.
写入特征的值。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func writeValue(
    _ data: Data,
    for characteristic: CBCharacteristic,
    type: CBCharacteristicWriteType
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:)#parameters)

- `data`

  The value to write. 要写入的值。

- `characteristic`

  The characteristic containing the value to write. 包含要写入的值的特征。

- `type`

  The type of write to execute. For a list of the possible types of writes to a characteristic’s value, see [`CBCharacteristicWriteType`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype). 要执行的写入类型。有关写入特征值的可能类型的列表，请参见 `CBCharacteristicWriteType` 。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:)#Discussion)

When you call this method to write the value of a characteristic, the peripheral calls the [`peripheral(_:didWriteValueFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-4f5ea) method of its delegate object only if you specified the write type as [`CBCharacteristicWriteType.withResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/withresponse). The response you receive through the [`peripheral(_:didWriteValueFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-4f5ea) delegate method indicates whether the write was successful; if the write failed, it details the cause of the failure in an error.
调用此方法以写入特征值时，仅当将写入类型指定为 `CBCharacteristicWriteType.withResponse` 时，外设才会调用其委托对象 `peripheral(_:didWriteValueFor:error:)` 的方法。通过 `peripheral(_:didWriteValueFor:error:)` 委托方法收到的响应指示写入是否成功;如果写入失败，则详细说明错误失败的原因。

On the other hand, if you specify the write type as [`CBCharacteristicWriteType.withoutResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype/withoutresponse), Core Bluetooth attempts to write the value but doesn’t guarantee success. If the write doesn’t succeed in this case, you aren’t notified and you don’t receive an error indicating the cause of the failure.
另一方面，如果将写入类型指定为 `CBCharacteristicWriteType.withoutResponse` ，Core Bluetooth 会尝试写入该值，但不能保证成功。如果在这种情况下写入不成功，则不会收到通知，也不会收到指示失败原因的错误。

Use the [`write`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/write) and [`writeWithoutResponse`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/writewithoutresponse) members of the characteristic’s [`properties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties) enumeration to determine which kinds of writes you can perform.
使用特征 `properties` 枚举的 `write` 和 `writeWithoutResponse` 成员来确定可以执行的写入类型。

This method copies the data passed into the `data` parameter, and you can dispose of it after the method returns.
此方法复制传递到参数中 `data` 的数据，您可以在方法返回后释放它。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:)#see-also)

### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:)#Writing-Characteristic-and-Descriptor-Values)

[`func writeValue(Data, for: CBDescriptor)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:))

Writes the value of a characteristic descriptor.
写入特征描述符的值。

[`func maximumWriteValueLength(for: CBCharacteristicWriteType) -> Int`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:))

The maximum amount of data, in bytes, you can send to a characteristic in a single write type.
可以发送到单个写入类型特征的最大数据量（以字节为单位）。

[`enum CBCharacteristicWriteType`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype)

Values representing the possible write types to a characteristic’s value.
表示特征值的可能写入类型的值。
