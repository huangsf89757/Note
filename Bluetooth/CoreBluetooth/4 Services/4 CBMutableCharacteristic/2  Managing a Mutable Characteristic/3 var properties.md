Instance Property 实例属性

# properties 

The properties of the characteristic.
特性的属性。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var properties: CBCharacteristicProperties { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/properties#Discussion)

The properties of a characteristic determine the access to and use of the characteristic’s value and descriptors. For a list of the possible values representing the properties of a characteristic, see the [`CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties) enumeration in [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic). However, you can’t use the [`broadcast`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/broadcast) and [`extendedProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/extendedproperties) characteristic properties when creating a mutable characteristic.
特性的属性决定了对特性的值和描述符的访问和使用。有关表示特性属性的可能值的列表，请参见 `CBCharacteristic` 中的 `CBCharacteristicProperties` 枚举。但是，在创建可变特性时，您不能使用 `broadcast` 和 `extendedProperties` 特性属性。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/properties#see-also)

### [Managing a Mutable Characteristic 管理可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/properties#Managing-a-Mutable-Characteristic)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value)

The value of the characteristic.
特性的值。

[`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors)

An array of the characteristic’s descriptors.
特征描述符的数组。

[`var permissions: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/permissions)

The permissions of the characteristic value.
特征值的权限。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。

[`var subscribedCentrals: [CBCentral\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals)

A list of centrals that are currently subscribed to the characteristic’s value.
当前订阅特征值的中心点列表。
