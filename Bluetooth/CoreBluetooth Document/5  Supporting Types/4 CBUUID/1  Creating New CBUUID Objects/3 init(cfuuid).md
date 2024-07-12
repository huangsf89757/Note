Initializer

# init(cfuuid:) 

Creates a Core Bluetooth UUID object from a Core Foundation UUID object.
从Core Foundation UUID对象创建Core Bluetooth UUID对象。

iOS 5.0–9.0`Deprecated` | iPadOS 5.0–9.0`Deprecated` | Mac Catalyst 13.1–13.1`Deprecated` | macOS 10.7–10.13`Deprecated` | tvOS 9.0–9.0`Deprecated` | visionOS 1.0–1.0`Deprecated` | watchOS 2.0–2.0`Deprecated`

```
init(cfuuid theUUID: CFUUID)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry#parameters)

- `theUUID`

  A UUID represented by a [`CFUUID`](https://developer.apple.com/documentation/corefoundation/cfuuid) object. 

  由 `CFUUID` 对象表示的UUID。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry#return-value)

A new [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object for the specified UUID.
指定UUID的新 `CBUUID` 对象。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry#see-also)

### [Creating New CBUUID Objects 创建新的CBUUID对象](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry#Creating-New-CBUUID-Objects)

[`init(string: String)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID string.
从16位、32位或128位UUID字符串创建Core Bluetooth UUID对象。

[`init(data: Data)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID data container.
从16位、32位或128位UUID数据容器创建Core Bluetooth UUID对象。

[`init(nsuuid: UUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob)

Creates a Core Bluetooth UUID object from a Foundation UUID object.
从Foundation UUID对象创建Core Bluetooth UUID对象。
