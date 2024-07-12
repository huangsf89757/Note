API Collection API 集合

# Peripheral Scanning Options 

Keys used to pass options when scanning for peripherals.
用于在扫描外围设备时传递选项的键。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/peripheral-scanning-options#topics)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/peripheral-scanning-options#Constants)

#### [`let CBCentralManagerScanOptionAllowDuplicatesKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionallowduplicateskey)

A Boolean value that specifies whether the scan should run without duplicate filtering.
一个 Boolean 值，该值指定是否应在不进行重复筛选的情况下运行扫描。



#### [`let CBCentralManagerScanOptionSolicitedServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionsolicitedserviceuuidskey)

An array of service UUIDs that you want to scan for.
要扫描的服务 UUID 数组。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/peripheral-scanning-options#see-also)

### [Scanning or Stopping Scans of Peripherals 扫描或停止外围设备的扫描](https://developer.apple.com/documentation/corebluetooth/peripheral-scanning-options#Scanning-or-Stopping-Scans-of-Peripherals)

[`func scanForPeripherals(withServices: [CBUUID\]?, options: [String : Any]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:))

Scans for peripherals that are advertising services.
扫描作为广告服务的外围设备。

[`func stopScan()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/stopscan())

Asks the central manager to stop scanning for peripherals.
要求中央管理器停止扫描外围设备。

[`var isScanning: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/isscanning)

A Boolean value that indicates whether the central is currently scanning.
一个 Boolean 值，该值指示中心当前是否正在扫描。
