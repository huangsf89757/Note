Instance Method Instance 方法

# startAdvertising(_:) 

Advertises peripheral manager data.
播发外设管理器数据。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func startAdvertising(_ advertisementData: [String : Any]?)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)#parameters)

- `advertisementData`

  An optional dictionary containing the data you want to advertise. The peripheral manager only supports two keys: [`CBAdvertisementDataLocalNameKey`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatalocalnamekey) and [`CBAdvertisementDataServiceUUIDsKey`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataserviceuuidskey). 

  包含要播发的数据的可选字典。外设管理器仅支持两个键： `CBAdvertisementDataLocalNameKey` 和 `CBAdvertisementDataServiceUUIDsKey` 。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)#Discussion)

When you start advertising peripheral data, the peripheral manager calls the [`peripheralManagerDidStartAdvertising(_:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidstartadvertising(_:error:)) method of its delegate object.
当您开始播发外设数据时，外设管理器将调用其委托对象 `peripheralManagerDidStartAdvertising(_:error:)` 的方法。

Core Bluetooth advertises data on a “best effort” basis, due to limited space and because there may be multiple apps advertising simultaneously. While in the foreground, your app can use up to 28 bytes of space in the initial advertisement data for any combination of the supported advertising data keys. If no this space remains, there’s an additional 10 bytes of space in the scan response, usable only for the local name (represented by the value of the [`CBAdvertisementDataLocalNameKey`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatalocalnamekey) key). Note that these sizes don’t include the 2 bytes of header information required for each new data type.
Core Bluetooth 在“尽最大努力”的基础上播发数据，因为空间有限，并且可能同时有多个应用程序播发。在前台，应用最多可以在初始播发数据中使用 28 个字节的空间，用于支持的播发数据密钥的任意组合。如果没有此空间，则扫描响应中还有额外的 10 个字节的空间，仅可用于本地名称（由 `CBAdvertisementDataLocalNameKey` 键的值表示）。请注意，这些大小不包括每个新数据类型所需的 2 个字节的标头信息。

Any service UUIDs contained in the value of the [`CBAdvertisementDataServiceUUIDsKey`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataserviceuuidskey) key that don’t fit in the allotted space go to a special “overflow” area. These services are discoverable only by an iOS device explicitly scanning for them.
`CBAdvertisementDataServiceUUIDsKey` 密钥值中包含的任何服务 UUID 如果不适合分配的空间，都会进入特殊的“溢出”区域。这些服务只能由显式扫描它们的 iOS 设备发现。

While your app is in the background, the local name isn’t advertised and all service UUIDs are in the overflow area.
当应用在后台时，不会播发本地名称，并且所有服务 UUID 都位于溢出区域中。

For details about the format of advertising and response data, see the Bluetooth 4.0 specification, Volume 3, Part C, Section 11.
有关广告和响应数据格式的详细信息，请参阅蓝牙 4.0 规范，第 3 卷，C 部分，第 11 节。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)#topics)

### [Related Documentation 相关主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)#Related-Documentation)

#### [`let CBAdvertisementDataOverflowServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataoverflowserviceuuidskey)

An array of UUIDs found in the overflow area of the advertisement data.
在播发数据的溢出区域中找到的 UUID 数组。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)#see-also)

### [Managing Advertising 管理广告](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)#Managing-Advertising)



Advertising Data 广告数据

[`func stopAdvertising()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/stopadvertising())

Stops advertising peripheral manager data.
停止通告外设管理器数据。

[`var isAdvertising: Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/isadvertising)

A Boolean value that indicates whether the peripheral is advertising data.
一个 Boolean 值，该值指示外围设备是否为播发数据。
