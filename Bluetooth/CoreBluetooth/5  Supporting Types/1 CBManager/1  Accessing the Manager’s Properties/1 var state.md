Instance Property 实例属性

# state 

The current state of the manager.
管理器的当前状态。

iOS 10.0+iPadOS 10.0+Mac Catalyst 13.1+macOS 10.13+tvOS 10.0+visionOS 1.0+watchOS 3.0+

```
var state: CBManagerState { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmanager/state#Discussion)

This state is initially set to [`CBManagerState.unknown`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate/unknown). When the state updates, the manager calls its delegate’s [`centralManagerDidUpdateState(_:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)) method.
此状态最初设置为 `CBManagerState.unknown` 。当状态更新时，管理器调用其委托的 `centralManagerDidUpdateState(_:)` 方法。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmanager/state#see-also)

### [Accessing the Manager’s Properties 删除管理员的属性](https://developer.apple.com/documentation/corebluetooth/cbmanager/state#Accessing-the-Managers-Properties)

[`enum CBManagerState`](https://developer.apple.com/documentation/corebluetooth/cbmanagerstate)

The possible states of a Core Bluetooth manager.
核心蓝牙管理器的可能状态。
