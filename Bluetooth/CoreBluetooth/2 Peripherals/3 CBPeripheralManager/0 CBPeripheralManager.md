Class 类

# CBPeripheralManager

An object that manages and advertises peripheral services exposed by this app.
管理和播发此应用公开的外围服务的对象。

iOS 6.0+ iOS的6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
class CBPeripheralManager
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#overview)

Core Bluetooth uses [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) objects to manage published services within the local peripheral’s Generic Attribute Profile (GATT) database and to advertise these services to central devices (represented by [`CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbcentral) objects). While a service is in the database, any connected central can see and connect to it. That said, if your app hasn’t specified the `bluetooth-peripheral` background mode, the contents of its services become disabled when it’s in the background or in a suspended state. In this scenario, any remote central trying to access the service’s characteristic value or characteristic descriptors receives an error.
核心蓝牙使用 `CBPeripheralManager` 对象来管理本地外设的通用属性配置文件 （GATT） 数据库中的已发布服务，并将这些服务通告到中央设备（由 `CBCentral` 对象表示）。当服务位于数据库中时，任何连接的中心都可以看到并连接到它。也就是说，如果您的应用未指定 `bluetooth-peripheral` 后台模式，则当其服务处于后台或挂起状态时，其服务的内容将被禁用。在这种情况下，任何尝试访问服务的特征值或特征描述符的远程中心都会收到错误。

Before you call [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) methods, the peripheral manager object must be in the powered-on state, as indicated by the [`CBPeripheralManagerState.poweredOn`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate/poweredon). This state indicates that the device (your iPhone or iPad, for instance) supports Bluetooth low energy and that its Bluetooth is on and available for use.
在调用 `CBPeripheralManager` 方法之前，外设管理器对象必须处于已打开电源的状态，如 `CBPeripheralManagerState.poweredOn` 所示。此状态表示设备（例如 iPhone 或 iPad）支持低功耗蓝牙，并且其蓝牙已打开并可供使用。

In watchOS, tvOS, and visionOS, you can’t advertise services using a [`CBPeripheralManager`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager) object because support for doing so is unavailable.
在 watchOS、Apple tvOS 和 visionOS 中，您无法使用 `CBPeripheralManager` 对象播发服务，因为不支持这样做。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#topics)

### [Initializing a Peripheral Manager 初始化外设管理器](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Initializing-a-Peripheral-Manager)

#### [`convenience init()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init())

Initializes the peripheral manager without a delegate.
在没有委托的情况下初始化外设管理器。



#### [`convenience init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:))

Initializes the peripheral manager with a specified delegate and dispatch queue.
使用指定的委托和调度队列初始化外设管理器。



#### [`init(delegate: (any CBPeripheralManagerDelegate)?, queue: dispatch_queue_t?, options: [String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/init(delegate:queue:options:))

Initializes the peripheral manager with a specified delegate, dispatch queue, and initialization options.
使用指定的委托、调度队列和初始化选项初始化外设管理器。



#### [`var delegate: (any CBPeripheralManagerDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/delegate)

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。



#### Peripheral Manager Initialization Options

外设管理器初始化选项

Keys used to specify options when creating a peripheral manager.
用于在创建外设管理器时指定选项的键。



### [Monitoring the State of a Peripheral Manager 监视外设管理器的状态](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Monitoring-the-State-of-a-Peripheral-Manager)

#### [`class func authorizationStatus() -> CBPeripheralManagerAuthorizationStatus`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/authorizationstatus())

Returns the app’s authorization status for sharing data while in the background.
返回应用在后台共享数据的授权状态。

`Deprecated 荒废的`



#### [`enum CBPeripheralManagerAuthorizationStatus`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus)

Values representing the current authorization state of the peripheral manager.
表示外设管理器当前授权状态的值。

`Deprecated 荒废的`



#### [`enum CBPeripheralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate)

Values that represent the current state of the peripheral manager.
表示外围管理器的当前状态的值。

`Deprecated 荒废的`



### [Adding and Removing Services 添加和删除服务](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Adding-and-Removing-Services)

#### [`func add(CBMutableService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/add(_:))

Publishes a service and any of its associated characteristics and characteristic descriptors to the local GATT database.
将服务及其任何关联的特征和特征描述符发布到本地 GATT 数据库。



#### [`func remove(CBMutableService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/remove(_:))

Removes a specified published service from the local GATT database.
从本地 GATT 数据库中删除指定的已发布服务。



#### [`func removeAllServices()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/removeallservices())

Removes all published services from the local GATT database.
从本地 GATT 数据库中删除所有已发布的服务。



### [Managing Advertising 管理广告](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Managing-Advertising)

#### [`func startAdvertising([String : Any\]?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/startadvertising(_:))

Advertises peripheral manager data.
播发外设管理器数据。



#### Advertising Data 

广告数据



#### [`func stopAdvertising()`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/stopadvertising())

Stops advertising peripheral manager data.
停止通告外设管理器数据。



#### [`var isAdvertising: Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/isadvertising)

A Boolean value that indicates whether the peripheral is advertising data.
一个 Boolean 值，该值指示外围设备是否为播发数据。



### [Sending Updates of a Characteristic’s Value 发送特征值的更新](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Sending-Updates-of-a-Characteristics-Value)

#### [`func updateValue(Data, for: CBMutableCharacteristic, onSubscribedCentrals: [CBCentral\]?) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:))

Send an updated characteristic value to one or more subscribed centrals, using a notification or indication.
使用通知或指示将更新的特征值发送到一个或多个订阅的中心。



### [Responding to Read and Write Requests 响应读取和写入请求](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Responding-to-Read-and-Write-Requests)

#### [`func respond(to: CBATTRequest, withResult: CBATTError.Code)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:))

Responds to a read or write request from a connected central.
响应来自连接中心的读取或写入请求。



### [Setting Connection Latency 设置连接延迟](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Setting-Connection-Latency)

#### [`func setDesiredConnectionLatency(CBPeripheralManagerConnectionLatency, for: CBCentral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/setdesiredconnectionlatency(_:for:))

Sets the desired connection latency for an existing connection to a central device.
为与中央设备的现有连接设置所需的连接延迟。



#### [`enum CBPeripheralManagerConnectionLatency`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency)

Values representing the connection latency of the peripheral manager.
表示外设管理器的连接延迟的值。



### [Using L2CAP Channels 使用 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Using-L2CAP-Channels)

#### [`func publishL2CAPChannel(withEncryption: Bool)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/publishl2capchannel(withencryption:))

Creates a listener for incoming L2CAP channel connections.
为传入的 L2CAP 通道连接创建侦听器。



#### [`func unpublishL2CAPChannel(CBL2CAPPSM)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/unpublishl2capchannel(_:))

Removes a published service from the local system.
从本地系统中删除已发布的服务。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#inherits-from)

- #### [`CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager)

  

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#conforms-to)

- [`CVarArg`](https://developer.apple.com/documentation/Swift/CVarArg)
- [`CustomDebugStringConvertible`](https://developer.apple.com/documentation/Swift/CustomDebugStringConvertible)
- [`CustomStringConvertible`](https://developer.apple.com/documentation/Swift/CustomStringConvertible)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#see-also)

### [Peripherals 外设](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager#Peripherals)

[`class CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral)

A remote peripheral device.
远程外围设备。

[`protocol CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate)

A protocol that provides updates on the use of a peripheral’s services.
提供有关外围设备服务使用情况的更新的协议。

[`protocol CBPeripheralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate)

A protocol that provides updates for local peripheral state and interactions with remote central devices.
一种协议，用于更新本地外设状态以及与远程中央设备的交互。

[`class CBAttribute`](https://developer.apple.com/documentation/corebluetooth/cbattribute)

A representation of common aspects of services offered by a peripheral.
表示外围设备提供的服务的常见方面。

[`struct CBAttributePermissions`](https://developer.apple.com/documentation/corebluetooth/cbattributepermissions)

Values that represent the read, write, and encryption permissions for a characteristic’s value.
表示特征值的读取、写入和加密权限的值。
