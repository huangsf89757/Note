Instance Property Instance 属性

# delegate

The delegate object that you want to receive central manager events.
要接收中央管理器事件的委托对象。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
weak var delegate: (any CBCentralManagerDelegate)? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/delegate#Discussion)

For information about how to implement your central manager delegate, see [`CBCentralManagerDelegate`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate).
有关如何实现中央管理器委托的信息，请参见 `CBCentralManagerDelegate` 。
