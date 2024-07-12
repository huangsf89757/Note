Structure 结构

# CBCharacteristicProperties 

Values that represent the possible properties of a characteristic.
表示特性的可能属性的值。

iOS 5.0+iPadOS 5.0+Mac Catalyst 13.0+macOS 10.10+tvOS 9.0+visionOS 1.0+watchOS 4.0+

```
struct CBCharacteristicProperties
```



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#overview)

Since you can combine characteristic properties, a characteristic may have multiple property values set.
由于您可以联合收割机特征属性，因此一个特征可以设置多个属性值。



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#topics)

### [Creating a Characteristic Properties Instance 创建特性属性实例](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#Creating-a-Characteristic-Properties-Instance)

#### [`init(rawValue: UInt)`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/init(rawvalue:))

Creates a characteristic properties instance from the given raw value.
从给定的原始值创建特征属性实例。



### [Characteristic Properties 特征性质](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#Characteristic-Properties)

#### [`static var broadcast: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/broadcast)

A property that indicates the characteristic can broadcast its value using a characteristic configuration descriptor.
指示特性的属性可以使用特性配置描述符广播其值。



#### [`static var read: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/read)

A property that indicates a peripheral can read the characteristic’s value.
指示外围设备可以读取特征值的属性。



#### [`static var writeWithoutResponse: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/writewithoutresponse)

A property that indicates a peripheral can write the characteristic’s value, without a response to indicate that the write succeeded.
一个属性，它指示外围设备可以写入特征值，而没有指示写入成功的响应。



#### [`static var write: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/write)

A property that indicates a peripheral can write the characteristic’s value, with a response to indicate that the write succeeded.
一个属性，指示外围设备可以写入特征值，并有一个响应指示写入成功。



#### [`static var notify: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/notify)

A property that indicates the peripheral permits notifications of the characteristic’s value, without a response from the central to indicate receipt of the notification.
指示外围设备允许通知特征值的属性，而无需来自中心设备的响应来指示收到通知。



#### [`static var indicate: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/indicate)

A property that indicates the peripheral permits notifications of the characteristic’s value, with a response from the central to indicate receipt of the notification.
指示外围设备允许通知特征值的属性，并从中心设备发出响应以指示收到通知。



#### [`static var authenticatedSignedWrites: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/authenticatedsignedwrites)

A property that indicates the perhipheral allows signed writes of the characteristic’s value, without a response to indicate the write succeeded.
一个属性，指示外围变量允许对特征值进行签名写入，而没有指示写入成功的响应。



#### [`static var extendedProperties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/extendedproperties)

A property that indicates the characteristic defines additional properties in the extended properties descriptor.
指示特性的属性在扩展属性描述符中定义附加属性。



#### [`static var notifyEncryptionRequired: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/notifyencryptionrequired)

A property that indicates that only trusted devices can enable notifications of the characteristic’s value.
一个属性，指示只有受信任的设备才能启用特征值的通知。



#### [`static var indicateEncryptionRequired: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties/indicateencryptionrequired)

A property that indicates only trusted devices can enable indications of the characteristic’s value.
指示只有受信任的设备才能启用特征值指示的属性。



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### OptionSet Implementations

OptionSet实现



#### SetAlgebra Implementations

集合代数实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`ExpressibleByArrayLiteral`](https://developer.apple.com/documentation/Swift/ExpressibleByArrayLiteral)
- [`OptionSet`](https://developer.apple.com/documentation/Swift/OptionSet)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)
- [`SetAlgebra`](https://developer.apple.com/documentation/Swift/SetAlgebra)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#see-also)

### [Accessing Characteristic Data 特征数据](https://developer.apple.com/documentation/corebluetooth/cbcharacteristicproperties#Accessing-Characteristic-Data)

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/value)

The value of the characteristic.
特性的值。

[`var descriptors: [CBDescriptor\]?`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/descriptors)

A list of the descriptors discovered in this characteristic.
在此特征中发现的描述符的列表。

[`var properties: CBCharacteristicProperties`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/properties)

The properties of the characteristic.
特性的属性。

[`var isNotifying: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isnotifying)

A Boolean value that indicates whether the characteristic is currently notifying a subscribed central of its value.
一个布尔值，指示特征当前是否正在向订阅中心通知其值。

[`var isBroadcasted: Bool`](https://developer.apple.com/documentation/corebluetooth/cbcharacteristic/isbroadcasted)

A Boolean value that indicates whether the characteristic the service broadcasts this characteristic.
一个布尔值，指示服务是否广播此特征.