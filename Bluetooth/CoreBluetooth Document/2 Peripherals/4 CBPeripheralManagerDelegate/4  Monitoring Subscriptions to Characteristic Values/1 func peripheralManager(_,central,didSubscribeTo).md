Instance Method Instance 方法

# peripheralManager(_:central:didSubscribeTo:) 

Tells the delegate that a remote central device subscribed to a characteristic’s value.
告知委托远程中心设备订阅了特征的值。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
optional func peripheralManager(
    _ peripheral: CBPeripheralManager,
    central: CBCentral,
    didSubscribeTo characteristic: CBCharacteristic
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:)#parameters)

- `peripheral`

  The peripheral manager connected to the remote central. 

  连接到远程中心的外围管理器。

- `central`

  The remote central device that subscribed to the characteristic’s value. 

  订阅特征值的远程中央设备。

- `characteristic`

  The characteristic subscribed to. 

  订阅的特征。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:)#Discussion)

Core Bluetooth invokes this method when a remote central device subscribes to the value of one of the local peripheral’s characteristics, by enabling notifications or indications on the characteristic’s value. When called, start sending the subscribed central updates as the characteristic’s value changes. To send updated characteristic values to subscribed centrals, use the [`updateValue(_:for:onSubscribedCentrals:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class.
当远程中央设备订阅本地外围设备之一的特征值时，核心蓝牙通过启用有关该特性值的通知或指示来调用此方法。调用时，随着特征值的更改，开始发送订阅的中心更新。若要将更新的特征值发送到订阅的中心，请使用 `CBPeripheralManager` 类 `updateValue(_:for:onSubscribedCentrals:)` 的方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:)#see-also)

### [Monitoring Subscriptions to Characteristic Values 监视对特征值的订阅](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:)#Monitoring-Subscriptions-to-Characteristic-Values)

[`func peripheralManager(CBPeripheralManager, central: CBCentral, didUnsubscribeFrom: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:))

Tells the delegate that a remote central device unsubscribed from a characteristic’s value.
告知委托远程中央设备取消订阅特征的值。

**Required 必填**

[`func peripheralManagerIsReady(toUpdateSubscribers: CBPeripheralManager)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:))

Tells the delegate that a local peripheral device is ready to send characteristic value updates.
告知委托本地外围设备已准备好发送特征值更新。
