Global Variable 全局变量

# CBConnectPeripheralOptionEnableAutoReconnect

A Boolean value that specifies whether the system automatically reconnects with a peripheral.
一个 Boolean 值，该值指定系统是否自动重新连接到外围设备。

iOS 17.0+ ｜ iPadOS 17.0+ ｜ Mac Catalyst 17.0+ ｜ macOS 14.0+ ｜ tvOS 17.0+ ｜ visionOS 1.0+ ｜ watchOS 10.0+ 

```
let CBConnectPeripheralOptionEnableAutoReconnect: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenableautoreconnect#Discussion)

After a peripheral device connects, this setting enables the system to initiate a connection to the peer device automatically when the link drops. The system uses [`centralManager(_:didDisconnectPeripheral:timestamp:isReconnecting:error:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddisconnectperipheral:timestamp:isreconnecting:error:)) to notify the caller about the disconnection.
外围设备连接后，此设置使系统能够在链路断开时自动启动与对等设备的连接。系统用于 `centralManager(_:didDisconnectPeripheral:timestamp:isReconnecting:error:)` 通知呼叫者断开连接。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenableautoreconnect#see-also)

### [Options 选项](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenableautoreconnect#Options)

[`let CBConnectPeripheralOptionEnableTransportBridgingKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenabletransportbridgingkey)

An option to bridge classic Bluetooth technology profiles, if already connected over Bluetooth Low Energy.
如果已通过低功耗蓝牙连接，则可桥接经典蓝牙技术配置文件的选项。

[`let CBConnectPeripheralOptionNotifyOnConnectionKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyonconnectionkey)

A Boolean value that specifies whether the system should display an alert when connecting a peripheral in the background.
一个 Boolean 值，该值指定系统在后台连接外围设备时是否应显示警报。

[`let CBConnectPeripheralOptionNotifyOnDisconnectionKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyondisconnectionkey)

A Boolean value that specifies whether the system should display an alert when disconnecting a peripheral in the background.
一个 Boolean 值，该值指定在后台断开外围设备连接时系统是否应显示警报。

[`let CBConnectPeripheralOptionNotifyOnNotificationKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyonnotificationkey)

A Boolean value that specifies whether the system should display an alert for any notification sent by a peripheral.
一个 Boolean 值，该值指定系统是否应针对外围设备发送的任何通知显示警报。

[`let CBConnectPeripheralOptionRequiresANCS: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionrequiresancs)

An option to require Apple Notification Center Service (ANCS) when connecting a device.
连接设备时需要 Apple 通知中心服务 （ANCS） 的选项。

[`let CBConnectPeripheralOptionStartDelayKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionstartdelaykey)

An option that indicates a delay before the system makes a connection.
指示系统建立连接之前延迟的选项。
