Type Property 类型属性

# authorization 

The current authorization status for using Bluetooth.
使用蓝牙的当前授权状态。

iOS 13.1+iPadOS 13.1+Mac Catalyst 13.1+macOS 10.15+tvOS 13.0+visionOS 1.0+watchOS 6.0+

```
class var authorization: CBManagerAuthorization { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmanager/authorization-swift.type.property#Discussion)

Check this property in your implementation of the delegate methods [`centralManagerDidUpdateState(_:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:)) and [`peripheralManagerDidUpdateState(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate/peripheralmanagerdidupdatestate(_:)) to determine whether your app can use Core Bluetooth. You can also use it to check the app’s authorization status before creating a [`CBManager`](https://developer.apple.com/documentation/corebluetooth/cbmanager) instance.
在委托方法 `centralManagerDidUpdateState(_:)` 和 `peripheralManagerDidUpdateState(_:)` 的实现中检查此属性，以确定您的应用是否可以使用Core Bluetooth。您还可以在创建 `CBManager` 实例之前使用它来检查应用的授权状态。

The initial value of this property is [`CBManagerAuthorization.notDetermined`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization/notdetermined).
此属性的初始值为 `CBManagerAuthorization.notDetermined` 。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmanager/authorization-swift.type.property#see-also)

### [Determining Authorization State 确定授权状态](https://developer.apple.com/documentation/corebluetooth/cbmanager/authorization-swift.type.property#Determining-Authorization-State)

[`enum CBManagerAuthorization`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization)

The current authorization state of a Core Bluetooth manager.
核心蓝牙管理器的当前授权状态。
