Global Variable 全局变量

# CBAdvertisementDataOverflowServiceUUIDsKey

An array of UUIDs found in the overflow area of the advertisement data.
在播发数据的溢出区域中找到的 UUID 数组。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
let CBAdvertisementDataOverflowServiceUUIDsKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataoverflowserviceuuidskey#Discussion)

The value associated with this key is an array of one or more [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects, representing [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice) UUIDs.
与此键关联的值是一个或多个 `CBUUID` 对象的数组，表示 `CBService` UUID。

Because data stored in this area results from not fitting in the main advertisement, UUIDs listed here are “best effort” and may not always be accurate. For details about the overflow area of advertisement data, see the [`startAdvertising(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)) method in [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager).
由于存储在此区域中的数据是由于不适合主广告，因此此处列出的 UUID 是“尽力而为”，可能并不总是准确的。有关通告数据溢出区域的详细信息，请参阅 中 `startAdvertising(_:)` `CBPeripheralManager` 的方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataoverflowserviceuuidskey#see-also)

### [Advertisement Keys 播发键](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataoverflowserviceuuidskey#Advertisement-Keys)

[`let CBAdvertisementDataLocalNameKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatalocalnamekey)

The local name of a peripheral.
外围设备的本地名称。

[`let CBAdvertisementDataManufacturerDataKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatamanufacturerdatakey)

The manufacturer data of a peripheral.
外围设备的制造商数据。

[`let CBAdvertisementDataServiceDataKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataservicedatakey)

A dictionary that contains service-specific advertisement data.
包含特定于服务的播发数据的字典。

[`let CBAdvertisementDataServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataserviceuuidskey)

An array of service UUIDs.
服务 UUID 的数组。

[`let CBAdvertisementDataTxPowerLevelKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatatxpowerlevelkey)

The transmit power of a peripheral.
外设的发射功率。

[`let CBAdvertisementDataIsConnectable: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataisconnectable)

A Boolean value that indicates whether the advertising event type is connectable.
一个 Boolean 值，该值指示广告事件类型是否可连接。

[`let CBAdvertisementDataSolicitedServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatasolicitedserviceuuidskey)

An array of solicited service UUIDs.
请求的服务 UUID 数组。
