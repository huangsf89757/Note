Instance Method Instance 方法

# peripheral(_:didReadRSSI:error:) 

Tells the delegate that retrieving the value of the peripheral’s current Received Signal Strength Indicator (RSSI) succeeded.
告知委托已成功检索外设的当前接收信号强度指示器 （RSSI） 的值。

iOS 8.0+ iOS的8.0 +iPadOS 8.0+Mac Catalyst 13.1+macOS 10.13+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didReadRSSI RSSI: NSNumber,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `RSSI`

  The RSSI, in decibels, of the peripheral. 

  外围设备的 RSSI，以分贝为单位。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`readRSSI()`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()) method, while the peripheral is connected to the central manager. If successful, the `error` parameter is `nil` and the parameter `RSSI` reports the peripheral’s signal strength, in decibels. If unsuccessful, the `error` parameter returns the cause of the failure.
当应用调用该 `readRSSI()` 方法时，核心蓝牙会调用此方法，而外围设备将连接到中央管理器。如果成功，则 `error` 参数为 `nil` ，该参数 `RSSI` 报告外设的信号强度（以分贝为单位）。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)#see-also)

### [Retrieving a Peripheral’s RSSI Data 检索外设的 RSSI 数据](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)#Retrieving-a-Peripherals-RSSI-Data)

[`func peripheralDidUpdateRSSI(CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:))

Tells the delegate that retrieving the value of the peripheral’s current Received Signal Strength Indicator (RSSI) succeeded.
告知委托已成功检索外设的当前接收信号强度指示器 （RSSI） 的值。

**Required 必填**

`Deprecated 荒废的`
