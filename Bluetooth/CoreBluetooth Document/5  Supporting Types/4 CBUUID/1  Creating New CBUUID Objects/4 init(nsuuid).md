Initializer

# init(nsuuid:)

Creates a Core Bluetooth UUID object from a Foundation UUID object.
从Foundation UUID对象创建Core Bluetooth UUID对象。

iOS 7.0+ ｜ iPadOS 7.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
init(nsuuid theUUID: UUID)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob#parameters)

- `theUUID`

  A UUID represented by an [`NSUUID`](https://developer.apple.com/documentation/foundation/nsuuid) object. 由 `NSUUID` 对象表示的UUID。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob#return-value)

A new [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object for the specified UUID.
指定UUID的新 `CBUUID` 对象。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob#see-also)

### [Creating New CBUUID Objects 创建新的CBUUID对象](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob#Creating-New-CBUUID-Objects)

[`init(string: String)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID string.
从16位、32位或128位UUID字符串创建Core Bluetooth UUID对象。

[`init(data: Data)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID data container.
从16位、32位或128位UUID数据容器创建Core Bluetooth UUID对象。

[`init(cfuuid: CFUUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry)

Creates a Core Bluetooth UUID object from a Core Foundation UUID object.
从Core Foundation UUID对象创建Core Bluetooth UUID对象。

Deprecated 弃用
