Instance Property 实例属性

# descriptors 

An array of the characteristic’s descriptors.
特征描述符的数组。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var descriptors: [CBDescriptor]? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors#Discussion)

The value of this property is an array of [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor) objects that provide more information about a characteristic’s value. For example, they may describe the value in human-readable form and describe how to format the value for presentation purposes. For more information about characteristic descriptors, see [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor).
此属性的值是一个由 `CBDescriptor` 对象组成的数组，这些对象提供有关特征值的更多信息。例如，它们可以以人类可读的形式描述值，并描述如何格式化值以用于表示目的。有关特征描述符的更多信息，请参见 `CBDescriptor` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors#see-also)

### [Managing a Mutable Characteristic 管理可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors#Managing-a-Mutable-Characteristic)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value)

The value of the characteristic.
特性的值。

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
