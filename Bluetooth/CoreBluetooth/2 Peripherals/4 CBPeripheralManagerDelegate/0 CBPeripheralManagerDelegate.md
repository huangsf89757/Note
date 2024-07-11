Protocol 协议

# CBPeripheralManagerDelegate CBPeripheralManager委托

A protocol that provides updates for local peripheral state and interactions with remote central devices.
一种协议，用于更新本地外设状态以及与远程中央设备的交互。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.0+macOS 10.10+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
protocol CBPeripheralManagerDelegate : NSObjectProtocol
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#overview)

The delegate of a [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) object must adopt the [`CBPeripheralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate) protocol, which consists of numerous optional methods and one required method. The delegate uses the protocol’s optional methods to verify publishing and advertising, and to monitor read, write, and subscription requests from remote central devices.
`CBPeripheralManager` 对象的委托必须采用该协议 `CBPeripheralManagerDelegate` ，该协议由许多可选方法和一个必需方法组成。委托使用协议的可选方法来验证发布和播发，并监视来自远程中央设备的读取、写入和订阅请求。

The protocol’s required one method, [`peripheralManagerDidUpdateState(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:)), which Core Bluetooth calls whenever the peripheral manager’s state updates to indicate whether the peripheral manager is available.
该协议需要一种方法， `peripheralManagerDidUpdateState(_:)` 每当外设管理器的状态更新时，Core Bluetooth 都会调用该方法以指示外设管理器是否可用。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#topics)

### [Monitoring Changes to the Peripheral Manager’s State 监视对外设管理器状态的更改](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Monitoring-Changes-to-the-Peripheral-Managers-State)

#### [`func peripheralManagerDidUpdateState(CBPeripheralManager)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:))

Tells the delegate the peripheral manager’s state updated.
告知委托外围设备管理器的状态已更新。

**Required 必填**



#### [`func peripheralManager(CBPeripheralManager, willRestoreState: [String : Any\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:willrestorestate:))

Tells the delegate the system is about to restore the peripheral manager.
告知委托系统即将恢复外围管理器。



#### Peripheral Manager State Restoration Options

外设管理器状态恢复选项

Keys used to specify options when restoring the state of a peripheral manager.
用于在恢复外设管理器状态时指定选项的键。



### [Adding Services 添加服务](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Adding-Services)

#### [`func peripheralManager(CBPeripheralManager, didAdd: CBService, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didadd:error:))

Tells the delegate the peripheral manager published a service to the local GATT database.
告知委托外围设备管理器向本地 GATT 数据库发布了服务。



### [Advertising Peripheral Data 广告外设数据](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Advertising-Peripheral-Data)

#### [`func peripheralManagerDidStartAdvertising(CBPeripheralManager, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidstartadvertising(_:error:))

Tells the delegate the peripheral manager started advertising the local peripheral device’s data.
告诉代理外围设备管理器开始播发本地外围设备的数据。



### [Monitoring Subscriptions to Characteristic Values 监视对特征值的订阅](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Monitoring-Subscriptions-to-Characteristic-Values)

#### [`func peripheralManager(CBPeripheralManager, central: CBCentral, didSubscribeTo: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didsubscribeto:))

Tells the delegate that a remote central device subscribed to a characteristic’s value.
告知委托远程中心设备订阅了特征的值。

**Required 必填**



#### [`func peripheralManager(CBPeripheralManager, central: CBCentral, didUnsubscribeFrom: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:central:didunsubscribefrom:))

Tells the delegate that a remote central device unsubscribed from a characteristic’s value.
告知委托远程中央设备取消订阅特征的值。

**Required 必填**



#### [`func peripheralManagerIsReady(toUpdateSubscribers: CBPeripheralManager)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerisready(toupdatesubscribers:))

Tells the delegate that a local peripheral device is ready to send characteristic value updates.
告知委托本地外围设备已准备好发送特征值更新。



### [Receiving Read and Write Requests 接收读写请求](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Receiving-Read-and-Write-Requests)

#### [`func peripheralManager(CBPeripheralManager, didReceiveRead: CBATTRequest)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceiveread:))

Tells the delegate that a local peripheral received an Attribute Protocol (ATT) read request for a characteristic with a dynamic value.
告知委托本地外设收到了具有动态值的特征的属性协议 （ATT） 读取请求。



#### [`func peripheralManager(CBPeripheralManager, didReceiveWrite: [CBATTRequest\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didreceivewrite:))

Tells the delegate that a local peripheral device received an Attribute Protocol (ATT) write request for a characteristic with a dynamic value.
告知委托本地外围设备收到了具有动态值的特征的属性协议 （ATT） 写入请求。



### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Using-L2CAP-Channels)

#### [`func peripheralManager(CBPeripheralManager, didPublishL2CAPChannel: CBL2CAPPSM, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didpublishl2capchannel:error:))

Tells the delegate that the peripheral manager created a listener for incoming L2CAP channel connections.
告知委托外围设备管理器为传入的 L2CAP 通道连接创建了一个侦听器。



#### [`func peripheralManager(CBPeripheralManager, didUnpublishL2CAPChannel: CBL2CAPPSM, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didunpublishl2capchannel:error:))

Tells the delegate that the peripheral manager removed a published service from the local system.
告知代理外围设备管理器从本地系统中删除了已发布的服务。



#### [`func peripheralManager(CBPeripheralManager, didOpen: CBL2CAPChannel?, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanager(_:didopen:error:))

Tells the delegate that the peripheral manager opened an L2CAP channel.
告知委托外围设备管理器打开了 L2CAP 通道。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#inherits-from)

- #### [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)

  

## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#see-also)

### [Peripherals 外设](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate#Peripherals)

[`class CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral)

A remote peripheral device.
远程外围设备。

[`protocol CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate)

A protocol that provides updates on the use of a peripheral’s services.
提供有关外围设备服务使用情况的更新的协议。

[`class CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager)

An object that manages and advertises peripheral services exposed by this app.
管理和播发此应用公开的外围服务的对象。

[`class CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)

A representation of common aspects of services offered by a peripheral.
表示外围设备提供的服务的常见方面。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
表示特征值的读取、写入和加密权限的值。
