Instance Property 实例属性

# characteristics 特性

A list of characteristics discovered in this service.
在此服务中发现的特征列表。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var characteristics: [CBCharacteristic]? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics#Discussion)

This array contains [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic) objects that represent a service’s characteristics. Characteristics provide further details about a peripheral’s service. For example, a heart rate service may contain one characteristic that describes the intended body location of the device’s heart rate sensor, while another characteristic transmits heart rate measurement data.
此数组包含表示服务特征的 `CBCharacteristic` 对象。特征提供有关外围设备服务的进一步详细信息。例如，心率服务可以包含描述设备的心率传感器的预期身体位置的一个特性，而另一个特性传输心率测量数据。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics#see-also)

### [Accessing Service Data 服务数据](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics#Accessing-Service-Data)

[`var includedServices: [CBService\]?`](https://developer.apple.com/documentation/corebluetooth/cbservice/includedservices)

A list of included services discovered in this service.
在此服务中发现的包含服务的列表。
