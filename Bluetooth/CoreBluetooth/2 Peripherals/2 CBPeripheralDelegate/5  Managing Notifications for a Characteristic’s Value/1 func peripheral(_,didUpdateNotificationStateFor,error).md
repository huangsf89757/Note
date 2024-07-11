Instance Method Instance 方法

# peripheral(_:didUpdateNotificationStateFor:error:) 

Tells the delegate that the peripheral received a request to start or stop providing notifications for a specified characteristic’s value.
告知委托外围设备收到开始或停止为指定特征值提供通知的请求。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didUpdateNotificationStateFor characteristic: CBCharacteristic,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatenotificationstatefor:error:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `characteristic`

  The characteristic for which to configure value notifications. 

  要为其配置值通知的特征。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatenotificationstatefor:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`setNotifyValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)) method. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `setNotifyValue(_:for:)` 方法时调用该方法。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。
