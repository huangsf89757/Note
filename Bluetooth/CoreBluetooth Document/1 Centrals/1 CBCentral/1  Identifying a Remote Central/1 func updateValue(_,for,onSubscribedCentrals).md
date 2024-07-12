Instance Method 实例方法

# updateValue(_:for:onSubscribedCentrals:) 

Send an updated characteristic value to one or more subscribed centrals, using a notification or indication.
使用通知或指示向一个或多个订阅中心发送更新的特征值。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func updateValue(
    _ value: Data,
    for characteristic: CBMutableCharacteristic,
    onSubscribedCentrals centrals: [CBCentral]?
) -> Bool
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)#parameters)

- `value`

  The characteristic value you want to send via a notification or indication. 要通过通知或指示发送的特征值。

- `characteristic`

  The characteristic whose value has changed. 其值已更改的特性。

- `centrals`

  A list of centrals (represented by [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral) objects) that have subscribed to receive updates of the characteristic’s value. If `nil`, the manager updates all subscribed centrals. The manager ignores any centrals that haven’t subscribed to the characteristic’s value. 已订阅接收特征值更新的中心点列表（由 `CBCentral` 对象表示）。如果是 `nil` ，管理器将更新所有订阅的中心。管理器忽略任何没有订阅特征值的中心。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)#return-value)

This value is [`true`](https://developer.apple.com/documentation/swift/true) if the update is successfully sent to the subscribed central or centrals. [`false`](https://developer.apple.com/documentation/swift/false) if the update isn’t successfully sent because the underlying transmit queue is full.
如果更新成功发送到订阅的中心，则此值为 `true` 。 `false` 如果由于底层传输队列已满而无法成功发送更新。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)#Discussion)

You use this method to send updates of a characteristic’s value—through a notification or indication—to selected centrals that have subscribed to that characteristic’s value. If the method returns [`false`](https://developer.apple.com/documentation/swift/false) because the underlying transmit queue is full, the peripheral manager calls the [`peripheralManagerIsReady(toUpdateSubscribers:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)) method of its delegate object when more space in the transmit queue becomes available. After you receive this delegate method callback, you may resend the update.
您可以使用此方法通过通知或指示将特征值的更新发送到已订阅该特征值的选定中心。如果由于底层传输队列已满，该方法返回 `false` ，则当传输队列中有更多空间可用时，外围设备管理器调用其委托对象的 `peripheralManagerIsReady(toUpdateSubscribers:)` 方法。收到此委托方法回调后，可以重新发送更新。

If the length of the `value` parameter exceeds the length of the [`maximumUpdateValueLength`](https://developer.apple.com/documentation/corebluetooth/cbcentral/maximumupdatevaluelength) property of a subscribed [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral), the `value` parameter truncates accordingly.
如果 `value` 参数的长度超过订阅的 `CBCentral` 的 `maximumUpdateValueLength` 属性的长度，则 `value` 参数相应地截断。
