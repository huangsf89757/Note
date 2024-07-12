Class 类

# CBPeripheral 

A remote peripheral device.
远程外围设备。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
class CBPeripheral
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbperipheral#overview)

The [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class represents remote peripheral devices that your app discovers with a central manager (an instance of [`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)). Peripherals use universally unique identifiers (UUIDs), represented by [`NSUUID`](https://developer.apple.com/documentation/foundation/nsuuid) objects, to identify themselves. Peripherals may contain one or more services or provide useful information about their connected signal strength.
该 `CBPeripheral` 类表示应用使用中央管理器（实例 ） `CBCentralManager` 发现的远程外围设备。外围设备使用由 `NSUUID` 对象表示的通用唯一标识符 （UUID） 来标识自身。外围设备可能包含一项或多项服务，或提供有关其连接信号强度的有用信息。

You use this class to discover, explore, and interact with the services available on a remote peripheral that supports Bluetooth low energy. A service encapsulates the way part of the device behaves. For example, one service of a heart rate monitor may be to expose heart rate data from a sensor. Services themselves contain of characteristics or included services (references to other services). Characteristics provide further details about a peripheral’s service. For example, the heart rate service may contain multiple characteristics. One characteristic could describe the intended body location of the device’s heart rate sensor, and another characteristic could transmit the heart rate measurement data. Finally, characteristics contain any number of descriptors that provide more information about the characteristic’s value, such as a human-readable description and a way to format the value.
您可以使用此类来发现、浏览支持低功耗蓝牙的远程外围设备上可用的服务并与之交互。服务封装了设备部分的行为方式。例如，心率监测器的一项服务可能是公开来自传感器的心率数据。服务本身包含特征或包含的服务（对其他服务的引用）。特征提供有关外围设备服务的更多详细信息。例如，心率服务可能包含多个特征。一个特征可以描述设备心率传感器的预期身体位置，另一个特征可以传输心率测量数据。最后，特征包含任意数量的描述符，这些描述符提供有关特征值的更多信息，例如人类可读的描述和设置值格式的方法。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheral#topics)

### [Identifying a Peripheral 识别外设](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Identifying-a-Peripheral)

#### [`var name: String?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name)

The name of the peripheral.
外围设备的名称。



#### [`var delegate: (any CBPeripheralDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/delegate)

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。



### [Discovering Services 发现服务](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Discovering-Services)

#### [`func discoverServices([CBUUID\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:))

Discovers the specified services of the peripheral.
发现外围设备的指定服务。



#### [`func discoverIncludedServices([CBUUID\]?, for: CBService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverincludedservices(_:for:))

Discovers the specified included services of a previously-discovered service.
发现以前发现的服务的指定包含的服务。



#### [`var services: [CBService\]?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services)

A list of a peripheral’s discovered services.
外围设备发现的服务的列表。



### [Discovering Characteristics and Descriptors 发现特征和描述符](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Discovering-Characteristics-and-Descriptors)

#### [`func discoverCharacteristics([CBUUID\]?, for: CBService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:))

Discovers the specified characteristics of a service.
发现服务的指定特征。



#### [`func discoverDescriptors(for: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:))

Discovers the descriptors of a characteristic.
发现特征的描述符。



### [Reading Characteristic and Descriptor Values 读取特征和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Reading-Characteristic-and-Descriptor-Values)

#### [`func readValue(for: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-6u2kr)

Retrieves the value of a specified characteristic.
检索指定特征的值。



#### [`func readValue(for: CBDescriptor)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp)

Retrieves the value of a specified characteristic descriptor.
检索指定特征描述符的值。



### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Writing-Characteristic-and-Descriptor-Values)

#### [`func writeValue(Data, for: CBCharacteristic, type: CBCharacteristicWriteType)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:type:))

Writes the value of a characteristic.
写入特征的值。



#### [`func writeValue(Data, for: CBDescriptor)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:))

Writes the value of a characteristic descriptor.
写入特征描述符的值。



#### [`func maximumWriteValueLength(for: CBCharacteristicWriteType) -> Int`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/maximumwritevaluelength(for:))

The maximum amount of data, in bytes, you can send to a characteristic in a single write type.
可以发送到单个写入类型特征的最大数据量（以字节为单位）。



#### [`enum CBCharacteristicWriteType`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicwritetype)

Values representing the possible write types to a characteristic’s value.
表示特征值的可能写入类型的值。



### [Setting Notifications for a Characteristic’s Value 为特征值设置通知](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Setting-Notifications-for-a-Characteristics-Value)

#### [`func setNotifyValue(Bool, for: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:))

Sets notifications or indications for the value of a specified characteristic.
设置指定特征值的通知或指示。



### [Monitoring a Peripheral’s Connection State 监视外设的连接状态](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Monitoring-a-Peripherals-Connection-State)

#### [`var state: CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/state)

The connection state of the peripheral.
外围设备的连接状态。



#### [`enum CBPeripheralState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralstate)

Values representing the connection state of a peripheral.
表示外围设备连接状态的值。



#### [`var canSendWriteWithoutResponse: Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/cansendwritewithoutresponse)

A Boolean value that indicates whether the remote device can send a write without a response.
一个 Boolean 值，该值指示远程设备是否可以在没有响应的情况下发送写入。



### [Accessing a Peripheral’s Signal Strength 访问外设的信号强度](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Accessing-a-Peripherals-Signal-Strength)

#### [`func readRSSI()`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readrssi())

Retrieves the current RSSI value for the peripheral while connected to the central manager.
在连接到中央管理器时检索外围设备的当前 RSSI 值。



#### [`var rssi: NSNumber?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/rssi)

The Received Signal Strength Indicator (RSSI), in decibels, of the peripheral.
外设的接收信号强度指示器 （RSSI），以分贝为单位。

`Deprecated 荒废的`



### [Working with L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Working-with-L2CAP-Channels)

#### [`func openL2CAPChannel(CBL2CAPPSM)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/openl2capchannel(_:))

Attempts to open an L2CAP channel to the peripheral using the supplied Protocol/Service Multiplexer (PSM).
尝试使用随附的协议/服务多路复用器 （PSM） 打开通往外设的 L2CAP 通道。



#### [`class CBL2CAPChannel`](https://developer.apple.com/documentation/corebluetooth/cbl2capchannel)

A live L2CAP connection to a remote device.
与远程设备的实时 L2CAP 连接。



#### [`typealias CBL2CAPPSM`](https://developer.apple.com/documentation/corebluetooth/cbl2cappsm)

The type of PSM identifiers.
PSM 标识符的类型。



### [Working with Apple Notification Center Service (ANCS) 使用 Apple 通知中心服务 （ANCS）](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Working-with-Apple-Notification-Center-Service-ANCS)

#### [`var ancsAuthorized: Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/ancsauthorized)

A Boolean value that indicates if the remote device has authorization to receive data over ANCS protocol.
一个 Boolean 值，该值指示远程设备是否有权通过 ANCS 协议接收数据。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheral#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbperipheral#inherits-from)

- [`CBPeer`](https://developer.apple.com/documentation/corebluetooth/cbpeer)



### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheral#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSCopying`](https://developer.apple.com/documentation/foundation/nscopying)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral#see-also)

### [Peripherals 外设](https://developer.apple.com/documentation/corebluetooth/cbperipheral#Peripherals)

[`protocol CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate)

A protocol that provides updates on the use of a peripheral’s services.
提供有关外围设备服务使用情况的更新的协议。

[`class CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)

An object that manages and advertises peripheral services exposed by this app.
管理和播发此应用公开的外围服务的对象。

[`protocol CBPeripheralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate)

A protocol that provides updates for local peripheral state and interactions with remote central devices.
一种协议，用于更新本地外设状态以及与远程中央设备的交互。

[`class CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)

A representation of common aspects of services offered by a peripheral.
表示外围设备提供的服务的常见方面。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
表示特征值的读取、写入和加密权限的值。
