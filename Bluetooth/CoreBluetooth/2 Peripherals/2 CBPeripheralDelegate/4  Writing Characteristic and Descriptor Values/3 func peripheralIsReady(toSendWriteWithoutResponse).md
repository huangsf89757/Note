Instance Method Instance 方法

# peripheralIsReady(toSendWriteWithoutResponse:) peripheralIsReady（toSendWriteWithoutResponse：）

Tells the delegate that a peripheral is again ready to send characteristic updates.
告知委托外围设备再次准备好发送特征更新。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheralIsReady(toSendWriteWithoutResponse peripheral: CBPeripheral)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:)#parameters)

- `peripheral`

  The peripheral providing this update. 

  提供此更新的外围设备。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:)#Discussion)

The peripheral calls this delegate method after a failed call to [`writeValue(_:for:type:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:)), once `peripheral` is ready to send characteristic value updates.
外设在调用 `writeValue(_:for:type:)` 失败后调用此委托方法，一旦 `peripheral` 准备好发送特征值更新。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:)#see-also)

### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:)#Writing-Characteristic-and-Descriptor-Values)

[`func peripheral(CBPeripheral, didWriteValueFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-4f5ea)

Tells the delegate that the peripheral successfully set a value for the characteristic.
告知委托外设已成功设置特征值。

[`func peripheral(CBPeripheral, didWriteValueFor: CBDescriptor, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3)

Tells the delegate that the peripheral successfully set a value for the descriptor.
告知委托外围设备已成功为描述符设置值。
