Class 类

# CBCentralManager

An object that scans for, discovers, connects to, and manages peripherals.
扫描、发现、连接和管理外围设备的对象。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ ｜ 

```
class CBCentralManager
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#overview)

[`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager) objects manage discovered or connected remote peripheral devices (represented by [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) objects), including scanning for, discovering, and connecting to advertising peripherals.
`CBCentralManager` 对象管理发现或连接的远程外围设备（由 `CBPeripheral` 对象表示），包括扫描、发现和连接到广告外围设备。

Before calling the [`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager) methods, set the state of the central manager object to powered on, as indicated by the [`CBCentralManagerState.poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate/poweredon) constant. This state indicates that the central device (your iPhone or iPad, for instance) supports Bluetooth low energy and that Bluetooth is on and available for use.
在调用 `CBCentralManager` 方法之前，将中央管理器对象的状态设置为通电，如 `CBCentralManagerState.poweredOn` 常量所示。此状态表示中央设备（例如您的iPhone或iPad）支持蓝牙低功耗，并且蓝牙已打开并可供使用。

## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#topics)

### [Initializing a Central Manager 初始化中央管理器](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Initializing-a-Central-Manager)

#### [`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init())

Initializes the central manager without a delegate.
在没有委派的情况下访问中央管理器。



#### [`convenience init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:))

Initializes the central manager with a specified delegate and dispatch queue.
使用指定的委托和分派队列对中央管理器进行初始化。



#### [`init(delegate: (any CBCentralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/init(delegate:queue:options:))

Initializes the central manager with specified delegate, dispatch queue, and initialization options.
使用指定的委托、分派队列和初始化选项重新配置中央管理器。



#### Central Manager Initialization Options

中央管理器选项

Keys used to pass options when initializing a central manager.
初始化中央管理器时用于传递选项的键。



#### Central Manager State Restoration Options

中央管理器状态恢复选项

Keys used to pass state restoration options to the central manager initializer.
用于将状态恢复选项传递给中央管理器初始化程序的键。



### [Establishing or Canceling Connections with Peripherals 建立或取消与外围设备的连接](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Establishing-or-Canceling-Connections-with-Peripherals)

#### [`func connect(CBPeripheral, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/connect(_:options:))

Establishes a local connection to a peripheral.
断开到外围设备的本地连接。



#### Peripheral Connection Options

外设连接选项

Keys used to pass options when connecting to a peripheral.
连接到外围设备时用于传递选项的键。



#### [`func cancelPeripheralConnection(CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/cancelperipheralconnection(_:))

Cancels an active or pending local connection to a peripheral.
取消到外围设备的活动或挂起的本地连接。



### [Retrieving Lists of Peripherals 检索外围设备列表](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Retrieving-Lists-of-Peripherals)

#### [`func retrieveConnectedPeripherals(withServices: [CBUUID\]) -> [CBPeripheral]`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveconnectedperipherals(withservices:))

Returns a list of the peripherals connected to the system whose services match a given set of criteria.
返回连接到系统的外围设备的列表，这些外围设备的服务符合给定的条件集。



#### [`func retrievePeripherals(withIdentifiers: [UUID\]) -> [CBPeripheral]`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/retrieveperipherals(withidentifiers:))

Returns a list of known peripherals by their identifiers.
返回已知外围设备的标识符列表。



### [Scanning or Stopping Scans of Peripherals 扫描或停止扫描外围设备](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Scanning-or-Stopping-Scans-of-Peripherals)

#### [`func scanForPeripherals(withServices: [CBUUID\]?, options: [String : Any]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:))

Scans for peripherals that are advertising services.
扫描属于广告服务的外围设备。



#### Peripheral Scanning Options

外围设备扫描选项

Keys used to pass options when scanning for peripherals.
扫描外围设备时用于传递选项的键。



#### [`func stopScan()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/stopscan())

Asks the central manager to stop scanning for peripherals.
要求中央管理器停止扫描外围设备。



#### [`var isScanning: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/isscanning)

A Boolean value that indicates whether the central is currently scanning.
指示中心当前是否正在扫描的布尔值。



### [Inspecting Feature Support 检查功能支持](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Inspecting-Feature-Support)

[`class func supports(CBCentralManager.Feature) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/supports(_:))

Returns a Boolean that indicates whether the device supports a specific set of features.
返回一个布尔值，指示设备是否支持一组特定的功能。

[`struct Feature`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature)

An option set of device-specific features.
设备特定功能的选项集。

### [Monitoring Properties 监控属性](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Monitoring-Properties)

[`var delegate: (any CBCentralManagerDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/delegate)

The delegate object that you want to receive central manager events.
要接收中央管理器事件的委托对象。

### [Receiving Connection Events 接收连接事件](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Receiving-Connection-Events)

[`func registerForConnectionEvents(options: [CBConnectionEventMatchingOption : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/registerforconnectionevents(options:))

Register for an event notification when the central manager makes a connection matching the given options.
当中央管理器建立与给定选项匹配的连接时，注册事件通知。



Peripheral Connection Options
外设连接选项

Keys used to pass options when connecting to a peripheral.
连接到外围设备时用于传递选项的键。

[`enum CBConnectionEvent`](https://developer.apple.com/documentation/corebluetooth/cbconnectionevent)

A change to the connection state of a peer.
对等体的连接状态的更改。

[`struct CBConnectionEventMatchingOption`](https://developer.apple.com/documentation/corebluetooth/cbconnectioneventmatchingoption)

A set of options to use when registering for connection events.
注册连接事件时使用的一组选项。

### [Deprecated 弃用](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Deprecated)

[`enum CBCentralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerstate)

Values that represent the current state of a central manager object.
表示中央管理器对象的当前状态的。

Deprecated 弃用

## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#inherits-from)

- [`CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)

## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#see-also)

### [Centrals 中锋](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager#Centrals)

[`class CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral)

A remote device connected to a local app, which is acting as a peripheral.
连接到本地应用程序的远程设备，该应用程序充当外围设备。

[`protocol CBCentralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate)

A protocol that provides updates for the discovery and management of peripheral devices.
为发现和管理外围设备提供更新的协议。
