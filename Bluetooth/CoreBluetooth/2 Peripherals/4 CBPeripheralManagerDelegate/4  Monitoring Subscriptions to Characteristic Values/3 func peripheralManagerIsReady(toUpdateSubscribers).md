Instance Method Instance 方法

# peripheralManagerIsReady(toUpdateSubscribers:) 

Tells the delegate that a local peripheral device is ready to send characteristic value updates.
告知委托本地外围设备已准备好发送特征值更新。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheralManagerIsReady(toUpdateSubscribers peripheral: CBPeripheralManager)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)#parameters)

- `peripheral`

  The peripheral manager that sends characteristic value updates. 

  发送特征值更新的外设管理器。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)#Discussion)

When a call to the [`updateValue(_:for:onSubscribedCentrals:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)) method fails because the underlying queue used to transmit the updated characteristic value is full, Core Bluetooth calls the [`peripheralManagerIsReady(toUpdateSubscribers:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)) method when more space in the transmit queue becomes available. You can then implement this delegate method to resend the value.
当由于用于传输更新的特征值的基础队列已满而导致对 `updateValue(_:for:onSubscribedCentrals:)` 方法的调用失败时，Core Bluetooth 会在传输队列中的更多空间可用时调用该 `peripheralManagerIsReady(toUpdateSubscribers:)` 方法。然后，可以实现此委托方法以重新发送值。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)#see-also)

### [Monitoring Subscriptions to Characteristic Values 监视对特征值的订阅](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)#Monitoring-Subscriptions-to-Characteristic-Values)

[`func peripheralManager(CBPeripheralManager, central: CBCentral, didSubscribeTo: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:))

Tells the delegate that a remote central device subscribed to a characteristic’s value.
告知委托远程中心设备订阅了特征的值。

**Required 必填**

[`func peripheralManager(CBPeripheralManager, central: CBCentral, didUnsubscribeFrom: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:))

Tells the delegate that a remote central device unsubscribed from a characteristic’s value.
告知委托远程中央设备取消订阅特征的值。

**Required 必填**
