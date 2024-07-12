Protocol 协议

# CBCentralManagerDelegate

A protocol that provides updates for the discovery and management of peripheral devices.
为外围设备的发现和管理提供更新的协议。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
protocol CBCentralManagerDelegate : NSObjectProtocol
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#overview)

The [`CBCentralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate) protocol defines the methods that a delegate of a [`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager) object must adopt. The optional methods of the protocol allow the delegate to monitor the discovery, connectivity, and retrieval of peripheral devices. The only required method is [`centralManagerDidUpdateState(_:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)); the central manager calls this when its state updates, thereby indicating the availability of the central manager.
该协议 `CBCentralManagerDelegate` 定义 `CBCentralManager` 对象委托必须采用的方法。该协议的可选方法允许委托监视外围设备的发现、连接和检索。唯一需要的方法是 `centralManagerDidUpdateState(_:)` ;中央管理器在其状态更新时调用此函数，从而指示中央管理器的可用性。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#topics)

### [Monitoring Connections with Peripherals 监视与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#Monitoring-Connections-with-Peripherals)

#### [`func centralManager(CBCentralManager, didConnect: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didconnect:))

Tells the delegate that the central manager connected to a peripheral.
告知委托中央管理器已连接到外围设备。



#### [`func centralManager(CBCentralManager, didDisconnectPeripheral: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:error:))

Tells the delegate that the central manager disconnected from a peripheral.
告知委托中央管理器已断开与外围设备的连接。

**Required 必填**



#### [`func centralManager(CBCentralManager, didFailToConnect: CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didfailtoconnect:error:))

Tells the delegate the central manager failed to create a connection with a peripheral.
告知代理中央管理器未能与外围设备建立连接。



#### [`func centralManager(CBCentralManager, connectionEventDidOccur: CBConnectionEvent, for: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:connectioneventdidoccur:for:))

Tells the delegate that a connection event occurred which matches the registered options.
告知委托发生了与已注册选项匹配的连接事件。

**Required 必填**



### [Discovering and Retrieving Peripherals 发现和检索外围设备](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#Discovering-and-Retrieving-Peripherals)

#### [`func centralManager(CBCentralManager, didDiscover: CBPeripheral, advertisementData: [String : Any\], rssi: NSNumber)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:))

Tells the delegate the central manager discovered a peripheral while scanning for devices.
告诉委托中央管理器在扫描设备时发现了外围设备。

**Required 必填**



#### Advertisement Data Retrieval Keys

播发数据检索密钥

Keys used to specify items in a dictionary of peripheral advertisement data.
用于指定外围通告数据字典中的项的键。



### [Monitoring the Central Manager’s State 监视中央管理器的状态](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#Monitoring-the-Central-Managers-State)

#### [`func centralManagerDidUpdateState(CBCentralManager)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:))

Tells the delegate the central manager’s state updated.
告知委托中央经理的状态已更新。

**Required 必填**



#### [`func centralManager(CBCentralManager, willRestoreState: [String : Any\])`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:willrestorestate:))

Tells the delegate the system is about to restore the central manager, as part of relaunching the app into the background.
告知委托系统即将还原中央管理器，作为将应用程序重新启动到后台的一部分。



### [Monitoring the Central Manager’s Authorization 监控中央管理器的授权](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#Monitoring-the-Central-Managers-Authorization)

#### [`func centralManager(CBCentralManager, didUpdateANCSAuthorizationFor: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didupdateancsauthorizationfor:))

Tells the delegate the authorization status changed for a ANCS-requiring connected peripheral.
告知代理需要 ANCS 的已连接外围设备的授权状态已更改。

**Required 必填**



### [Instance Methods 实例方法](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#Instance-Methods)

#### [`func centralManager(CBCentralManager, didDisconnectPeripheral: CBPeripheral, timestamp: CFAbsoluteTime, isReconnecting: Bool, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:timestamp:isreconnecting:error:))



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#inherits-from)

- #### [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#see-also)

### [Centrals 中央设备](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate#Centrals)

[`class CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral)

A remote device connected to a local app, which is acting as a peripheral.
连接到本地应用的远程设备，该应用充当外围设备。

[`class CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)

An object that scans for, discovers, connects to, and manages peripherals.
扫描、发现、连接和管理外围设备的对象。
