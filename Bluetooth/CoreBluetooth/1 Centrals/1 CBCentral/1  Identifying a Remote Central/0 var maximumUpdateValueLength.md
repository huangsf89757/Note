Instance Property 实例属性

# maximumUpdateValueLength 

The maximum amount of data, in bytes, that the central can receive in a single notification or indication.
中心节点在单个通知或指示中可以接收的最大数据量（以字节为单位）。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+

```
var maximumUpdateValueLength: Int { get }
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcentral/maximumupdatevaluelength#topics)

### [Related Documentation 相关文件](https://developer.apple.com/documentation/corebluetooth/cbcentral/maximumupdatevaluelength#Related-Documentation)

#### [`func updateValue(Data, for: CBMutableCharacteristic, onSubscribedCentrals: [CBCentral\]?) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/updatevalue(_:for:onsubscribedcentrals:))

Send an updated characteristic value to one or more subscribed centrals, using a notification or indication.
使用通知或指示向一个或多个订阅中心发送更新的特征值。
