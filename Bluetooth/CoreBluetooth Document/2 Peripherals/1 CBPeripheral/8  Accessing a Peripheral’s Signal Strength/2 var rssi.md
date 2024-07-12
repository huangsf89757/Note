Instance Property Instance 属性

# rssi 

The Received Signal Strength Indicator (RSSI), in decibels, of the peripheral.
外设的接收信号强度指示器 （RSSI），以分贝为单位。

iOS 5.0–8.0`Deprecated` ｜ iPadOS 5.0–8.0`Deprecated` ｜ Mac Catalyst 13.1–13.1`Deprecated` ｜ macOS 10.7–10.13`Deprecated` ｜ tvOS 9.0+ ｜ visionOS 1.0–1.0`Deprecated` ｜ watchOS 2.0–2.0`Deprecated`

```
var rssi: NSNumber? { get }
```

`Deprecated 荒废的`

On iOS and tvOS, when you call the [`readRSSI()`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()) method, the system returns the RSSI as a parameter in a call to the delegate’s [`peripheral(_:didReadRSSI:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)) method. Use that value instead.
在 iOS 和 Apple tvOS 上，当您调用该 `readRSSI()` 方法时，系统会在调用委托 `peripheral(_:didReadRSSI:error:)` 的方法时将 RSSI 作为参数返回。请改用该值。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/rssi#Discussion)

Returns a number, in decibels, that indicates the RSSI of the peripheral while connected to the central manager. You can use a connected peripheral’s RSSI property to determine the peripheral’s proximity. The default value of this property is `nil`; the first successful call to [`readRSSI()`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()) sets its value.
返回一个数字（以分贝为单位），该数字指示外围设备在连接到中央管理器时的 RSSI。您可以使用连接的外围设备的 RSSI 属性来确定外围设备的邻近程度。此属性的默认值为 `nil` ;第一次成功调用以 `readRSSI()` 设置其值。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/rssi#see-also)

### [Accessing a Peripheral’s Signal Strength 访问外设的信号强度](https://developer.apple.com/documentation/corebluetooth/cbperipheral/rssi#Accessing-a-Peripherals-Signal-Strength)

[`func readRSSI()`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi())

Retrieves the current RSSI value for the peripheral while connected to the central manager.
在连接到中央管理器时检索外围设备的当前 RSSI 值。
