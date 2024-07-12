Instance Property 实例属性

# value 

The value of the characteristic.
特性的值。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var value: Data? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value#Discussion)

This property contains the value of the characteristic. For example, a temperature measurement characteristic of a health thermometer service may have a value that indicates a temperature in Celsius.
此属性包含特征的值。例如，健康温度计服务的温度测量特性可以具有指示以摄氏度为单位的温度的值。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value#see-also)

### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value#Accessing-Characteristic-Data)

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

[`var isBroadcasted: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted)

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.
