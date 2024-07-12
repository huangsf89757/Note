Initializer

# init(string:) 

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID string.
从16位、32位或128位UUID字符串创建Core Bluetooth UUID对象。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
init(string theString: String)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:)#parameters)

- `theString`

  A string containing a 16-, 32-, or 128-bit UUID. 

  包含16位、32位或128位UUID的字符串。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:)#return-value)

A new [`CBUUID`](https://developer.apple.com/documentation/corebluetooth/cbuuid) object for the specified UUID string.
指定UUID字符串的新 `CBUUID` 对象。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:)#Discussion)

Specify 128-bit UUIDs as a string of hexadecimal digits punctuated by hyphens, for example, 68753A44-4D6F-1226-9C60-0050E4C00067. Specify 16- or 32-bit UUIDs as a string of 4 or 8 hexadecimal digits, respectively. For an example of how to use this method, see [Services and Characteristics Are Identified by UUIDs](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW8) and [Create Your Own UUIDs for Custom Services and Characteristics](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW9).
将128位UUID指定为由连字符分隔的十六进制数字字符串，例如，68753 A44 - 4D 6 F-1226- 9 C60 - 0050 E4 C 00067。将16位或32位UUID分别指定为4位或8位十六进制数字的字符串。有关如何使用此方法的示例，请参阅服务和特征由UUID标识和为自定义服务和特征创建您自己的UUID。

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅Core Bluetooth Programming Guide。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:)#see-also)

### [Creating New CBUUID Objects 创建新的CBUUID对象](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(string:)#Creating-New-CBUUID-Objects)

[`init(data: Data)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(data:))

Creates a Core Bluetooth UUID object from a 16-, 32-, or 128-bit UUID data container.
从16位、32位或128位UUID数据容器创建Core Bluetooth UUID对象。

[`init(cfuuid: CFUUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(cfuuid:)-3h0ry)

Creates a Core Bluetooth UUID object from a Core Foundation UUID object.
从Core Foundation UUID对象创建Core Bluetooth UUID对象。

Deprecated 弃用

[`init(nsuuid: UUID)`](https://developer.apple.com/documentation/corebluetooth/cbuuid/init(nsuuid:)-2amob)

Creates a Core Bluetooth UUID object from a Foundation UUID object.
从Foundation UUID对象创建Core Bluetooth UUID对象。
