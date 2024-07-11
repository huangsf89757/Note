Instance Method Instance 方法

# peripheralManager(_:central:didUnsubscribeFrom:) 

Tells the delegate that a remote central device unsubscribed from a characteristic’s value.
告知委托远程中央设备取消订阅特征的值。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    central: CBCentral,
    didUnsubscribeFrom characteristic: CBCharacteristic
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:)#parameters)

- `peripheral`

  The peripheral manager connected to the remote central. 

  连接到远程中心的外围管理器。

- `central`

  The remote central device that subscribed to the characteristic’s value. 

  订阅特征值的远程中央设备。

- `characteristic`

  The characteristic unsubscribed from. 

  取消订阅的特征。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:)#Discussion)

Core Bluetooth calls this method when a remote central device unsubscribes from the value of one of the local peripheral’s characteristics, by disabling notifications or indications on the characteristic’s value. When called, stop sending the subscribed central updates of updates to the characteristic’s value.
当远程中央设备取消订阅本地外围设备之一的特征值时，核心蓝牙会调用此方法，方法是禁用有关该特征值的通知或指示。调用时，停止发送订阅的特征值更新的中心更新。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:)#see-also)

### [Monitoring Subscriptions to Characteristic Values 监视对特征值的订阅](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:)#Monitoring-Subscriptions-to-Characteristic-Values)

[`func peripheralManager(CBPeripheralManager, central: CBCentral, didSubscribeTo: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:))

Tells the delegate that a remote central device subscribed to a characteristic’s value.
告知委托远程中心设备订阅了特征的值。

**Required 必填**

[`func peripheralManagerIsReady(toUpdateSubscribers: CBPeripheralManager)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:))

Tells the delegate that a local peripheral device is ready to send characteristic value updates.
告知委托本地外围设备已准备好发送特征值更新。
