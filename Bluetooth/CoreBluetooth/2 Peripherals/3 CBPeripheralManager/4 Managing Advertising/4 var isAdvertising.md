Instance Property Instance 属性

# isAdvertising 是广告

A Boolean value that indicates whether the peripheral is advertising data.
一个 Boolean 值，该值指示外围设备是否为播发数据。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
var isAdvertising: Bool { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/isadvertising#Discussion)

This value is [`true`](https://developer.apple.com/documentation/swift/true) if the peripheral is advertising data as a result of successfully calling the [`startAdvertising(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:)) method. The value is [`false`](https://developer.apple.com/documentation/swift/false) if the peripheral is no longer advertising its data.
`true` 如果外围设备因成功调用该 `startAdvertising(_:)` 方法而播发数据，则此值为值。该值是 `false` 外围设备不再通告其数据的情况。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/isadvertising#see-also)

### [Managing Advertising 管理广告](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/isadvertising#Managing-Advertising)

[`func startAdvertising([String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:))

Advertises peripheral manager data.
播发外设管理器数据。



Advertising Data 广告数据

[`func stopAdvertising()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/stopadvertising())

Stops advertising peripheral manager data.
停止通告外设管理器数据。
