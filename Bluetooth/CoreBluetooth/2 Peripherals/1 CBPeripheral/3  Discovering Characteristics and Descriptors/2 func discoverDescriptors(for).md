Instance Method Instance 方法

# discoverDescriptors(for:) 

Discovers the descriptors of a characteristic.
发现特征的描述符。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func discoverDescriptors(for characteristic: CBCharacteristic)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:)#parameters)

- `characteristic`

  The characteristic whose descriptors you want to discover. 

  要发现其描述符的特征。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:)#Discussion)

When the peripheral discovers one or more descriptors of the specified characteristic, it calls the [`peripheral(_:didDiscoverDescriptorsFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:)) method of its delegate object. After the peripheral discovers the descriptors of the characteristic, you can access them through the characteristic’s [`descriptors`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors) property.
当外围设备发现指定特征的一个或多个描述符时，它会调用其委托对象 `peripheral(_:didDiscoverDescriptorsFor:error:)` 的方法。外围设备发现特征的描述符后，可以通过特征 `descriptors` 的属性访问它们。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:)#see-also)

### [Discovering Characteristics and Descriptors 发现特征和描述符](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:)#Discovering-Characteristics-and-Descriptors)

[`func discoverCharacteristics([CBUUID\]?, for: CBService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:))

Discovers the specified characteristics of a service.
发现服务的指定特征。
