Instance Method Instance 方法

# peripheralDidUpdateRSSI(_:error:) 

Tells the delegate that retrieving the value of the peripheral’s current Received Signal Strength Indicator (RSSI) succeeded.
告知委托已成功检索外设的当前接收信号强度指示器 （RSSI） 的值。

iOS 5.0–8.0`Deprecated` ｜ iPadOS 5.0–8.0`Deprecated` ｜ Mac Catalyst 13.1–13.1`Deprecated` ｜ macOS 10.7–10.13`Deprecated` ｜ tvOS 9.0+visionOS 1.0–1.0`Deprecated` ｜ watchOS 2.0–2.0`Deprecated`

```
optional func peripheralDidUpdateRSSI(
    _ peripheral: CBPeripheral,
    error: (any Error)?
)
```

**Required 必填**

`Deprecated 荒废的`

in iOS and tvOS, use the [`peripheral(_:didReadRSSI:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)) method instead.
在 iOS 和 Apple tvOS 中，请改用该 `peripheral(_:didReadRSSI:error:)` 方法。



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`readRSSI()`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()) method, while the peripheral is connected to the central manager. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
当应用调用该 `readRSSI()` 方法时，核心蓝牙会调用此方法，而外围设备将连接到中央管理器。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:)#see-also)

### [Retrieving a Peripheral’s RSSI Data 检索外设的 RSSI 数据](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:)#Retrieving-a-Peripherals-RSSI-Data)

[`func peripheral(CBPeripheral, didReadRSSI: NSNumber, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:))

Tells the delegate that retrieving the value of the peripheral’s current Received Signal Strength Indicator (RSSI) succeeded.
告知委托已成功检索外设的当前接收信号强度指示器 （RSSI） 的值。
