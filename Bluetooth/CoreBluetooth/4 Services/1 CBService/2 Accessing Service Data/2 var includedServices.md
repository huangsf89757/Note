Instance Property 实例属性

# includedServices 包含的服务

A list of included services discovered in this service.
在此服务中发现的包含服务的列表。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var includedServices: [CBService]? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbservice/includedservices#Discussion)

This array contains [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice) objects that represent the included services of a service. A service of a peripheral may contain a reference to other services that are available on the peripheral. These other services are the included services of the service. You discover included services using the [`discoverIncludedServices(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverincludedservices(_:for:)) method of the [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class.
此数组包含 `CBService` 对象，表示服务中包含的服务。外围设备的服务可以包含对外围设备上可用的其他服务的引用。这些其他服务是服务的包含服务。您可以使用 `CBPeripheral` 类的 `discoverIncludedServices(_:for:)` 方法发现包含的服务。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbservice/includedservices#see-also)

### [Accessing Service Data 服务数据](https://developer.apple.com/documentation/corebluetooth/cbservice/includedservices#Accessing-Service-Data)

[`var characteristics: [CBCharacteristic\]?`](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics)

A list of characteristics discovered in this service.
在此服务中发现的特征列表。
