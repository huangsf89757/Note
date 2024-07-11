Instance Property Instance 属性

# isScanning 

A Boolean value that indicates whether the central is currently scanning.
一个 Boolean 值，该值指示中心当前是否正在扫描。

iOS 9.0+ iOS的9.0 +iPadOS 9.0+Mac Catalyst 13.1+macOS 10.13+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
var isScanning: Bool { get }
```



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/isscanning#see-also)

### [Scanning or Stopping Scans of Peripherals 扫描或停止外围设备的扫描](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/isscanning#Scanning-or-Stopping-Scans-of-Peripherals)

[`func scanForPeripherals(withServices: [CBUUID\]?, options: [String : Any]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:))

Scans for peripherals that are advertising services.
扫描作为广告服务的外围设备。



Peripheral Scanning Options
外围设备扫描选项

Keys used to pass options when scanning for peripherals.
用于在扫描外围设备时传递选项的键。

[`func stopScan()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/stopscan())

Asks the central manager to stop scanning for peripherals.
要求中央管理器停止扫描外围设备。
