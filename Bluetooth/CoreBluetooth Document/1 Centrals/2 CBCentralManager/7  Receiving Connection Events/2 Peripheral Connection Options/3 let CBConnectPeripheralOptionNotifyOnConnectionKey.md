Global Variable 全局变量

# CBConnectPeripheralOptionNotifyOnConnectionKey

A Boolean value that specifies whether the system should display an alert when connecting a peripheral in the background.
一个 Boolean 值，该值指定系统在后台连接外围设备时是否应显示警报。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.13+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
let CBConnectPeripheralOptionNotifyOnConnectionKey: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyonconnectionkey#Discussion)

The value for this key is an [`NSNumber`](https://developer.apple.com/documentation/foundation/nsnumber) object. This key is useful for apps that haven’t specified the `bluetooth-central` background mode and can’t display their own alert. If more than one app requests a notification for a given peripheral, the one that was most recently in the foreground receives the alert. If the key isn’t specified, the default value is [`false`](https://developer.apple.com/documentation/swift/false).
此键的值是一个 `NSNumber` 对象。此键对于未指定 `bluetooth-central` 后台模式且无法显示自己的警报的应用非常有用。如果多个应用请求给定外围设备的通知，则最近处于前台的外围设备将收到警报。如果未指定键，则默认值为 `false` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyonconnectionkey#see-also)

### [Options 选项](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionnotifyonconnectionkey#Options)

[`let CBConnectPeripheralOptionEnableAutoReconnect: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenableautoreconnect)

A Boolean value that specifies whether the system automatically reconnects with a peripheral.
一个 Boolean 值，该值指定系统是否自动重新连接到外围设备。

[`let CBConnectPeripheralOptionEnableTransportBridgingKey: String`](https://developer.apple.com/documentation/corebluetooth/cbconnectperipheraloptionenabletransportbridgingkey)

An option to bridge classic Bluetooth technology profiles, if already connected over Bluetooth Low Energy.
如果已通过低功耗蓝牙连接，则可桥接经典蓝牙技术配置文件的选项。

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
