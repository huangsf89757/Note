# isBroadcasted

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.

iOS 5.0–8.0`Deprecated` | iPadOS 5.0–8.0`Deprecated` | Mac Catalyst 13.1–13.1`Deprecated` | macOS 10.9–10.13`Deprecated` | tvOS 9.0+visionOS 1.0–1.0`Deprecated` | watchOS 2.0–2.0`Deprecated`

```
var isBroadcasted: Bool { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted#Discussion)

Don’t use this deprecated property.
不要使用此已弃用的属性。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted#see-also)

### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted#Accessing-Characteristic-Data)

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

[`var isNotifying: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying)

A Boolean value that indicates whether the characteristic is currently notifying a subscribed central of its value.
一个布尔值，指示特征当前是否正在向订阅中心通知其值。
