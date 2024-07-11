Global Variable 全局变量

# CBAdvertisementDataIsConnectable

A Boolean value that indicates whether the advertising event type is connectable.
一个 Boolean 值，该值指示广告事件类型是否可连接。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
let CBAdvertisementDataIsConnectable: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataisconnectable#Discussion)

The value for this key is an [`NSNumber`](https://developer.apple.com/documentation/foundation/nsnumber) object. You can use this value to determine whether your app can currently connect to a peripheral.
此键的值是一个 `NSNumber` 对象。可以使用此值来确定应用当前是否可以连接到外围设备。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataisconnectable#see-also)

### [Advertisement Keys 播发键](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataisconnectable#Advertisement-Keys)

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

[`let CBAdvertisementDataTxPowerLevelKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatatxpowerlevelkey)

The transmit power of a peripheral.
外设的发射功率。

[`let CBAdvertisementDataSolicitedServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatasolicitedserviceuuidskey)

An array of solicited service UUIDs.
请求的服务 UUID 数组。
