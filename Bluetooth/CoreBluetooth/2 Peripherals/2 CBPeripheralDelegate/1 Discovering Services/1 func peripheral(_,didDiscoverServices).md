Instance Method Instance 方法

# peripheral(_:didDiscoverServices:) 

Tells the delegate that peripheral service discovery succeeded.
告知委托外围服务发现成功。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didDiscoverServices error: (any Error)?
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:)#parameters)

- `peripheral`

  The peripheral to which the services belong. 

  服务所属的外围设备。

- `error`

  The reason the call failed, or `nil` if no error occurred. 
  
  调用失败的原因，或者 `nil` 是否未发生错误。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:)#Discussion)

Core Bluetooth invokes this method when your app calls the [`discoverServices(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)) method. If the peripheral successfully discovers services, you can access them through the peripheral’s [`services`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services) property. If successful, the `error` parameter is `nil`. If unsuccessful, the `error` parameter returns the cause of the failure.
核心蓝牙会在应用调用该 `discoverServices(_:)` 方法时调用该方法。如果外围设备成功发现服务，则可以通过外围设备 `services` 的属性访问它们。如果成功，则参数 `error` 为 `nil` 。如果不成功，该 `error` 参数将返回失败的原因。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅核心蓝牙编程指南。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:)#see-also)

### [Discovering Services 发现服务](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:)#Discovering-Services)

[`func peripheral(CBPeripheral, didDiscoverIncludedServicesFor: CBService, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverincludedservicesfor:error:))

Tells the delegate that discovering included services within the indicated service completed.
告知委托已完成发现指示服务中的包含服务。
