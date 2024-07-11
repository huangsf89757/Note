Instance Method Instance 方法

# retrievePeripherals(withIdentifiers:) 

Returns a list of known peripherals by their identifiers.
按标识符返回已知外围设备的列表。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func retrievePeripherals(withIdentifiers identifiers: [UUID]) -> [CBPeripheral]
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveperipherals(withidentifiers:)#parameters)

- `identifiers`

  A list of peripheral identifiers (represented by [`NSUUID`](https://developer.apple.com/documentation/foundation/nsuuid) objects) from which [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) objects can be retrieved. 

  可从中检索 `CBPeripheral` 对象的外围标识符（由 `NSUUID` 对象表示）的列表。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveperipherals(withidentifiers:)#return-value)

A list of peripherals that the central manager is able to match to the provided identifiers.
中央管理器能够与提供的标识符匹配的外围设备列表。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveperipherals(withidentifiers:)#see-also)

### [Retrieving Lists of Peripherals 检索外围设备列表](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveperipherals(withidentifiers:)#Retrieving-Lists-of-Peripherals)

[`func retrieveConnectedPeripherals(withServices: [CBUUID\]) -> [CBPeripheral]`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:))

Returns a list of the peripherals connected to the system whose services match a given set of criteria.
返回连接到系统的外围设备的列表，这些外围设备的服务与一组给定的条件匹配。
