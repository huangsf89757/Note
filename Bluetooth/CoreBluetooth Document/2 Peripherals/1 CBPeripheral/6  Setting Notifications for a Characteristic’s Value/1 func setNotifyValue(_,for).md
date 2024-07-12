Instance Method Instance 方法

# setNotifyValue(_:for:) 

Sets notifications or indications for the value of a specified characteristic.
设置指定特征值的通知或指示。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func setNotifyValue(
    _ enabled: Bool,
    for characteristic: CBCharacteristic
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)#parameters)

- `enabled`

  A Boolean value that indicates whether to receive notifications or indications whenever the characteristic’s value changes. [`true`](https://developer.apple.com/documentation/swift/true) if you want to enable notifications or indications for the characteristic’s value. [`false`](https://developer.apple.com/documentation/swift/false) if you don’t want to receive notifications or indications whenever the characteristic’s value changes. 一个 Boolean 值，该值指示在特征值更改时是否接收通知或指示。 `true` 如果要启用特征值的通知或指示。 `false` 如果您不希望在特征值更改时收到通知或指示。

- `characteristic`

  The specified characteristic. 指定的特征。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)#Discussion)

When you enable notifications for the characteristic’s value, the peripheral calls the [`peripheral(_:didUpdateNotificationStateFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatenotificationstatefor:error:)) method of its delegate object to indicate if the action succeeded. If successful, the peripheral then calls the [`peripheral(_:didUpdateValueFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna) method of its delegate object whenever the characteristic value changes. Because the peripheral chooses when it sends an update, your app should prepare to handle them as long as notifications or indications remain enabled. If the specified characteristic’s configuration allows both notifications and indications, calling this method enables notifications only. You can disable notifications and indications for a characteristic’s value by calling this method with the `enabled` parameter set to [`false`](https://developer.apple.com/documentation/swift/false).
当您为特征的值启用通知时，外围设备将调用其委托对象 `peripheral(_:didUpdateNotificationStateFor:error:)` 的方法以指示操作是否成功。如果成功，则每当特征值发生更改时，外设就会调用其委托对象 `peripheral(_:didUpdateValueFor:error:)` 的方法。由于外围设备选择何时发送更新，因此只要通知或指示保持启用状态，应用就应准备好处理更新。如果指定特征的配置同时允许通知和指示，则调用此方法仅启用通知。您可以通过调用此方法并将 `enabled` 参数设置为 `false` 来禁用特征值的通知和指示。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)#topics)

### [Related Documentation 相关主题](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)#Related-Documentation)

[`let CBConnectPeripheralOptionNotifyOnNotificationKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyonnotificationkey)

A Boolean value that specifies whether the system should display an alert for any notification sent by a peripheral.
一个 Boolean 值，该值指定系统是否应针对外围设备发送的任何通知显示警报。
