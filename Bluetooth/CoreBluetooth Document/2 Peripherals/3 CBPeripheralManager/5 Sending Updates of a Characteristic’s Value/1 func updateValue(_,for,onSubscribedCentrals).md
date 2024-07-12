Instance Method Instance 方法

# updateValue(_:for:onSubscribedCentrals:) 

Send an updated characteristic value to one or more subscribed centrals, using a notification or indication.
使用通知或指示将更新的特征值发送到一个或多个订阅的中心。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func updateValue(
    _ value: Data,
    for characteristic: CBMutableCharacteristic,
    onSubscribedCentrals centrals: [CBCentral]?
) -> Bool
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)#parameters)

- `value`

  The characteristic value you want to send via a notification or indication. 

  要通过通知或指示发送的特征值。

- `characteristic`

  The characteristic whose value has changed. 

  其值已更改的特征。

- `centrals`

  A list of centrals (represented by [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral) objects) that have subscribed to receive updates of the characteristic’s value. If `nil`, the manager updates all subscribed centrals. The manager ignores any centrals that haven’t subscribed to the characteristic’s value. 

  已订阅接收特征值更新的中心（由 `CBCentral` 对象表示）的列表。如果 `nil` ，则管理器更新所有订阅的中心。经理会忽略任何未订阅特征值的中心。

  

## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)#return-value)

This value is [`true`](https://developer.apple.com/documentation/swift/true) if the update is successfully sent to the subscribed central or centrals. [`false`](https://developer.apple.com/documentation/swift/false) if the update isn’t successfully sent because the underlying transmit queue is full.
此值为 `true` 如果更新已成功发送到订阅的一个或多个中心。 `false` 如果由于基础传输队列已满而未成功发送更新。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:)#Discussion)

You use this method to send updates of a characteristic’s value—through a notification or indication—to selected centrals that have subscribed to that characteristic’s value. If the method returns [`false`](https://developer.apple.com/documentation/swift/false) because the underlying transmit queue is full, the peripheral manager calls the [`peripheralManagerIsReady(toUpdateSubscribers:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:)) method of its delegate object when more space in the transmit queue becomes available. After you receive this delegate method callback, you may resend the update.
使用此方法通过通知或指示将特征值的更新发送到已订阅该特征值的选定中心。如果 `false` 该方法返回是因为基础传输队列已满，则当传输队列中的更多空间可用时，外围管理器将调用其委托对象 `peripheralManagerIsReady(toUpdateSubscribers:)` 的方法。收到此委托方法回调后，可以重新发送更新。

If the length of the `value` parameter exceeds the length of the [`maximumUpdateValueLength`](https://developer.apple.com/documentation/corebluetooth/cbcentral/maximumupdatevaluelength) property of a subscribed [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral), the `value` parameter truncates accordingly.
如果 `value` 参数的长度超过订阅的 `maximumUpdateValueLength` 属性的长度 `CBCentral` ，则参数 `value` 将相应地截断。
