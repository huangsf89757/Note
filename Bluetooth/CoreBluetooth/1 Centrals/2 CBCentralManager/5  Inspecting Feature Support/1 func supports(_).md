Type Method Type 方法

# supports(_:) 

Returns a Boolean that indicates whether the device supports a specific set of features.
返回一个布尔值，该值指示设备是否支持一组特定的功能。

iOS 13.0+ iOS的 13.0+iPadOS 13.0+Mac Catalyst 13.1+tvOS 13.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 6.0+ watchOS 6.0+ 操作系统

```
class func supports(_ features: CBCentralManager.Feature) -> Bool
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/supports(_:)#parameters)

- `features`

  One or more features that you would like to check for support. 

  您要检查支持的一个或多个功能。

  

## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/supports(_:)#see-also)

### [Inspecting Feature Support 检查功能支持](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/supports(_:)#Inspecting-Feature-Support)

[`struct Feature`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager/feature)

An option set of device-specific features.
一组特定于设备的功能。
