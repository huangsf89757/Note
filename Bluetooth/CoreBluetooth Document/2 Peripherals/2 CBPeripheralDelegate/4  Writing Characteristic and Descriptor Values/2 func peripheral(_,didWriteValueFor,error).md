# peripheral(_:didWriteValueFor:error:) 

Tells the delegate that the peripheral successfully set a value for the descriptor.
告知委托外围设备已成功为描述符设置值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didWriteValueFor descriptor: CBDescriptor,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `descriptor`

  The characteristic descriptor containing the value. 

  包含值的特征描述符。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3#Discussion)

Core Bluetooth invokes this method when your app calls the [`writeValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)) method. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `writeValue(_:for:)` 方法时调用该方法。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3#see-also)

### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3#Writing-Characteristic-and-Descriptor-Values)

[`func peripheral(CBPeripheral, didWriteValueFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-4f5ea)

Tells the delegate that the peripheral successfully set a value for the characteristic.
告知委托外设已成功设置特征值。

[`func peripheralIsReady(toSendWriteWithoutResponse: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:))

Tells the delegate that a peripheral is again ready to send characteristic updates.
告知委托外围设备再次准备好发送特征更新。
