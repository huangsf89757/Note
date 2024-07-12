Instance Method Instance 方法

# retrieveConnectedPeripherals(withServices:) 

Returns a list of the peripherals connected to the system whose services match a given set of criteria.
返回连接到系统的外围设备的列表，这些外围设备的服务与一组给定的条件匹配。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func retrieveConnectedPeripherals(withServices serviceUUIDs: [CBUUID]) -> [CBPeripheral]
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:)#parameters)

- `serviceUUIDs`

  A list of service UUIDs, represented by [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects. 服务 UUID 的列表，由 `CBUUID` 对象表示。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:)#return-value)

A list of the peripherals that are currently connected to the system and that contain any of the services specified in the `serviceUUID` parameter.
当前连接到系统且包含 `serviceUUID` 参数中指定的任何服务的外围设备的列表。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:)#Discussion)

The list of connected peripherals can include those that other apps have connected. You need to connect these peripherals locally using the [`connect(_:options:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:)) method before using them.
连接的外围设备列表可以包括其他应用已连接的外围设备。在使用这些外围设备之前，您需要使用该 `connect(_:options:)` 方法在本地连接它们。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:)#see-also)

### [Retrieving Lists of Peripherals 检索外围设备列表](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:)#Retrieving-Lists-of-Peripherals)

[`func retrievePeripherals(withIdentifiers: [UUID\]) -> [CBPeripheral]`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveperipherals(withidentifiers:))

Returns a list of known peripherals by their identifiers.
按标识符返回已知外围设备的列表。
