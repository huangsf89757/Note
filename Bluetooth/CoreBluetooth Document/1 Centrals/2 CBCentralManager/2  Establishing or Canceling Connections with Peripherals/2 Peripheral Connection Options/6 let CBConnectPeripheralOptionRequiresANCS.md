Global Variable 全局变量

# CBConnectPeripheralOptionRequiresANCS

An option to require Apple Notification Center Service (ANCS) when connecting a device.
连接设备时需要 Apple 通知中心服务 （ANCS） 的选项。

iOS 13.0+ ｜ iPadOS 13.0+ ｜ Mac Catalyst 13.1+ ｜ tvOS 13.0+ ｜ visionOS 1.0+ ｜ watchOS 6.0+ 

```
let CBConnectPeripheralOptionRequiresANCS: String
```



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionrequiresancs#see-also)

### [Options 选项](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionrequiresancs#Options)

[`let CBConnectPeripheralOptionEnableAutoReconnect: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenableautoreconnect)

A Boolean value that specifies whether the system automatically reconnects with a peripheral.
一个 Boolean 值，该值指定系统是否自动重新连接到外围设备。

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

[`let CBConnectPeripheralOptionStartDelayKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionstartdelaykey)

An option that indicates a delay before the system makes a connection.
指示系统建立连接之前延迟的选项。
