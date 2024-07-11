Instance Method Instance 方法

# peripheral(_:didModifyServices:) 

Tells the delegate that a peripheral’s services changed.
告知代理外围设备的服务已更改。

iOS 7.0+ iOS的7.0 +iPadOS 7.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func peripheral(
    _ peripheral: CBPeripheral,
    didModifyServices invalidatedServices: [CBService]
)
```

**Required 必填**



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didmodifyservices:)#parameters)

- `peripheral`

  The peripheral providing this information. 

  提供此信息的外围设备。

- `invalidatedServices`

  A list of services invalidated by this change. 

  因此更改而失效的服务列表。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didmodifyservices:)#Discussion)

Core Bluetooth invokes this method whenever one or more services of a peripheral change. A peripheral’s services have changed if:
每当外围设备的一个或多个服务发生更改时，核心蓝牙都会调用此方法。在以下情况下，外围设备的服务已更改：

- The peripheral removes a service from its database.
  外围设备从其数据库中删除服务。
- The peripheral adds a new service to its database.
  外围设备将新服务添加到其数据库中。
- The peripheral adds back a previously-removed service, but at a different location in the database.
  外围设备将添加回以前删除的服务，但位于数据库中的不同位置。

The `invalidatedServices` parameter includes any changed services that you previously discovered; you can no longer use these services. You can use the [`discoverServices(_:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)) method to discover any new services that the peripheral added to its database. Use this same method to find out whether any of the invalidated services that you were using (and want to continue using) now have a different location in the peripheral’s database.
该 `invalidatedServices` 参数包括您之前发现的任何更改的服务;您不能再使用这些服务。可以使用该 `discoverServices(_:)` 方法发现外围设备添加到其数据库的任何新服务。使用相同的方法确定您正在使用（并希望继续使用）的任何无效服务现在在外围设备的数据库中是否具有不同的位置。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didmodifyservices:)#see-also)

### [Monitoring Changes to a Peripheral’s Name or Services 监视对外围设备名称或服务的更改](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:didmodifyservices:)#Monitoring-Changes-to-a-Peripherals-Name-or-Services)

[`func peripheralDidUpdateName(CBPeripheral)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheraldidupdatename(_:))

Tells the delegate that a peripheral’s name changed.
告知代理外围设备的名称已更改。

**Required 必填**
