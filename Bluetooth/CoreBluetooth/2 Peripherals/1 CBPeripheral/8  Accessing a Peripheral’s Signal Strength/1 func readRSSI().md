Instance Method Instance 方法

# readRSSI() 

Retrieves the current RSSI value for the peripheral while connected to the central manager.
在连接到中央管理器时检索外围设备的当前 RSSI 值。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func readRSSI()
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()#Discussion)

On macOS, when you call this method to retrieve the Received Signal Strength Indicator (RSSI) of the peripheral while connected to the central manager, the peripheral calls the [`peripheralDidUpdateRSSI(_:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:)) method of its delegate object. If retrieving the RSSI value of the peripheral succeeds, you can access it through the peripheral’s [`rssi`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/rssi) property.
在 macOS 上，当您调用此方法以检索连接到中央管理器时外围设备的接收信号强度指示器 （RSSI） 时，外设将调用其委托对象 `peripheralDidUpdateRSSI(_:error:)` 的方法。如果检索外设的 RSSI 值成功，则可以通过外设 `rssi` 的属性访问它。

On iOS and tvOS, when you call this method to retrieve the RSSI of the peripheral while connected to the central manager, the peripheral calls the [`peripheral(_:didReadRSSI:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:)) method of its delegate object, which includes the RSSI value as a parameter.
在 iOS 和 Apple tvOS 上，当您调用此方法以在连接到中央管理器时检索外围设备的 RSSI 时，外设将调用其委托对象 `peripheral(_:didReadRSSI:error:)` 的方法，其中包括 RSSI 值作为参数。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()#see-also)

### [Accessing a Peripheral’s Signal Strength 访问外设的信号强度](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi()#Accessing-a-Peripherals-Signal-Strength)

[`var rssi: NSNumber?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/rssi)

The Received Signal Strength Indicator (RSSI), in decibels, of the peripheral.
外设的接收信号强度指示器 （RSSI），以分贝为单位。

Deprecated 荒废的
