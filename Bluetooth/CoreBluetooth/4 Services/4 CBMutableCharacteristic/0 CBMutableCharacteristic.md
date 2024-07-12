Class 类

# CBMutableCharacteristic

A characteristic of a local peripheral’s service.
本地外围设备服务的特征。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
class CBMutableCharacteristic
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#overview)

[`CBMutableCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic) objects represent the characteristics of a local peripheral’s service. This class adds write access to many of the properties in the [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic) class, which it inherits from.
`CBMutableCharacteristic` 对象表示本地外设服务的特征。这个类为 `CBCharacteristic` 类中的许多属性添加了写访问权限，它从 `CBCharacteristic` 类继承。

You use this class to create a characteristic and to set its properties and permissions as desired. After you create and add a characteristic to a local service, you can publish it (and the service) to the peripheral’s local database with the [`add(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:)) method of the [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) class. After you publish a characteristic, Core Bluetooth caches the characteristic and you can’t make changes to it.
您可以使用此类创建特征并根据需要设置其属性和权限。在创建特征并将其添加到本地服务后，可以使用 `CBPeripheralManager` 类的 `add(_:)` 方法将其（和服务）发布到外围设备的本地数据库。发布特征后，Core Bluetooth会缓存该特征，您无法对其进行更改。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#topics)

### [Creating a Mutable Characteristic 创建可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#Creating-a-Mutable-Characteristic)

#### [`init(type: CBUUID, properties: CBCharacteristicProperties, value: Data?, permissions: CBAttributePermissions)`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/init(type:properties:value:permissions:))

Creates a mutable characteristic with specified permissions, properties, and value.
创建具有指定权限、属性和值的可变特征。



### [Managing a Mutable Characteristic 管理可变特性](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#Managing-a-Mutable-Characteristic)

#### [`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/value)

The value of the characteristic.
特性的值。



#### [`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/descriptors)

An array of the characteristic’s descriptors.
特征描述符的数组。



#### [`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/properties)

The properties of the characteristic.
特性的属性。



#### [`var permissions: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/permissions)

The permissions of the characteristic value.
特征值的权限。



#### [`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。



#### [`var subscribedCentrals: [CBCentral\]?`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic/subscribedcentrals)

A list of centrals that are currently subscribed to the characteristic’s value.
当前订阅特征值的中心点列表。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#inherits-from)

- [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#see-also)

### [Services 服务](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic#Services)

[`class CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)

A collection of data and associated behaviors that accomplish a function or feature of a device.
完成设备功能或特性的数据和相关行为的集合。

[`class CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice)

A service with writeable property values.
具有可写属性值的服务。

[`class CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic)

A characteristic of a remote peripheral’s service.
远程外设服务的一种特性。

[`class CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)

An object that provides further information about a remote peripheral’s characteristic.
提供有关远程外围设备特性的进一步信息的对象。

[`class CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor)

An object that provides additional information about a local peripheral’s characteristic.
提供有关本地外设特性的附加信息的对象。
