Instance Property 实例属性

# isPrimary

A Boolean value that indicates whether the type of service is primary or secondary.
一个布尔值，指示服务类型是主服务还是辅助服务。

iOS 5.0+ ｜ iPadOS 5.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.7+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var isPrimary: Bool { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbservice/isprimary#Discussion)

A peripheral’s service is either primary or secondary. A primary service describes the primary function of a device. A secondary service describes a service that’s relevant only in the context of another service that references it. For example, the primary service of a heart rate monitor may be to expose heart rate data from the monitor’s heart rate sensor. In this example, a secondary service may be to expose the sensor’s battery data.
外围设备的服务可以是主要的，也可以是次要的。主要服务描述设备的主要功能。次要服务描述的是仅在引用它的另一个服务的上下文中相关的服务。例如，心率监测器的主要服务可能是从监测器的心率传感器公开心率数据。在该示例中，次要服务可以是暴露传感器的电池数据。

If the value of this property is [`true`](https://developer.apple.com/documentation/swift/true), the type of service is primary. If the value of this property is [`false`](https://developer.apple.com/documentation/swift/false), the type of service is secondary.
如果此属性的值为 `true` ，则服务类型为主服务。如果此属性的值为 `false` ，则服务类型为次要。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbservice/isprimary#see-also)

### [Identifying a Service 识别服务](https://developer.apple.com/documentation/corebluetooth/cbservice/isprimary#Identifying-a-Service)

[`var peripheral: CBPeripheral?`](https://developer.apple.com/documentation/corebluetooth/cbservice/peripheral)

The peripheral to which this service belongs.
此服务所属的外围设备。
