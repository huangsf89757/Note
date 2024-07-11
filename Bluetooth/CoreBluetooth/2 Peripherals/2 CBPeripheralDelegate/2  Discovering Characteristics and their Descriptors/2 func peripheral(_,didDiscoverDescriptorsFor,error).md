Instance Method Instance 方法

# peripheral(_:didDiscoverDescriptorsFor:error:) 

Tells the delegate that the peripheral found descriptors for a characteristic.
告诉委托外围设备找到了特征的描述符。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didDiscoverDescriptorsFor characteristic: CBCharacteristic,
    error: (any Error)?
)
```

**Required 必填**



## [Parameters](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `characteristic`

  The characteristic to which the characteristic descriptors belong. 

  特征描述符所属的特征。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`discoverDescriptors(for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:)) method. If the peripheral successfully discovers the descriptors of the specified characteristic, you can access them through the characteristic’s [`descriptors`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors) property. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `discoverDescriptors(for:)` 方法时调用该方法。如果外围设备成功发现指定特征的描述符，则可以通过特征的 `descriptors` 属性访问它们。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:)#see-also)

### [Discovering Characteristics and their Descriptors 发现特征及其描述符](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:)#Discovering-Characteristics-and-their-Descriptors)

[`func peripheral(CBPeripheral, didDiscoverCharacteristicsFor: CBService, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:))

Tells the delegate that the peripheral found characteristics for a service.
告知委托外围设备找到了服务的特征。
