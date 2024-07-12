Initializer

# init(type:properties:value:permissions:) 

Creates a mutable characteristic with specified permissions, properties, and value.
创建具有指定权限、属性和值的可变特征。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+

```
init(
    type UUID: CBUUID,
    properties: CBCharacteristicProperties,
    value: Data?,
    permissions: CBAttributePermissions
)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/init(type:properties:value:permissions:)#parameters)

- `UUID`

  A 128-bit UUID that identifies the characteristic. 

  标识特征的128位UUID。

- `properties`

  The properties of the characteristic. 

  特性的属性。

- `value`

  The characteristic value to cache. If `nil`, the value is dynamic and the peripheral manager fetches it on demand. 

  要缓存的特征值。如果是 `nil` ，则该值是动态的，外围设备管理器根据需要获取该值。

- `permissions`

  The permissions of the characteristic value. 

  特征值的权限。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/init(type:properties:value:permissions:)#return-value)

A newly initialized mutable characteristic.
新初始化的可变特征。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/init(type:properties:value:permissions:)#Discussion)

If you specify a value for the characteristic, the characteristic caches the value and sets its properties and permissions to [`read`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/read) and [`readable`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/readable), respectively. Therefore, if you need the value of a characteristic to be writeable, or if you expect the value to change during the lifetime of the published service to which the characteristic belongs, you must specify the value as `nil`. This ensures that the characteristic treats the value dynamically. With a dynamic value, the peripheral manager requests the value whenever the peripheral manager receives a read or write request from a central. The peripheral does this by calling the [`peripheralManager(_:didReceiveRead:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:)) and [`peripheralManager(_:didReceiveWrite:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:)) methods of its delegate object, respectively.
如果您为特性指定了一个值，则特性会缓存该值，并将其属性和权限分别设置为 `read` 和 `readable` 。因此，如果您需要特性的值是可写的，或者如果您希望该值在特性所属的已发布服务的生存期内发生更改，则必须将该值指定为 `nil` 。这确保了特征动态地处理该值。对于动态值，每当外围设备管理器接收到来自中央设备的读或写请求时，外围设备管理器就请求该值。外围设备通过分别调用其委托对象的 `peripheralManager(_:didReceiveRead:)` 和 `peripheralManager(_:didReceiveWrite:)` 方法来实现这一点。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅Core Bluetooth Programming Guide。
