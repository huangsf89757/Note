Instance Property Instance 属性

# delegate 委托

The delegate object specified to receive peripheral events.
指定用于接收外围事件的委托对象。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
weak var delegate: (any CBPeripheralDelegate)? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/delegate#Discussion)

For information about how to implement your peripheral delegate, see [`CBPeripheralDelegate`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate).
有关如何实现外围设备委托的信息，请参见 `CBPeripheralDelegate` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/delegate#see-also)

### [Identifying a Peripheral 识别外设](https://developer.apple.com/documentation/corebluetooth/cbperipheral/delegate#Identifying-a-Peripheral)

[`var name: String?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/name)

The name of the peripheral.
外围设备的名称。
