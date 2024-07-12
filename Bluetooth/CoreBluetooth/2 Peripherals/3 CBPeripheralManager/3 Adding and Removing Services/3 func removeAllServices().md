Instance Method Instance 方法

# removeAllServices() 删除AllServices（）

Removes all published services from the local GATT database.
从本地 GATT 数据库中删除所有已发布的服务。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func removeAllServices()
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/removeallservices()#Discussion)

Use this when you want to remove all services you’ve previously published, for example, if your app has a toggle button to expose GATT services.
当您想要移除之前发布的所有服务时，例如，如果您的应用具有用于公开 GATT 服务的切换按钮，请使用此选项。

Because apps on the local peripheral device share the GATT database, this method removes only the services that you added using the [`add(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)) method. This call doesn’t remove any services published by other apps on the local peripheral device.
由于本地外围设备上的应用共享 GATT 数据库，因此此方法仅删除使用该 `add(_:)` 方法添加的服务。此调用不会删除本地外围设备上其他应用发布的任何服务。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/removeallservices()#see-also)

### [Adding and Removing Services 添加和删除服务](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/removeallservices()#Adding-and-Removing-Services)

[`func add(CBMutableService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:))

Publishes a service and any of its associated characteristics and characteristic descriptors to the local GATT database.
将服务及其任何关联的特征和特征描述符发布到本地 GATT 数据库。

[`func remove(CBMutableService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:))

Removes a specified published service from the local GATT database.
从本地 GATT 数据库中删除指定的已发布服务。
