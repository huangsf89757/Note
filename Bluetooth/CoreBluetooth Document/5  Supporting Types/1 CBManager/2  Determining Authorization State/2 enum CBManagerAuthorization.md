Enumeration 枚举

# CBManagerAuthorization 

The current authorization state of a Core Bluetooth manager.
核心蓝牙管理器的当前授权状态。

iOS 13.0+ ｜ iPadOS 13.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.15+ ｜ tvOS 13.0+ ｜ visionOS 1.0+ ｜ watchOS 6.0+ 

```
enum CBManagerAuthorization
```



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#topics)

### [Authorization States 授权国](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#Authorization-States)

#### [`case allowedAlways`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization/allowedalways)

A state that indicates the user has authorized Bluetooth at any time.
指示用户已随时授权蓝牙的状态。



#### [`case denied`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization/denied)

A state that indicates the user explicitly denied Bluetooth access for this app.
指示用户明确拒绝此应用的蓝牙访问的状态。



#### [`case notDetermined`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization/notdetermined)

A state that indicates the user has yet to authorize Bluetooth for this app.
指示用户尚未为此应用授权蓝牙的状态。



#### [`case restricted`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization/restricted)

A state that indicates this app isn’t authorized to use Bluetooth.
指示此应用未被授权使用蓝牙的状态。



### [Initializers](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#Default-Implementations)

#### Equatable Implementations

Equatable实现



#### RawRepresentable Implementations

原始可代表的实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#see-also)

### [Determining Authorization State 确定授权状态](https://developer.apple.com/documentation/corebluetooth/cbmanagerauthorization#Determining-Authorization-State)

[`class var authorization: CBManagerAuthorization`](https://developer.apple.com/documentation/corebluetooth/cbmanager/authorization-swift.type.property)

The current authorization status for using Bluetooth.
使用蓝牙的当前授权状态。
