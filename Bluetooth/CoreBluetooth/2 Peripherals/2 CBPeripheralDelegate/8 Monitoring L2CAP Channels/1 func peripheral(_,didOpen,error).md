Instance Method Instance 方法

# peripheral(_:didOpen:error:) 

Delivers the result of an attempt to open an L2CAP channel.
提供尝试打开 L2CAP 通道的结果。

iOS 11.0+ ｜ iPadOS 11.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 11.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didOpen channel: CBL2CAPChannel?,
    error: (any Error)?
)
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didopen:error:)#Discussion)

This method delivers the result of a previous call to [`openL2CAPChannel(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/openl2capchannel(_:)).
此方法提供上一个调用的结果 `openL2CAPChannel(_:)` 。
