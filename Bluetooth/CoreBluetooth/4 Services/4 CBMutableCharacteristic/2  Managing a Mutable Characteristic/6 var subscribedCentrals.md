Instance Property 实例属性

# subscribedCentrals 订阅中心

A list of centrals that are currently subscribed to the characteristic’s value.
当前订阅特征值的中心点列表。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var subscribedCentrals: [CBCentral]? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals#Discussion)

The value of this property is an array of [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral) objects that currently subscribe to the characteristic’s value. The array is empty if the characteristic isn’t configured to support notifications or indications. Even if the characteristic’s configuration supports notifications or indications, the array is empty if centrals aren’t subscribing to the characteristic’s value.
此属性的值是当前订阅特征值的 `CBCentral` 对象的数组。如果未将特征配置为支持通知或指示，则数组为空。即使特征的配置支持通知或指示，如果中心不订阅特征的值，数组也是空的。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals#topics)

### [Related Documentation 相关文件](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals#Related-Documentation)

#### [`func updateValue(Data, for: CBMutableCharacteristic, onSubscribedCentrals: [CBCentral\]?) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:))

Send an updated characteristic value to one or more subscribed centrals, using a notification or indication.
使用通知或指示向一个或多个订阅中心发送更新的特征值。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals#see-also)

### [Managing a Mutable Characteristic 管理可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals#Managing-a-Mutable-Characteristic)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value)

The value of the characteristic.
特性的值。

[`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors)

An array of the characteristic’s descriptors.
特征描述符的数组。

[`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/properties)

The properties of the characteristic.
特性的属性。

[`var permissions: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/permissions)

The permissions of the characteristic value.
特征值的权限。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。
