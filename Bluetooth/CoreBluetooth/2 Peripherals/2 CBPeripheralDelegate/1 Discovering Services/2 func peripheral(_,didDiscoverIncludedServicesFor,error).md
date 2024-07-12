Instance Method Instance 方法

# peripheral(_:didDiscoverIncludedServicesFor:error:) 

Tells the delegate that discovering included services within the indicated service completed.
告知委托已完成发现指示服务中的包含服务。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didDiscoverIncludedServicesFor service: CBService,
    error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverincludedservicesfor:error:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `service`

  The [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice) object containing the included service. 

  包含包含的服务的 `CBService` 对象。

- `error`

  The reason the call failed, or `nil` if no error occurred. 
  
  调用失败的原因，或者 `nil` 是否未发生错误。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverincludedservicesfor:error:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`discoverIncludedServices(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverincludedservices(_:for:)) method. If the peripheral successfully discovers services, you can access them through the service’s [`includedServices`](https://developer.apple.com/documentation/corebluetooth/cbservice/includedservices) property. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `discoverIncludedServices(_:for:)` 方法时调用该方法。如果外围设备成功发现服务，则可以通过服务的 `includedServices` 属性访问它们。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverincludedservicesfor:error:)#see-also)

### [Discovering Services 发现服务](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverincludedservicesfor:error:)#Discovering-Services)

[`func peripheral(CBPeripheral, didDiscoverServices: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:))

Tells the delegate that peripheral service discovery succeeded.
告知委托外围服务发现成功。
