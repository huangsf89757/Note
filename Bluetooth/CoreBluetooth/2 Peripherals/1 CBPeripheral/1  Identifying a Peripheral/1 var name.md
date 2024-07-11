Instance Property Instance 属性

# name 名字

The name of the peripheral.
外围设备的名称。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
var name: String? { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name#Discussion)

Use this property to retrieve a human-readable name of the peripheral. A peripheral may have two different name types: one that the device advertises and another that the device publishes in its database as its Bluetooth low energy Generic Access Profile (GAP) device name. If a peripheral has both types of names, this property returns its GAP device name.
使用此属性可检索外围设备的人类可读名称。外围设备可能具有两种不同的名称类型：一种是设备播发的名称类型，另一种是设备在其数据库中作为其低功耗蓝牙通用访问配置文件 （GAP） 设备名称发布的名称。如果外围设备具有这两种类型的名称，则此属性返回其 GAP 设备名称。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name#topics)

### [Related Documentation 相关主题](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name#Related-Documentation)

#### [`func peripheralDidUpdateName(CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:))

Tells the delegate that a peripheral’s name changed.
告知代理外围设备的名称已更改。

**Required 必填**



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name#see-also)

### [Identifying a Peripheral 识别外设](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name#Identifying-a-Peripheral)

[`var delegate: (any CBPeripheralDelegate)?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/delegate)

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。
