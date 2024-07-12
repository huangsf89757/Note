Protocol 协议

# CBPeripheralDelegate

A protocol that provides updates on the use of a peripheral’s services.
提供有关外围设备服务使用情况的更新的协议。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.0+ ｜ macOS 10.10+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 4.0+ 

```
protocol CBPeripheralDelegate : NSObjectProtocol
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#overview)

The delegate of a [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) object must adopt the [`CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate) protocol. The delegate uses this protocol’s methods to monitor the discovery, exploration, and interaction of a remote peripheral’s services and properties. This protocol doesn’t have any required methods.
`CBPeripheral` 对象的委托必须采用该协议 `CBPeripheralDelegate` 。委托使用此协议的方法来监视远程外围设备的服务和属性的发现、探索和交互。此协议没有任何必需的方法。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#topics)

### [Discovering Services 发现服务](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Discovering-Services)

#### [`func peripheral(CBPeripheral, didDiscoverServices: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:))

Tells the delegate that peripheral service discovery succeeded.
告知委托外围服务发现成功。



#### [`func peripheral(CBPeripheral, didDiscoverIncludedServicesFor: CBService, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverincludedservicesfor:error:))

Tells the delegate that discovering included services within the indicated service completed.
告知委托已完成发现指示服务中的包含服务。



### [Discovering Characteristics and their Descriptors 发现特征及其描述符](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Discovering-Characteristics-and-their-Descriptors)

#### [`func peripheral(CBPeripheral, didDiscoverCharacteristicsFor: CBService, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:))

Tells the delegate that the peripheral found characteristics for a service.
告知委托外围设备找到了服务的特征。



#### [`func peripheral(CBPeripheral, didDiscoverDescriptorsFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverdescriptorsfor:error:))

Tells the delegate that the peripheral found descriptors for a characteristic.
告诉委托外围设备找到了特征的描述符。

**Required 必填**



### [Retrieving Characteristic and Descriptor Values 检索特征和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Retrieving-Characteristic-and-Descriptor-Values)

#### [`func peripheral(CBPeripheral, didUpdateValueFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1xyna)

Tells the delegate that retrieving the specified characteristic’s value succeeded, or that the characteristic’s value changed.
告知委托检索指定特征的值已成功，或者特征的值已更改。

**Required 必填**



#### [`func peripheral(CBPeripheral, didUpdateValueFor: CBDescriptor, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatevaluefor:error:)-1t3wm)

Tells the delegate that retrieving a specified characteristic descriptor’s value succeeded.
告知委托检索指定特征描述符的值已成功。



### [Writing Characteristic and Descriptor Values 编写特征值和描述符值](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Writing-Characteristic-and-Descriptor-Values)

#### [`func peripheral(CBPeripheral, didWriteValueFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-4f5ea)

Tells the delegate that the peripheral successfully set a value for the characteristic.
告知委托外设已成功设置特征值。



#### [`func peripheral(CBPeripheral, didWriteValueFor: CBDescriptor, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didwritevaluefor:error:)-1ybl3)

Tells the delegate that the peripheral successfully set a value for the descriptor.
告知委托外围设备已成功为描述符设置值。



#### [`func peripheralIsReady(toSendWriteWithoutResponse: CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheralisready(tosendwritewithoutresponse:))

Tells the delegate that a peripheral is again ready to send characteristic updates.
告知委托外围设备再次准备好发送特征更新。



### [Managing Notifications for a Characteristic’s Value 管理特征值的通知](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Managing-Notifications-for-a-Characteristics-Value)

#### [`func peripheral(CBPeripheral, didUpdateNotificationStateFor: CBCharacteristic, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didupdatenotificationstatefor:error:))

Tells the delegate that the peripheral received a request to start or stop providing notifications for a specified characteristic’s value.
告知委托外围设备收到开始或停止为指定特征值提供通知的请求。



### [Retrieving a Peripheral’s RSSI Data 检索外设的 RSSI 数据](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Retrieving-a-Peripherals-RSSI-Data)

#### [`func peripheral(CBPeripheral, didReadRSSI: NSNumber, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didreadrssi:error:))

Tells the delegate that retrieving the value of the peripheral’s current Received Signal Strength Indicator (RSSI) succeeded.
告知委托已成功检索外设的当前接收信号强度指示器 （RSSI） 的值。



#### [`func peripheralDidUpdateRSSI(CBPeripheral, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdaterssi(_:error:))

Tells the delegate that retrieving the value of the peripheral’s current Received Signal Strength Indicator (RSSI) succeeded.
告知委托已成功检索外设的当前接收信号强度指示器 （RSSI） 的值。

**Required 必填**

`Deprecated 荒废的`



### [Monitoring Changes to a Peripheral’s Name or Services 监视对外围设备名称或服务的更改](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Monitoring-Changes-to-a-Peripherals-Name-or-Services)

#### [`func peripheralDidUpdateName(CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:))

Tells the delegate that a peripheral’s name changed.
告知代理外围设备的名称已更改。

**Required 必填**



#### [`func peripheral(CBPeripheral, didModifyServices: [CBService\])`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didmodifyservices:))

Tells the delegate that a peripheral’s services changed.
告知代理外围设备的服务已更改。

**Required 必填**



### [Monitoring L2CAP Channels 监控 L2CAP 通道](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Monitoring-L2CAP-Channels)

#### [`func peripheral(CBPeripheral, didOpen: CBL2CAPChannel?, error: (any Error)?)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didopen:error:))

Delivers the result of an attempt to open an L2CAP channel.
提供尝试打开 L2CAP 通道的结果。



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#relationships)

### [Inherits From 继承自](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#inherits-from)

- #### [`NSObjectProtocol`](https://developer.apple.com/documentation/objectivec/nsobjectprotocol)

  

## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#see-also)

### [Peripherals 外设](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate#Peripherals)

[`class CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral)

A remote peripheral device.
远程外围设备。

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
