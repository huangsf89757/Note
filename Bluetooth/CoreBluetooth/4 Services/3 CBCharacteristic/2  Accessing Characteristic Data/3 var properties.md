Instance Property 实例属性

# properties 

The properties of the characteristic.
特性的属性。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var properties: CBCharacteristicProperties { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties#Discussion)

The properties of a characteristic determine the access to and use of the characteristic’s value and descriptors. For a list of the possible values representing the properties of a characteristic, see [`CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties).
特性的属性决定了对特性的值和描述符的访问和使用。有关表示特征属性的可能值的列表，请参见 `CBCharacteristicProperties` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties#see-also)

### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties#Accessing-Characteristic-Data)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value)

The value of the characteristic.
特性的值。

[`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors)

A list of the descriptors discovered in this characteristic.
在此特征中发现的描述符的列表。

[`struct CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties)

Values that represent the possible properties of a characteristic.
表示特性的可能属性的值。

[`var isNotifying: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying)

A Boolean value that indicates whether the characteristic is currently notifying a subscribed central of its value.
一个布尔值，指示特征当前是否正在向订阅中心通知其值。

[`var isBroadcasted: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted)

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.
