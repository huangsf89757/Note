Structure 结构

# CBCentralManager.Feature

An option set of device-specific features.
一组特定于设备的功能。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.0+macOS 10.10+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 4.0+

```
struct Feature
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#topics)

### [Creating a Central Manager Feature Instance 创建中央管理器功能实例](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#Creating-a-Central-Manager-Feature-Instance)

#### [`init(rawValue: UInt)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature/init(rawvalue:))

Creates a central manager feature instance.
创建中央管理器功能实例。



### [Extended Scan Features 扩展扫描功能](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#Extended-Scan-Features)

#### [`static var extendedScanAndConnect: CBCentralManager.Feature`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature/extendedscanandconnect)

The hardware supports extended scans and enhanced connection creation.
硬件支持扩展扫描和增强的连接创建。



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#Default-Implementations)

#### Equatable Implementations

等式实现

#### OptionSet Implementations

OptionSet 实现

#### SetAlgebra Implementations

SetAlgebra 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`ExpressibleByArrayLiteral`](https://developer.apple.com/documentation/Swift/ExpressibleByArrayLiteral)
- [`OptionSet`](https://developer.apple.com/documentation/Swift/OptionSet)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)
- [`SetAlgebra`](https://developer.apple.com/documentation/Swift/SetAlgebra)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#see-also)

### [Inspecting Feature Support 检查功能支持](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature#Inspecting-Feature-Support)

[`class func supports(CBCentralManager.Feature) -> Bool`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/supports(_:))

Returns a Boolean that indicates whether the device supports a specific set of features.
返回一个布尔值，该值指示设备是否支持一组特定的功能。
