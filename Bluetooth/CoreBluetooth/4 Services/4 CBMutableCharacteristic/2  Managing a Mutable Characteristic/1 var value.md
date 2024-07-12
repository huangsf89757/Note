Instance Property 实例属性

# value 值

The value of the characteristic.
特性的值。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var value: Data? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value#Discussion)

This property contains the value of the characteristic. For example, a temperature measurement characteristic of a health thermometer service may have a value that indicates a temperature in Celsius.
此属性包含特征的值。例如，健康温度计服务的温度测量特性可以具有指示以摄氏度为单位的温度的值。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value#see-also)

### [Managing a Mutable Characteristic 管理可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value#Managing-a-Mutable-Characteristic)

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

[`var subscribedCentrals: [CBCentral\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals)

A list of centrals that are currently subscribed to the characteristic’s value.
当前订阅特征值的中心点列表。
