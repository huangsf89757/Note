Instance Method Instance 方法

# peripheral(_:didDiscoverCharacteristicsFor:error:) 

Tells the delegate that the peripheral found characteristics for a service.
告知委托外围设备找到了服务的特征。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didDiscoverCharacteristicsFor service: CBService,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `service`

  The service to which the characteristics belong. 

  特征所属的服务。

- `error`

  The reason the call failed, or `nil` if no error occurred. 

  调用失败的原因，或者 `nil` 是否未发生错误。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`discoverCharacteristics(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:)) method. If the peripheral successfully discovers the characteristics of the specified service, you can access them through the service’s [`characteristics`](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics) property. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `discoverCharacteristics(_:for:)` 方法时调用该方法。如果外围设备成功发现指定服务的特征，则可以通过服务的 `characteristics` 属性访问它们。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:)#see-also)

### [Discovering Characteristics and their Descriptors 发现特征及其描述符](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:)#Discovering-Characteristics-and-their-Descriptors)

[`func peripheral(CBPeripheral, didDiscoverDescriptorsFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:))

Tells the delegate that the peripheral found descriptors for a characteristic.
告诉委托外围设备找到了特征的描述符。

**Required 必填**
