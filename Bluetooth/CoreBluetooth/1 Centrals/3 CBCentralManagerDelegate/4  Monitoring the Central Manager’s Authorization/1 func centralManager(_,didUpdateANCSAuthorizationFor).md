Instance Method Instance 方法

# centralManager(_:didUpdateANCSAuthorizationFor:) 

Tells the delegate the authorization status changed for a ANCS-requiring connected peripheral.
告知代理需要 ANCS 的已连接外围设备的授权状态已更改。

iOS 13.0+ ｜ iPadOS 13.0+ ｜ Mac Catalyst 13.1+ ｜ tvOS 13.0+ ｜ visionOS 1.0+ ｜ watchOS 6.0+ 

```
optional func centralManager(
    _ central: CBCentralManager,
    didUpdateANCSAuthorizationFor peripheral: CBPeripheral
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:didupdateancsauthorizationfor:)#parameters)

- `central`

  The central manager providing this information. 

  提供此信息的中央管理器。

- `peripheral`

  The [`CBPeripheral`](https://developer.apple.com/documentation/corebluetooth/cbperipheral) that caused the event. 

  `CBPeripheral` 导致事件的原因。
