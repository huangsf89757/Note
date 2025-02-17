Instance Method Instance 方法

# stopScan() 

Asks the central manager to stop scanning for peripherals.
要求中央管理器停止扫描外围设备。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func stopScan()
```



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/stopscan()#see-also)

### [Scanning or Stopping Scans of Peripherals 扫描或停止外围设备的扫描](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/stopscan()#Scanning-or-Stopping-Scans-of-Peripherals)

[`func scanForPeripherals(withServices: [CBUUID\]?, options: [String : Any]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:))

Scans for peripherals that are advertising services.
扫描作为广告服务的外围设备。



Peripheral Scanning Options
外围设备扫描选项

Keys used to pass options when scanning for peripherals.
用于在扫描外围设备时传递选项的键。

[`var isScanning: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/isscanning)

A Boolean value that indicates whether the central is currently scanning.
一个 Boolean 值，该值指示中心当前是否正在扫描。
