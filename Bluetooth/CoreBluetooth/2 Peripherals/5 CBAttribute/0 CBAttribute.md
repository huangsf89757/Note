Class 类

# CBAttribute

A representation of common aspects of services offered by a peripheral.
外围设备提供的服务的公共方面的表示。

iOS 8.0+iPadOS 8.0+Mac Catalyst 13.1+macOS 10.13+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
class CBAttribute
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbattribute#overview)

Concrete subclasses of [`CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute) (and their mutable counterparts) represent the services a peripheral offers, the characteristics of those services, and the descriptors attached to those characteristics. The concrete subclasses are:
`CBAttribute` 的具体子类（以及它们的可变对应物）表示外围设备提供的服务、这些服务的特征以及附加到这些特征的描述符。具体的子类是：

- [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)
- [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic)
- [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbattribute#topics)

### [Identifying an Attribute 识别属性](https://developer.apple.com/documentation/corebluetooth/cbattribute#Identifying-an-Attribute)

#### [`var uuid: CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbattribute/uuid)

The Bluetooth-specific UUID of the attribute.
属性的蓝牙特定UUID。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbattribute#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbattribute#inherits-from)

- [`NSObject`](https://developer.apple.com/documentation/objectivec/nsobject)



### [Inherited By 继承](https://developer.apple.com/documentation/corebluetooth/cbattribute#inherited-by)

- [`CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic)
- [`CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)
- [`CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbattribute#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbattribute#see-also)

### [Peripherals 外围设备](https://developer.apple.com/documentation/corebluetooth/cbattribute#Peripherals)

[`class CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral)

A remote peripheral device.
一种远程外围设备。

[`protocol CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate)

A protocol that provides updates on the use of a peripheral’s services.
一种协议，提供外围设备服务使用的更新。

[`class CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)

An object that manages and advertises peripheral services exposed by this app.
一个对象，用于管理和维护此应用程序公开的外围设备服务。

[`protocol CBPeripheralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate)

A protocol that provides updates for local peripheral state and interactions with remote central devices.
一种协议，提供本地外围设备状态的更新以及与远程中央设备的交互。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。
