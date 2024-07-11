Instance Method Instance 方法

# scanForPeripherals(withServices:options:) scanForPeripherals（withServices：options：）

Scans for peripherals that are advertising services.
扫描作为广告服务的外围设备。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func scanForPeripherals(
    withServices serviceUUIDs: [CBUUID]?,
    options: [String : Any]? = nil
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:)#parameters)

- `serviceUUIDs`

  An array of [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects that the app is interested in. Each [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object represents the UUID of a service that a peripheral advertises. 应用感兴趣的对象数 `CBUUID` 组。每个 `CBUUID` 对象表示外围设备通告的服务的 UUID。

- `options`

  A dictionary of options for customizing the scan. For available options, see [Peripheral Scanning Options](https://developer.apple.com/documentation/corebluetooth/peripheral-scanning-options). 用于自定义扫描的选项字典。有关可用选项，请参阅外围设备扫描选项。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:)#Discussion)

You can provide an array of [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects — representing service UUIDs — in the `serviceUUIDs` parameter. When you do, the central manager returns only peripherals that advertise the services you specify. If the `serviceUUIDs` parameter is `nil`, this method returns all discovered peripherals, regardless of their supported services.
您可以在 `serviceUUIDs` 参数中提供对象数组 `CBUUID` （表示服务 UUID）。执行此操作时，中央管理器仅返回通告您指定服务的外围设备。如果 `serviceUUIDs` 参数为 `nil` ，则此方法返回所有发现的外围设备，而不考虑其支持的服务。

> Note 注意
>
> The recommended practice is to populate the `serviceUUIDs` parameter rather than leaving it `nil`.
> 推荐的做法是填充 `serviceUUIDs` 参数而不是保留它 `nil` 。

If the central manager is actively scanning with one set of parameters and it receives another set to scan, the new parameters override the previous set. When the central manager discovers a peripheral, it calls the [`centralManager(_:didDiscover:advertisementData:rssi:)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:diddiscover:advertisementdata:rssi:)) method of its delegate object.
如果中央管理器正在使用一组参数进行主动扫描，并且它收到另一组要扫描的参数，则新参数将覆盖前一组参数。当中央管理器发现外围设备时，它会调用其委托对象 `centralManager(_:didDiscover:advertisementData:rssi:)` 的方法。

Your app can scan for Bluetooth devices in the background by specifying the `bluetooth-central` background mode. To do this, your app must explicitly scan for one or more services by specifying them in the `serviceUUIDs` parameter. The [`CBCentralManager`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager) scan option has no effect while scanning in the background.
您的应用可以通过指定 `bluetooth-central` 后台模式在后台扫描蓝牙设备。为此，应用必须通过在 `serviceUUIDs` 参数中指定一个或多个服务来显式扫描这些服务。在后台扫描时， `CBCentralManager` 扫描选项不起作用。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:)#see-also)

### [Scanning or Stopping Scans of Peripherals 扫描或停止外围设备的扫描](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/scanforperipherals(withservices:options:)#Scanning-or-Stopping-Scans-of-Peripherals)



Peripheral Scanning Options
外围设备扫描选项

Keys used to pass options when scanning for peripherals.
用于在扫描外围设备时传递选项的键。

[`func stopScan()`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/stopscan())

Asks the central manager to stop scanning for peripherals.
要求中央管理器停止扫描外围设备。

[`var isScanning: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/isscanning)

A Boolean value that indicates whether the central is currently scanning.
一个 Boolean 值，该值指示中心当前是否正在扫描。
