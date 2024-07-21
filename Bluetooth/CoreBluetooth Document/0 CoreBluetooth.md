Framework 框架

# Core Bluetooth 核心蓝牙

Communicate with Bluetooth low energy and BR/EDR (“Classic”) Devices.
与低功耗蓝牙和BR/EDR（“经典”）设备通信。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 



## [Overview 概述](https://developer.apple.com/documentation/CoreBluetooth#overview)

The Core Bluetooth framework provides the classes needed for your apps to communicate with Bluetooth-equipped low energy (LE) and Basic Rate / Enhanced Data Rate (BR/EDR) wireless technology.
Core Bluetooth框架提供应用与蓝牙低功耗（LE）和基本速率/增强数据速率（BR/EDR）无线技术通信所需的类。

Don’t subclass any of the classes of the Core Bluetooth framework. Overriding these classes isn’t supported and results in undefined behavior.
不要继承Core Bluetooth框架的任何类。不支持重写这些类，并会导致未定义的行为。

Core Bluetooth background execution modes aren’t supported in iPad apps running on macOS.
在macOS上运行的iPad应用不支持核心蓝牙后台执行模式。


> [!IMPORTANT]
> **Important 重要**
>
> Your app will crash if its `Info.plist` doesn’t include usage description keys for the types of data it needs to access. To access Core Bluetooth APIs on apps linked on or after iOS 13, include the [`NSBluetoothAlwaysUsageDescription`](https://developer.apple.com/documentation/bundleresources/information_property_list/nsbluetoothalwaysusagedescription) key. In iOS 12 and earlier, include [`NSBluetoothPeripheralUsageDescription`](https://developer.apple.com/documentation/bundleresources/information_property_list/nsbluetoothperipheralusagedescription) to access Bluetooth peripheral data.
> 如果您的应用的 `Info.plist` 不包含其需要访问的数据类型的使用说明键，则应用将崩溃。若要在iOS 13上或之后链接的应用上访问Core Bluetooth API，请包括 `NSBluetoothAlwaysUsageDescription` 键。在iOS 12及更早版本中，包括 `NSBluetoothPeripheralUsageDescription` 以访问蓝牙外设数据。



## [Topics 主题](https://developer.apple.com/documentation/CoreBluetooth#topics)

### [Centrals 中央设备](https://developer.apple.com/documentation/CoreBluetooth#Centrals)

#### [`class CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral)

A remote device connected to a local app, which is acting as a peripheral.
连接到本地应用程序的远程设备，该应用程序充当外围设备。



#### [`class CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)

An object that scans for, discovers, connects to, and manages peripherals.
扫描、发现、连接和管理外围设备的对象。



#### [`protocol CBCentralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate)

A protocol that provides updates for the discovery and management of peripheral devices.
为发现和管理外围设备提供更新的协议。



### [Peripherals 外围设备](https://developer.apple.com/documentation/CoreBluetooth#Peripherals)

#### [`class CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral)

A remote peripheral device.
一种远程外围设备。



#### [`protocol CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate)

A protocol that provides updates on the use of a peripheral’s services.
一种协议，提供外围设备服务使用的更新。



#### [`class CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)

An object that manages and advertises peripheral services exposed by this app.
一个对象，用于管理和维护此应用程序公开的外围设备服务。



#### [`protocol CBPeripheralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate)

A protocol that provides updates for local peripheral state and interactions with remote central devices.
一种协议，提供本地外围设备状态的更新以及与远程中央设备的交互。



#### [`class CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)

A representation of common aspects of services offered by a peripheral.
外围设备提供的服务的公共方面的表示。



#### [`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
值之一，表示特征值的读、写和加密权限。



### [Data Transfer 数据传输](https://developer.apple.com/documentation/CoreBluetooth#Data-Transfer)

Transferring Data Between Bluetooth Low Energy Devices
在低功耗蓝牙设备之间传输数据

Create a Bluetooth low energy central and peripheral device, and allow them to discover each other and exchange data.
创建低功耗蓝牙中央和外围设备，并允许它们相互发现并交换数据。



### [Services 服务](https://developer.apple.com/documentation/CoreBluetooth#Services)

#### [`class CBService`](https://developer.apple.com/documentation/corebluetooth/cbservice)

A collection of data and associated behaviors that accomplish a function or feature of a device.
完成设备功能或特性的数据和相关行为的集合。



#### [`class CBMutableService`](https://developer.apple.com/documentation/corebluetooth/cbmutableservice)

A service with writeable property values.
具有可写属性值的服务。



#### [`class CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic)

A characteristic of a remote peripheral’s service.
远程外设服务的一种特性。



#### [`class CBMutableCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbmutablecharacteristic)

A characteristic of a local peripheral’s service.
本地外围设备服务的特征。



#### [`class CBDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbdescriptor)

An object that provides further information about a remote peripheral’s characteristic.
提供有关远程外围设备特性的进一步信息的对象。



#### [`class CBMutableDescriptor`](https://developer.apple.com/documentation/corebluetooth/cbmutabledescriptor)

An object that provides additional information about a local peripheral’s characteristic.
提供有关本地外设特性的附加信息的对象。



### [Supporting Types 支持类型](https://developer.apple.com/documentation/CoreBluetooth#Supporting-Types)

#### [`class CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager)

The abstract base class that manages central and peripheral objects.
管理中心对象和外围对象的抽象基类。



#### [`class CBATTRequest`](https://developer.apple.com/documentation/corebluetooth/cbattrequest)

A request that uses the Attribute Protocol (ATT).
使用属性协议（ATT）的请求。



#### [`class CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer)

An object that represents a remote device.
表示远程设备的对象。



#### [`class CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid)

A universally unique identifier, as defined by Bluetooth standards.
一种通用的唯一标识符，由蓝牙标准定义。



### [Bluetooth Classic Support 经典蓝牙支持](https://developer.apple.com/documentation/CoreBluetooth#Bluetooth-Classic-Support)

Using Core Bluetooth Classic
使用Core Bluetooth Classic

Discover and communicate with a Bluetooth Classic device by using the Core Bluetooth APIs.
通过使用核心蓝牙API发现蓝牙经典设备并与之通信。



### [Errors 错误](https://developer.apple.com/documentation/CoreBluetooth#Errors)

#### [`struct CBError`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct)

An error that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误。



#### [`let CBErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cberrordomain)

The domain for Core Bluetooth errors.
核心蓝牙错误的域。



#### [`enum Code`](https://developer.apple.com/documentation/corebluetooth/cberror-swift.struct/code)

The codes for errors that Core Bluetooth returns during Bluetooth transactions.
Core Bluetooth在蓝牙事务期间返回的错误代码。



#### [`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。



#### [`let CBATTErrorDomain: String`](https://developer.apple.com/documentation/corebluetooth/cbatterrordomain)

The domain for Core Bluetooth ATT errors.
核心蓝牙ATT错误的域。



#### [`enum Code`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct/code)

The possible errors returned by a GATT server (a remote peripheral) during Bluetooth low energy ATT transactions.
蓝牙低功耗ATT事务期间GATT服务器（远程外设）可能返回的错误。



#### [`struct CBATTError`](https://developer.apple.com/documentation/corebluetooth/cbatterror-swift.struct)

An error that Core Bluetooth returns while using Attribute Protocol (ATT).
使用属性协议（ATT）时Core Bluetooth返回的错误。



### [Deprecated 弃用](https://developer.apple.com/documentation/CoreBluetooth#Deprecated)

#### [`enum CBCentralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate)

Values that represent the current state of a central manager object.
表示中央管理器对象的当前状态的。

`Deprecated 弃用`



#### [`enum CBPeripheralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate)

Values that represent the current state of the peripheral manager.
表示外围设备管理器当前状态的值。

`Deprecated 弃用`



#### Deprecated Constants 不推荐的常量

This document describes the constants found in the Core Bluetooth framework.
本文档描述了Core Bluetooth框架中的常量。



### [Variables 变量](https://developer.apple.com/documentation/CoreBluetooth#Variables)

#### [`let CBUUIDCharacteristicObservationScheduleString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicobservationschedulestring)

## [See Also 另见](https://developer.apple.com/documentation/CoreBluetooth#see-also)

### [Related Documentation 相关文件](https://developer.apple.com/documentation/CoreBluetooth#Related-Documentation)

[Core Bluetooth Programming Guide
核心蓝牙编程指南](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257)

