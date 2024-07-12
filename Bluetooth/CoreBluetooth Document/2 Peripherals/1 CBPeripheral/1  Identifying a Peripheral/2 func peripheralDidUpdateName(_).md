Instance Method Instance 方法

# peripheralDidUpdateName(_:) 

Tells the delegate that a peripheral’s name changed.
告知代理外围设备的名称已更改。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheralDidUpdateName(_ peripheral: CBPeripheral)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:)#parameters)

- `peripheral`

  The peripheral providing this information. 提供此信息的外围设备。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:)#Discussion)

Core Bluetooth invokes this method whenever the peripheral’s Generic Access Profile (GAP) device name changes. Since a peripheral device can change its GAP device name, you can implement this method if your app needs to display the current name of the peripheral device.
每当外围设备的通用访问配置文件 （GAP） 设备名称发生更改时，核心蓝牙都会调用此方法。由于外围设备可以更改其 GAP 设备名称，因此，如果您的应用需要显示外围设备的当前名称，则可以实现此方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:)#see-also)

### [Monitoring Changes to a Peripheral’s Name or Services 监视对外围设备名称或服务的更改](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:)#Monitoring-Changes-to-a-Peripherals-Name-or-Services)

[`func peripheral(CBPeripheral, didModifyServices: [CBService\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didmodifyservices:))

Tells the delegate that a peripheral’s services changed.
告知代理外围设备的服务已更改。

**Required 必填**
