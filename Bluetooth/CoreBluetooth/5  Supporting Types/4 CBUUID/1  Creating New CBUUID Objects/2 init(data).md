Initializer

# init(data:) 

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID data container.
从16位、32位或128位UUID数据容器创建Core Bluetooth UUID对象。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
init(data theData: Data)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:)#parameters)

- `theData`

  Data containing a 16-, 32-, or 128-bit UUID. 

  包含16、32或128位UUID的数据。

  

## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:)#return-value)

A new [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object for the specified UUID data.
指定UUID数据的新 `CBUUID` 对象。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:)#Discussion)

This method is useful when handling the UUID of a Bluetooth attribute in raw bytes.
当以原始字节的形式处理蓝牙属性的UUID时，此方法非常有用。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:)#see-also)

### [Creating New CBUUID Objects 创建新的CBUUID对象](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:)#Creating-New-CBUUID-Objects)

[`init(string: String)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID string.
从16位、32位或128位UUID字符串创建Core Bluetooth UUID对象。

[`init(cfuuid: CFUUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry)

Creates a Core Bluetooth UUID object from a Core Foundation UUID object.
从Core Foundation UUID对象创建Core Bluetooth UUID对象。

Deprecated 弃用

[`init(nsuuid: UUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob)

Creates a Core Bluetooth UUID object from a Foundation UUID object.
从Foundation UUID对象创建Core Bluetooth UUID对象。
