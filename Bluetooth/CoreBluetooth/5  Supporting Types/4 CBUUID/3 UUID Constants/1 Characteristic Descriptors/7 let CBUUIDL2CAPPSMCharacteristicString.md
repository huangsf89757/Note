Global Variable 全局变量

# CBUUIDL2CAPPSMCharacteristicString

The PSM of an L2CAP channel associated with the GATT service containing this characteristic.
与包含此特征的GATT服务关联的L2CAP通道的PSM。

iOS 11.0+iPadOS 11.0+Mac Catalyst 13.1+macOS 10.13+tvOS 11.0+visionOS 1.0+watchOS 4.0+

```
let CBUUIDL2CAPPSMCharacteristicString: String
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbuuidl2cappsmcharacteristicstring#Discussion)

This PSM is a little-endian [`UInt16`](https://developer.apple.com/documentation/Swift/UInt16). Servers can publish this characteristic with the UUID `ABDD3056-28FA-441D-A470-55A75A52553A`.
这个PSM是一个little-endian `UInt16` 。服务器可以使用UUID `ABDD3056-28FA-441D-A470-55A75A52553A` 发布此特征。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbuuidl2cappsmcharacteristicstring#see-also)

### [Characteristic Descriptors 特征描述符](https://developer.apple.com/documentation/corebluetooth/cbuuidl2cappsmcharacteristicstring#Characteristic-Descriptors)

[`let CBUUIDCharacteristicExtendedPropertiesString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicextendedpropertiesstring)

The UUID for the Extended Properties descriptor, as a string.
扩展属性描述符的UUID，作为字符串。

[`let CBUUIDCharacteristicUserDescriptionString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicuserdescriptionstring)

The UUID for the User Description descriptor, as a string.
用户描述描述符的UUID，作为字符串。

[`let CBUUIDClientCharacteristicConfigurationString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidclientcharacteristicconfigurationstring)

The UUID for the Client Configuration descriptor, as a string.
客户端配置描述符的UUID，作为字符串。

[`let CBUUIDServerCharacteristicConfigurationString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidservercharacteristicconfigurationstring)

The UUID for the Server Configuration descriptor, as a string.
服务器配置描述符的UUID，作为字符串。

[`let CBUUIDCharacteristicFormatString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicformatstring)

The UUID for the Presentation Format descriptor, as a string.
表示格式描述符的UUID，作为字符串。

[`let CBUUIDCharacteristicAggregateFormatString: String`](https://developer.apple.com/documentation/corebluetooth/cbuuidcharacteristicaggregateformatstring)

The UUID for the Aggregate Format descriptor, as a string.
聚合格式描述符的UUID，作为字符串。
