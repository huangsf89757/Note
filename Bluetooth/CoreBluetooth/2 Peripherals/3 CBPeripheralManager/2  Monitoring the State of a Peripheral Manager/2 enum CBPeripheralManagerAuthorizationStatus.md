Enumeration 列举

# CBPeripheralManagerAuthorizationStatus

Values representing the current authorization state of the peripheral manager.
表示外设管理器当前授权状态的值。

iOS 7.0–13.0`Deprecated` ｜ iPadOS 7.0–13.0`Deprecated` ｜ Mac Catalyst 13.1–13.1`Deprecated` ｜ macOS 10.9–10.15`Deprecated` ｜ tvOS 9.0–13.0`Deprecated` ｜ visionOS 1.0–1.0`Deprecated` ｜ watchOS 2.0–6.0`Deprecated`

```
enum CBPeripheralManagerAuthorizationStatus
```

`Deprecated 荒废的`

Use CBManagerAuthorization instead
请改用 CBManagerAuthorization



## [Topics 主题](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#topics)

### [Constants 常数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#Constants)

#### [`case notDetermined`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus/notdetermined)

An authorization status that indicates the user hasn’t indicated whether this app can share data using Bluetooth while in the background.
一种授权状态，指示用户尚未指示此应用是否可以在后台使用蓝牙共享数据。



#### [`case restricted`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus/restricted)

An authorization status that indicates this app isn’t authorized to share data using Bluetooth while in the background.
一种授权状态，指示此应用无权在后台使用蓝牙共享数据。



#### [`case denied`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus/denied)

An authorization status that indicates the user explicitly denied this app from sharing data using Bluetooth while in the background.
一种授权状态，指示用户在后台明确拒绝此应用使用蓝牙共享数据。



#### [`case authorized`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus/authorized)

An authorization status that indicates the user authorized this app to share data using Bluetooth while in the background.
一种授权状态，指示用户授权此应用在后台使用蓝牙共享数据。



### [Initializers 初始值设定项](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#Initializers)

#### [`init?(rawValue: Int)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus/init(rawvalue:))



### [Default Implementations 默认实现](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#Default-Implementations)

#### Equatable Implementations

等式实现



#### RawRepresentable Implementations

RawRepresentable 实现



## [Relationships 关系](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#relationships)

### [Conforms To 符合](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#conforms-to)

- [`BitwiseCopyable`](https://developer.apple.com/documentation/Swift/BitwiseCopyable)
- [`Equatable`](https://developer.apple.com/documentation/Swift/Equatable)
- [`Hashable`](https://developer.apple.com/documentation/Swift/Hashable)
- [`RawRepresentable`](https://developer.apple.com/documentation/Swift/RawRepresentable)
- [`Sendable`](https://developer.apple.com/documentation/Swift/Sendable)



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#see-also)

### [Monitoring the State of a Peripheral Manager 监视外设管理器的状态](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus#Monitoring-the-State-of-a-Peripheral-Manager)

[`class func authorizationStatus() -> CBPeripheralManagerAuthorizationStatus`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/authorizationstatus())

Returns the app’s authorization status for sharing data while in the background.
返回应用在后台共享数据的授权状态。

Deprecated 荒废的

[`enum CBPeripheralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate)

Values that represent the current state of the peripheral manager.
表示外围管理器的当前状态的值。

Deprecated 荒废的