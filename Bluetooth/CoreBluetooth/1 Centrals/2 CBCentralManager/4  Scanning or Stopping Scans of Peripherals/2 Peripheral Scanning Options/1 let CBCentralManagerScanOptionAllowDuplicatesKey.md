Global Variable 全局变量

# CBCentralManagerScanOptionAllowDuplicatesKey

A Boolean value that specifies whether the scan should run without duplicate filtering.
一个 Boolean 值，该值指定是否应在不进行重复筛选的情况下运行扫描。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.0+macOS 10.10+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
let CBCentralManagerScanOptionAllowDuplicatesKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionallowduplicateskey#Discussion)

The value for this key is an [`NSNumber`](https://developer.apple.com/documentation/foundation/nsnumber) object. If [`true`](https://developer.apple.com/documentation/swift/true), the central disables filtering and generates a discovery event each time it receives an advertising packet from the peripheral. If [`false`](https://developer.apple.com/documentation/swift/false) (the default), the central coalesces multiple discoveries of the same peripheral into a single discovery event.
此键的值是一个 `NSNumber` 对象。如果 `true` ，则中心禁用过滤，并在每次从外围设备接收通告数据包时生成发现事件。如果 `false` （默认值），则中心将同一外围设备的多个发现合并为单个发现事件。

> Important 重要
>
> Disabling this filtering can have an adverse effect on battery life; use it only if necessary.
> 禁用此过滤可能会对电池寿命产生不利影响;仅在必要时才使用它。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionallowduplicateskey#see-also)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionallowduplicateskey#Constants)

[`let CBCentralManagerScanOptionSolicitedServiceUUIDsKey: String`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerscanoptionsolicitedserviceuuidskey)

An array of service UUIDs that you want to scan for.
要扫描的服务 UUID 数组。
