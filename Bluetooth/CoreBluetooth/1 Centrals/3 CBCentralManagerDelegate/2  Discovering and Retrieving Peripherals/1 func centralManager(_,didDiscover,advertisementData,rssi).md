Instance Method Instance 方法

# centralManager(_:didDiscover:advertisementData:rssi:) 

Tells the delegate the central manager discovered a peripheral while scanning for devices.
告诉委托中央管理器在扫描设备时发现了外围设备。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func centralManager(
    _ central: CBCentralManager,
    didDiscover peripheral: CBPeripheral,
    advertisementData: [String : Any],
    rssi RSSI: NSNumber
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:)#parameters)

- `central`

  The central manager that provides the update. 提供更新的中央管理器。

- `peripheral`

  The discovered peripheral. 发现的外围设备。

- `advertisementData`

  A dictionary containing any advertisement data. 包含任何播发数据的字典。

- `RSSI`

  The current received signal strength indicator (RSSI) of the peripheral, in decibels. 外设的电流接收信号强度指示器 （RSSI），以分贝为单位。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:)#Discussion)

You can access the advertisement data with the keys listed in [Advertisement Data Retrieval Keys](https://developer.apple.com/documentation/corebluetooth/advertisement-data-retrieval-keys). You must retain a local copy of the peripheral if you want to perform commands on it. Use the RSSI data to determine the proximity of a discoverable peripheral device, and whether you want to connect to it automatically.
您可以使用播发数据检索密钥中列出的密钥访问播发数据。如果要对外围设备执行命令，则必须保留外围设备的本地副本。使用 RSSI 数据确定可发现的外围设备的距离，以及是否要自动连接到该外围设备。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:)#see-also)

### [Discovering and Retrieving Peripherals 发现和检索外围设备](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:)#Discovering-and-Retrieving-Peripherals)



Advertisement Data Retrieval Keys
播发数据检索密钥

Keys used to specify items in a dictionary of peripheral advertisement data.
用于指定外围通告数据字典中的项的键。
