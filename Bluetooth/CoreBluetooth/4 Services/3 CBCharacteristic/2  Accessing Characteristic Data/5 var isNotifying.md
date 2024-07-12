Instance Property 实例属性

# isNotifying 

A Boolean value that indicates whether the characteristic is currently notifying a subscribed central of its value.
一个布尔值，指示特征当前是否正在向订阅中心通知其值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var isNotifying: Bool { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying#Discussion)

This value is [`true`](https://developer.apple.com/documentation/swift/true) if you enabled notifications or indications for the characteristic by successfully calling the [`setNotifyValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)) method of the [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class. In this case, the peripheral updates its connected central that whenever the characteristic’s value changes.
如果您通过成功调用 `CBPeripheral` 类的 `setNotifyValue(_:for:)` 方法为特征启用了通知或指示，则此值为 `true` 。在这种情况下，外围设备更新其连接的中心，每当特征的值发生变化。

If the value of the property is [`false`](https://developer.apple.com/documentation/swift/false), notifications (or indications) aren’t enabled for the characteristic, and the peripheral doesn’t update its connected central when the characteristic’s value changes.
如果属性的值为 `false` ，则不会为特征启用通知（或指示），并且当特征的值更改时，外围设备不会更新其连接的中心设备。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying#topics)

### [Related Documentation 相关文件](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying#Related-Documentation)

#### [`func setNotifyValue(Bool, for: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:))

Sets notifications or indications for the value of a specified characteristic.
为指定特征的值设置通知或指示。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying#see-also)

### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying#Accessing-Characteristic-Data)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value)

The value of the characteristic.
特性的值。

[`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors)

A list of the descriptors discovered in this characteristic.
在此特征中发现的描述符的列表。

[`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties)

The properties of the characteristic.
特性的属性。

[`struct CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties)

Values that represent the possible properties of a characteristic.
表示特性的可能属性的值。

[`var isBroadcasted: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted)

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.
