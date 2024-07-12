Instance Property 实例属性

# descriptors 

A list of the descriptors discovered in this characteristic.
在此特征中发现的描述符的列表。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var descriptors: [CBDescriptor]? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors#Discussion)

The value of this property is an array of [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor) objects that represent a characteristic’s descriptors. Characteristic descriptors provide more information about a characteristic’s value. For example, they may describe the value in human-readable form and describe how to format the value for presentation purposes. For more information about characteristic descriptors, see [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor).
该属性的值是一个由 `CBDescriptor` 对象组成的数组，这些对象表示特征的描述符。特征描述符提供了有关特征值的更多信息。例如，它们可以以人类可读的形式描述值，并描述如何格式化值以用于表示目的。有关特征描述符的更多信息，请参见 `CBDescriptor` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors#see-also)

### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors#Accessing-Characteristic-Data)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value)

The value of the characteristic.
特性的值。

[`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties)

The properties of the characteristic.
特性的属性。

[`struct CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties)

Values that represent the possible properties of a characteristic.
表示特性的可能属性的值。

[`var isNotifying: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying)

A Boolean value that indicates whether the characteristic is currently notifying a subscribed central of its value.
一个布尔值，指示特征当前是否正在向订阅中心通知其值。

[`var isBroadcasted: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted)

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.
