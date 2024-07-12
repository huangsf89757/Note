Instance Property 实例属性

# permissions 

The permissions of the characteristic value.
特征值的权限。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var permissions: CBAttributePermissions { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/permissions#Discussion)

Characteristic permissions represent the read, write, and encryption permissions for a characteristic’s value. For a complete list and discussion of the available characteristic permissions, see [`CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions).
特征权限表示特征值的读、写和加密权限。有关可用特性权限的完整列表和讨论，请参见 `CBAttributePermissions` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/permissions#see-also)

### [Managing a Mutable Characteristic 管理可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/permissions#Managing-a-Mutable-Characteristic)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value)

The value of the characteristic.
特性的值。

[`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors)

An array of the characteristic’s descriptors.
特征描述符的数组。

[`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/properties)

The properties of the characteristic.
特性的属性。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。

[`var subscribedCentrals: [CBCentral\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals)

A list of centrals that are currently subscribed to the characteristic’s value.
当前订阅特征值的中心点列表。
