Instance Property 实例属性

# value 

The value of the descriptor.
描述符的值。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var value: Any? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbdescriptor/value#Discussion)

The documentation for [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) details the value types for the various descriptor types.
`CBUUID` 的文档详细说明了各种描述符类型的值类型。

You can read the value of a descriptor by calling the [`readValue(for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/readvalue(for:)-91hhp) method of the [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class. You can write the value of a descriptor by calling the [`writeValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)) method of the [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class. You can’t, however, use the [`writeValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/writevalue(_:for:)) method to write the value of a client configuration descriptor ([`CBUUIDClientCharacteristicConfigurationString`](https://developer.apple.com/documentation/corebluetooth/cbuuidclientcharacteristicconfigurationstring)). Instead, you use the [`setNotifyValue(_:for:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/setnotifyvalue(_:for:)) method of the [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) class to configure client indications or notifications of a characteristic’s value on a server.
您可以通过调用 `CBPeripheral` 类的 `readValue(for:)` 方法来读取描述符的值。您可以通过调用 `CBPeripheral` 类的 `writeValue(_:for:)` 方法来写入描述符的值。但是，您不能使用 `writeValue(_:for:)` 方法来写入客户端配置描述符的值（ `CBUUIDClientCharacteristicConfigurationString` ）。相反，您可以使用 `CBPeripheral` 类的 `setNotifyValue(_:for:)` 方法来配置客户端指示或服务器上特征值的通知。
