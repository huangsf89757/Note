Global Variable 全局变量

# CBCentralManagerScanOptionSolicitedServiceUUIDsKey

An array of service UUIDs that you want to scan for.
要扫描的服务 UUID 数组。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
let CBCentralManagerScanOptionSolicitedServiceUUIDsKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionsolicitedserviceuuidskey#Discussion)

The array is an instance of [`NSArray`](https://developer.apple.com/documentation/foundation/nsarray), and uses [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects to represent the UUIDs to scan for.
该数组是 的 `NSArray` 实例，并使用 `CBUUID` 对象来表示要扫描的 UUID。

Specifying this scan option causes the central manager to also scan for peripherals soliciting any of the services contained in the array.
指定此扫描选项会导致中央管理器还扫描请求阵列中包含的任何服务的外围设备。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionsolicitedserviceuuidskey#see-also)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionsolicitedserviceuuidskey#Constants)

[`let CBCentralManagerScanOptionAllowDuplicatesKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionallowduplicateskey)

A Boolean value that specifies whether the scan should run without duplicate filtering.
一个 Boolean 值，该值指定是否应在不进行重复筛选的情况下运行扫描。
