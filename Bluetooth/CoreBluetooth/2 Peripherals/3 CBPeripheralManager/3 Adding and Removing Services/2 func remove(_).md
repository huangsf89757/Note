Instance Method Instance 方法

# remove(_:) 

Removes a specified published service from the local GATT database.
从本地 GATT 数据库中删除指定的已发布服务。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func remove(_ service: CBMutableService)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:)#parameters)

- `service`

  The service you want to remove. 

  要删除的服务。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:)#Discussion)

Because apps on the local peripheral device share the GATT database, more than one instance of a service may exist in the database. As a result, this method removes only the instance of the service that your app added to the database (using the [`add(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)) method). If any other services contains this service, you must first remove them.
由于本地外围设备上的应用共享 GATT 数据库，因此数据库中可能存在多个服务实例。因此，此方法仅删除应用添加到数据库的服务实例（使用该 `add(_:)` 方法）。如果任何其他服务包含此服务，则必须先将其删除。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:)#see-also)

### [Adding and Removing Services 添加和删除服务](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:)#Adding-and-Removing-Services)

[`func add(CBMutableService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:))

Publishes a service and any of its associated characteristics and characteristic descriptors to the local GATT database.
将服务及其任何关联的特征和特征描述符发布到本地 GATT 数据库。

[`func removeAllServices()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/removeallservices())

Removes all published services from the local GATT database.
从本地 GATT 数据库中删除所有已发布的服务。
