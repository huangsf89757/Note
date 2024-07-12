Instance Property 实例属性

# includedServices 包含的服务

A list of included services.
包含的服务列表。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var includedServices: [CBService]? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/includedservices#Discussion)

A service of a peripheral may contain a reference to other services that are available on the peripheral. These other services are the included services of the service.
外围设备的服务可以包含对外围设备上可用的其他服务的引用。这些其他服务是服务的包含服务。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/includedservices#see-also)

### [Managing a Mutable Service 管理可变服务](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/includedservices#Managing-a-Mutable-Service)

[`var characteristics: [CBCharacteristic\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/characteristics)

A list of characteristics of a service.
服务的特性列表。
