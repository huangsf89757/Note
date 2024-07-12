Instance Method Instance 方法

# discoverCharacteristics(_:for:) 

Discovers the specified characteristics of a service.
发现服务的指定特征。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func discoverCharacteristics(
    _ characteristicUUIDs: [CBUUID]?,
    for service: CBService
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:)#parameters)

- `characteristicUUIDs`

  An array of [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects that you are interested in. Each [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object represents a UUID that identifies the type of a characteristic you want to discover.

   您感兴趣的对象数 `CBUUID` 组。每个 `CBUUID` 对象都表示一个 UUID，用于标识要发现的特征类型。

- `service`

  The service whose characteristics you want to discover. 要发现其特征的服务。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:)#Discussion)

You can provide an array of [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) objects—representing characteristic UUIDs— in the `characteristicUUIDs` parameter. When you do, the peripheral returns only the characteristics of the service that match the provided UUIDs. If the `characteristicUUIDs` parameter is `nil`, this method returns all characteristics of the service.
您可以在 `characteristicUUIDs` 参数中提供表示特征 UUID 的 `CBUUID` 对象数组。执行此操作时，外围设备仅返回与提供的 UUID 匹配的服务特征。如果 `characteristicUUIDs` 参数为 `nil` ，则此方法返回服务的所有特征。

> Note 注意
>
> If the `characteristicUUIDs` parameter is `nil`, this method returns all of the service’s characteristics. This is much slower than providing an array of characteristic UUIDs to search for.
> 如果 `characteristicUUIDs` 参数为 `nil` ，则此方法返回服务的所有特征。这比提供要搜索的特征 UUID 数组要慢得多。

When the peripheral discovers one or more characteristics of the specified service, it calls the [`peripheral(_:didDiscoverCharacteristicsFor:error:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheraldelegate/peripheral(_:diddiscovercharacteristicsfor:error:)) method of its delegate object. After the peripheral discovers the service’s characteristics, you can access them through the service’s [`characteristics`](https://developer.apple.com/documentation/corebluetooth/cbservice/characteristics) property.
当外围设备发现指定服务的一个或多个特征时，它会调用其委托对象 `peripheral(_:didDiscoverCharacteristicsFor:error:)` 的方法。外围设备发现服务的特征后，可以通过服务的 `characteristics` 属性访问它们。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:)#see-also)

### [Discovering Characteristics and Descriptors 发现特征和描述符](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discovercharacteristics(_:for:)#Discovering-Characteristics-and-Descriptors)

[`func discoverDescriptors(for: CBCharacteristic)`](https://developer.apple.com/documentation/corebluetooth/cbperipheral/discoverdescriptors(for:))

Discovers the descriptors of a characteristic.
发现特征的描述符。
