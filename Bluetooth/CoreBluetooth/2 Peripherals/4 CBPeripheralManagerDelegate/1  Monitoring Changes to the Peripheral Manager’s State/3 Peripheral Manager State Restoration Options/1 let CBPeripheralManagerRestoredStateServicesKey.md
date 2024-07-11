Global Variable 全局变量

# CBPeripheralManagerRestoredStateServicesKey

An array of restored peripheral services.
一系列已恢复的外围服务。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
let CBPeripheralManagerRestoredStateServicesKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerrestoredstateserviceskey#Discussion)

The value associated with this key is an [`NSArray`](https://developer.apple.com/documentation/foundation/nsarray) of [`CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice) objects. It contains all of the services that previously published to the local peripheral’s database when the system quit the app.
与此键关联的值是 `NSArray` of `CBMutableService` 对象。它包含系统退出应用程序时以前发布到本地外围设备数据库的所有服务。

Restoration includes all information about a service, including any included services, characteristics, characteristic descriptors, and subscribed centrals.
还原包括有关服务的所有信息，包括任何包含的服务、特征、特征描述符和订阅的中心。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerrestoredstateserviceskey#see-also)

### [State Restoration Dictionary Keys 状态还原字典键](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerrestoredstateserviceskey#State-Restoration-Dictionary-Keys)

[`let CBPeripheralManagerRestoredStateAdvertisementDataKey: String`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerrestoredstateadvertisementdatakey)

A dictionary of restored advertising data.
恢复广告数据的字典。
