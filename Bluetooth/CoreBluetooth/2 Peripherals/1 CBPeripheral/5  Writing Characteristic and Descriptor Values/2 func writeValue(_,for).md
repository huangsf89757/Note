Instance Method Instance 方法

# writeValue(_:for:) 

Writes the value of a characteristic descriptor.
写入特征描述符的值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func writeValue(
    _ data: Data,
    for descriptor: CBDescriptor
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)#parameters)

- `data`

  The value to write. 要写入的值。

- `descriptor`

  The descriptor containing the value to write. 包含要写入的值的描述符。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)#Discussion)

When you call this method to write the value of a characteristic descriptor, the peripheral calls the [`peripheral(_:didWriteValueFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3) method of its delegate object.
调用此方法以写入特征描述符的值时，外设将调用其委托对象 `peripheral(_:didWriteValueFor:error:)` 的方法。

This method copies the `data` passed into the data parameter, and you can dispose of it after the method returns.
此方法将传递的内容 `data` 复制到 data 参数中，您可以在方法返回后释放它。

You can’t use this method to write the value of a client configuration descriptor (represented by the [`CBUUIDClientCharacteristicConfigurationString`](https://developer.apple.com/documentation/corebluetooth/cbuuidclientcharacteristicconfigurationstring) constant), which describes the configuration of notification or indications for a characteristic’s value. If you want to manage notifications or indications for a characteristic’s value, you must use the [`setNotifyValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)) method instead.
不能使用此方法编写客户端配置描述符（由 `CBUUIDClientCharacteristicConfigurationString` 常量表示）的值，该描述特征值的通知或指示的配置。如果要管理特征值的通知或指示，则必须改用该 `setNotifyValue(_:for:)` 方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)#see-also)

### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)#Writing-Characteristic-and-Descriptor-Values)

[`func writeValue(Data, for: CBCharacteristic, type: CBCharacteristicWriteType)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:))

Writes the value of a characteristic.
写入特征的值。

[`func maximumWriteValueLength(for: CBCharacteristicWriteType) -> Int`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:))

The maximum amount of data, in bytes, you can send to a characteristic in a single write type.
可以发送到单个写入类型特征的最大数据量（以字节为单位）。

[`enum CBCharacteristicWriteType`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype)

Values representing the possible write types to a characteristic’s value.
表示特征值的可能写入类型的值。
