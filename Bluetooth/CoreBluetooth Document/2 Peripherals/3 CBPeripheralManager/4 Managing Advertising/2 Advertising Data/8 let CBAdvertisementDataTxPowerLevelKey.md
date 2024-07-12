Global Variable 全局变量

# CBAdvertisementDataTxPowerLevelKey

The transmit power of a peripheral.
外设的发射功率。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
let CBAdvertisementDataTxPowerLevelKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatatxpowerlevelkey#Discussion)

The value associated with this key is an instance of [`NSNumber`](https://developer.apple.com/documentation/foundation/nsnumber).
与此键关联的值是 `NSNumber` 的实例。

This key and value are available if the peripheral provides its transmitting power level in its advertising packet. You can calculate the path loss by comparing the RSSI value with the transmitting power level.
如果外设在其通告数据包中提供其发射功率级别，则此键和值可用。您可以通过将RSSI值与发射功率电平进行比较来计算路径损耗。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatatxpowerlevelkey#see-also)

### [Advertisement Keys 播发键](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatatxpowerlevelkey#Advertisement-Keys)

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

[`let CBAdvertisementDataOverflowServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataoverflowserviceuuidskey)

An array of UUIDs found in the overflow area of the advertisement data.
在播发数据的溢出区域中找到的 UUID 数组。

[`let CBAdvertisementDataIsConnectable: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataisconnectable)

A Boolean value that indicates whether the advertising event type is connectable.
一个 Boolean 值，该值指示广告事件类型是否可连接。

[`let CBAdvertisementDataSolicitedServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatasolicitedserviceuuidskey)

An array of solicited service UUIDs.
请求的服务 UUID 数组。
