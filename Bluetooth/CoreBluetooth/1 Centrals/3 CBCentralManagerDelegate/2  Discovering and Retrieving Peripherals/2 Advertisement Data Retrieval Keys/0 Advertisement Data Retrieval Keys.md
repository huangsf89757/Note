API Collection API 集合

# Advertisement Data Retrieval Keys 播发数据检索密钥

Keys used to specify items in a dictionary of peripheral advertisement data.
用于指定外围通告数据字典中的项的键。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/advertisement-data-retrieval-keys#topics)

### [Advertisement Keys 播发键](https://developer.apple.com/documentation/corebluetooth/advertisement-data-retrieval-keys#Advertisement-Keys)

#### [`let CBAdvertisementDataLocalNameKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatalocalnamekey)

The local name of a peripheral.
外围设备的本地名称。



#### [`let CBAdvertisementDataManufacturerDataKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatamanufacturerdatakey)

The manufacturer data of a peripheral.
外围设备的制造商数据。



#### [`let CBAdvertisementDataServiceDataKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataservicedatakey)

A dictionary that contains service-specific advertisement data.
包含特定于服务的播发数据的字典。



#### [`let CBAdvertisementDataServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataserviceuuidskey)

An array of service UUIDs.
服务 UUID 的数组。



#### [`let CBAdvertisementDataOverflowServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataoverflowserviceuuidskey)

An array of UUIDs found in the overflow area of the advertisement data.
在播发数据的溢出区域中找到的 UUID 数组。



#### [`let CBAdvertisementDataTxPowerLevelKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatatxpowerlevelkey)

The transmit power of a peripheral.
外设的发射功率。



#### [`let CBAdvertisementDataIsConnectable: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdataisconnectable)

A Boolean value that indicates whether the advertising event type is connectable.
一个 Boolean 值，该值指示广告事件类型是否可连接。



#### [`let CBAdvertisementDataSolicitedServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbadvertisementdatasolicitedserviceuuidskey)

An array of solicited service UUIDs.
请求的服务 UUID 数组。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/advertisement-data-retrieval-keys#see-also)

### [Discovering and Retrieving Peripherals 发现和检索外围设备](https://developer.apple.com/documentation/corebluetooth/advertisement-data-retrieval-keys#Discovering-and-Retrieving-Peripherals)

[`func centralManager(CBCentralManager, didDiscover: CBPeripheral, advertisementData: [String : Any\], rssi: NSNumber)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:))

Tells the delegate the central manager discovered a peripheral while scanning for devices.
告诉委托中央管理器在扫描设备时发现了外围设备。

**Required 必填**
