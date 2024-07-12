Structure 结构

# CBAttributePermissions CBAttribute

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
struct CBAttributePermissions
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#overview)

When you initialize a new mutable characteristic, you set the read, write, and encryption permissions for the characteristic’s value. Setting the read and write *permissions* for a characteristic’s value is different from specifying the read and write *properties* for a characteristic’s value. When you specify the read and write properties, the client (a central) inspects the read and write permissions of the characteristic’s value. When you specify the read and write permissions for a characteristic’s value, you set the permissions for the server (the peripheral) to allow the type of read or write specified by the characteristic’s properties. Therefore, when you initialize a mutable characteristic, you need to specify read or write properties and their corresponding permissions.
当您初始化一个新的可变特征时，您可以为该特征的值设置读、写和加密权限。为特征值设置读写权限不同于为特征值指定读写属性。当您指定读和写属性时，客户端（中心）检查特征值的读和写权限。当您为特征值指定读写权限时，您将服务器（外围设备）的权限设置为允许特征属性指定的读写类型。因此，在初始化可变特性时，需要指定读或写属性及其相应的权限。

If you want to enforce encryption requirements for reads and writes on a characteristic’s value, you must specify the relevant permission ([`readEncryptionRequired`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/readencryptionrequired) or [`writeEncryptionRequired`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/writeencryptionrequired)). You may set more than one permission for a characteristic’s value.
如果要对特征值的读写强制加密要求，则必须指定相关权限（ `readEncryptionRequired` 或 `writeEncryptionRequired` ）。您可以为一个特征值设置多个权限。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#topics)

### [Creating a Permissions Instance 创建实例](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#Creating-a-Permissions-Instance)

#### [`init(rawValue: UInt)`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/init(rawvalue:))

Creates a permissions instance from the provided raw value.
从提供的原始值创建权限实例。



### [Permissions 权限](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#Permissions)

#### [`static var readable: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/readable)

A permission that indicates a peripheral can read the attribute’s value.
指示外围设备可以读取属性值的权限。



#### [`static var writeable: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/writeable)

A permission that indicates a peripheral can write the attribute’s value.
指示外围设备可以写入属性值的权限。



#### [`static var readEncryptionRequired: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/readencryptionrequired)

A permission that indicates only trusted devices can read the attribute’s value.
一种权限，指示只有受信任的设备可以读取属性的值。



#### [`static var writeEncryptionRequired: CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions/writeencryptionrequired)

A permission that indicates only trusted devices can write the attribute’s value.
一种权限，指示只有受信任的设备可以写入属性的值。



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### OptionSet Implementations

OptionSet实现



#### SetAlgebra Implementations

集合代数实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`ExpressibleByArrayLiteral`](https://developer.apple.com/documentation/Swift/ExpressibleByArrayLiteral)
- [`OptionSet`](https://developer.apple.com/documentation/Swift/OptionSet)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)
- [`SetAlgebra`](https://developer.apple.com/documentation/Swift/SetAlgebra)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#see-also)

### [Peripherals 外围设备](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions#Peripherals)

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

[`class CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)

A representation of common aspects of services offered by a peripheral.
外围设备提供的服务的公共方面的表示。