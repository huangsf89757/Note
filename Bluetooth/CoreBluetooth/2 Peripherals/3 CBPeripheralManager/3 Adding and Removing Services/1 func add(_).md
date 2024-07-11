Instance Method Instance 方法

# add(_:) 

Publishes a service and any of its associated characteristics and characteristic descriptors to the local GATT database.
将服务及其任何关联的特征和特征描述符发布到本地 GATT 数据库。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func add(_ service: CBMutableService)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)#parameters)

- `service`

  The service you want to publish. 

  要发布的服务。
  
  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)#Discussion)

When you add a service to the database, the peripheral manager calls the [`peripheralManager(_:didAdd:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didadd:error:)) method of its delegate object. If the service contains any included services, you must first publish them.
将服务添加到数据库时，外围管理器将调用其委托对象 `peripheralManager(_:didAdd:error:)` 的方法。如果服务包含任何包含的服务，则必须首先发布它们。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)#see-also)

### [Adding and Removing Services 添加和删除服务](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)#Adding-and-Removing-Services)

[`func remove(CBMutableService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:))

Removes a specified published service from the local GATT database.
从本地 GATT 数据库中删除指定的已发布服务。

[`func removeAllServices()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/removeallservices())

Removes all published services from the local GATT database.
从本地 GATT 数据库中删除所有已发布的服务。
