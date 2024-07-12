Instance Method Instance 方法

# readValue(for:) 

Retrieves the value of a specified characteristic.
检索指定特征的值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func readValue(for characteristic: CBCharacteristic)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr#parameters)

- `characteristic`

  The characteristic whose value you want to read. 

  要读取其值的特征。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr#Discussion)

When you call this method to read the value of a characteristic, the peripheral calls the [`peripheral(_:didUpdateValueFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna) method of its delegate object. If the peripheral successfully reads the value of the characteristic, you can access it through the characteristic’s [`value`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value) property.
调用此方法读取特征值时，外设将调用其委托对象 `peripheral(_:didUpdateValueFor:error:)` 的方法。如果外设成功读取特征的值，则可以通过特征的 `value` 属性访问它。

Not all characteristics have a readable value. You can determine whether a characteristic’s value is readable by accessing the relevant properties of the [`CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties) enumeration.
并非所有特征都具有可读值。可以通过访问枚举的 `CBCharacteristicProperties` 相关属性来确定特征的值是否可读。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr#see-also)

### [Reading Characteristic and Descriptor Values 读取特征和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr#Reading-Characteristic-and-Descriptor-Values)

[`func readValue(for: CBDescriptor)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp)

Retrieves the value of a specified characteristic descriptor.
检索指定特征描述符的值。
