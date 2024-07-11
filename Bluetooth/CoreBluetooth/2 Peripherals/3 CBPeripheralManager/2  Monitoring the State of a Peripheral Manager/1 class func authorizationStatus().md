Type Method Type 方法

# authorizationStatus() 

Returns the app’s authorization status for sharing data while in the background.
返回应用在后台共享数据的授权状态。

iOS 7.0–13.0Deprecated 荒废的iPadOS 7.0–13.0Deprecated 荒废的Mac Catalyst 13.1–13.1Deprecated 荒废的macOS 10.9–10.15Deprecated 荒废的tvOS 9.0–13.0 Apple tvOS 9.0–13.0Deprecated 荒废的visionOS 1.0–1.0Deprecated 荒废的watchOS 2.0–6.0Deprecated 荒废的

```
class func authorizationStatus() -> CBPeripheralManagerAuthorizationStatus
```

`Deprecated 荒废的`

Use CBManagerAuthorization instead
请改用 CBManagerAuthorization



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/authorizationstatus()#return-value)

A value that indicates whether the app has authorization to share data using Bluetooth services while in the background. For a list of possible values, see [`CBPeripheralManagerAuthorizationStatus`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus).
一个值，指示应用是否有权在后台使用蓝牙服务共享数据。有关可能值的列表，请参见 `CBPeripheralManagerAuthorizationStatus` 。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/authorizationstatus()#Discussion)

The system manages the authorization status of a given app, and considers several factors. The user must explicitly authorize apps to share data using Bluetooth services while in the background state. The system automatically displays a request for user authorization when your app first attempts to use Bluetooth services to share data.
系统管理给定应用程序的授权状态，并考虑多个因素。用户必须显式授权应用在后台状态下使用蓝牙服务共享数据。当您的应用首次尝试使用蓝牙服务共享数据时，系统会自动显示用户授权请求。

Calling this method doesn’t prompt the user for access. Instead, you use this method to detect restricted access and hide any affected UI features from the user.
调用此方法不会提示用户进行访问。相反，您可以使用此方法检测受限访问，并对用户隐藏任何受影响的 UI 功能。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/authorizationstatus()#see-also)

### [Monitoring the State of a Peripheral Manager 监视外设管理器的状态](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/authorizationstatus()#Monitoring-the-State-of-a-Peripheral-Manager)

[`enum CBPeripheralManagerAuthorizationStatus`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerauthorizationstatus)

Values representing the current authorization state of the peripheral manager.
表示外设管理器当前授权状态的值。

Deprecated 荒废的

[`enum CBPeripheralManagerState`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerstate)

Values that represent the current state of the peripheral manager.
表示外围管理器的当前状态的值。

Deprecated 荒废的
