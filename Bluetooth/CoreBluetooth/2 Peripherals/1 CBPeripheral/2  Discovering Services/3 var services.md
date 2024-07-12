Instance Property Instance 属性

# services 服务业

A list of a peripheral’s discovered services.
外围设备发现的服务的列表。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var services: [CBService]? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services#Discussion)

Returns an array of services (represented by [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice) objects) that successful call to the [`discoverServices(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)) method discovered. If you haven’t yet called the [`discoverServices(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)) method to discover the services of the peripheral, or if there was an error in doing so, the value of this property is `nil`.
返回成功调用所发现 `discoverServices(_:)` 方法的服务数组（由 `CBService` 对象表示）。如果尚未调用该 `discoverServices(_:)` 方法来发现外围设备的服务，或者在调用时出错，则此属性的值为 `nil` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services#see-also)

### [Discovering Services 发现服务](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services#Discovering-Services)

[`func discoverServices([CBUUID\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:))

Discovers the specified services of the peripheral.
发现外围设备的指定服务。

[`func discoverIncludedServices([CBUUID\]?, for: CBService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverincludedservices(_:for:))

Discovers the specified included services of a previously-discovered service.
发现以前发现的服务的指定包含的服务。
