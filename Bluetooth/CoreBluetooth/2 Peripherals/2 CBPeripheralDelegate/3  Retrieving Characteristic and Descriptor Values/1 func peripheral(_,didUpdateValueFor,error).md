Instance Method Instance 方法

# peripheral(_:didUpdateValueFor:error:) 外设（_：didUpdateValueFor：error：）

Tells the delegate that retrieving the specified characteristic’s value succeeded, or that the characteristic’s value changed.
告知委托检索指定特征的值已成功，或者特征的值已更改。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didUpdateValueFor characteristic: CBCharacteristic,
    error: (any Error)?
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `characteristic`

  The characteristic containing the value. 

  包含值的特征。

- `error`

  The reason the call failed, or `nil` if no error occurred.

   调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna#Discussion)

Core Bluetooth invokes this method when your app calls the [`readValue(for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr) method. A peripheral also invokes this method to notify your app of a change to the value of the characteristic for which the app previously enabled notifications by calling [`setNotifyValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)). If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `readValue(for:)` 方法时调用该方法。外围设备还调用此方法，以通知应用之前通过调用 `setNotifyValue(_:for:)` 为其启用通知的特征值的更改。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna#see-also)

### [Retrieving Characteristic and Descriptor Values 检索特征和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna#Retrieving-Characteristic-and-Descriptor-Values)

[`func peripheral(CBPeripheral, didUpdateValueFor: CBDescriptor, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1t3wm)

Tells the delegate that retrieving a specified characteristic descriptor’s value succeeded.
告知委托检索指定特征描述符的值已成功。
