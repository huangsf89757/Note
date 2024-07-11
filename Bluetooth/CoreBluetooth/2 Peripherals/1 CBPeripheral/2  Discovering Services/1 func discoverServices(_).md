Instance Method Instance 方法

# discoverServices(_:) 

Discovers the specified services of the peripheral.
发现外围设备的指定服务。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
func discoverServices(_ serviceUUIDs: [CBUUID]?)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)#parameters)

- `serviceUUIDs`

  An array of [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects that you are interested in. Each [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object represents a UUID that identifies the type of service you want to discover. 

  您感兴趣的对象数 `CBUUID` 组。每个 `CBUUID` 对象都表示一个 UUID，用于标识要发现的服务类型。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)#Discussion)

You can provide an array of [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects—representing service UUIDs—in the `serviceUUIDs` parameter. When you do, the peripheral returns only the services of the peripheral that match the provided UUIDs.
您可以在 `serviceUUIDs` 参数中提供表示服务 UUID 的 `CBUUID` 对象数组。执行此操作时，外设仅返回与提供的 UUID 匹配的外围设备服务。

> Note 注意
>
> If the `servicesUUIDs` parameter is `nil`, this method returns all of the peripheral’s available services. This is much slower than providing an array of service UUIDs to search for.
> 如果 `servicesUUIDs` 参数为 `nil` ，则此方法返回外围设备的所有可用服务。这比提供要搜索的服务 UUID 阵列要慢得多。

When the peripheral discovers one or more services, it calls the [`peripheral(_:didDiscoverServices:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscoverservices:)): method of its delegate object. After a peripheral discovers services, you can access them through the peripheral’s [`services`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services) property.
当外围设备发现一个或多个服务时，它会调用其委托对象的 `peripheral(_:didDiscoverServices:)` ： 方法。外围设备发现服务后，您可以通过外围设备 `services` 的属性访问它们。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)#see-also)

### [Discovering Services 发现服务](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverservices(_:)#Discovering-Services)

[`func discoverIncludedServices([CBUUID\]?, for: CBService)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverincludedservices(_:for:))

Discovers the specified included services of a previously-discovered service.
发现以前发现的服务的指定包含的服务。

[`var services: [CBService\]?`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/services)

A list of a peripheral’s discovered services.
外围设备发现的服务的列表。
