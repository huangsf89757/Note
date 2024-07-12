# readValue(for:) 

Retrieves the value of a specified characteristic descriptor.
检索指定特征描述符的值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func readValue(for descriptor: CBDescriptor)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp#parameters)

- `descriptor`

  The characteristic descriptor whose value you want to read. 

  要读取其值的特征描述符。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp#Discussion)

When you call this method to read the value of a characteristic descriptor, the peripheral calls the [`peripheral(_:didUpdateValueFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1t3wm) method of its delegate object. If the peripheral successfully retrieves the value of the characteristic descriptor, you can access it through the characteristic descriptor’s [`value`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor/value) property.
调用此方法读取特征描述符的值时，外围设备将调用其委托对象 `peripheral(_:didUpdateValueFor:error:)` 的方法。如果外设成功检索特征描述符的值，则可以通过特征描述符 `value` 的属性访问它。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp#see-also)

### [Reading Characteristic and Descriptor Values 读取特征和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp#Reading-Characteristic-and-Descriptor-Values)

[`func readValue(for: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr)

Retrieves the value of a specified characteristic.
检索指定特征的值。
