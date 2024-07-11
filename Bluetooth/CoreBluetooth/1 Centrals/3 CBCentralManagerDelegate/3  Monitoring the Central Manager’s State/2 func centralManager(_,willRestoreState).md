Instance Method Instance 方法

# centralManager(_:willRestoreState:) 

Tells the delegate the system is about to restore the central manager, as part of relaunching the app into the background.
告知委托系统即将还原中央管理器，作为将应用程序重新启动到后台的一部分。

iOS 5.0+ iOS的5.0+iPadOS 5.0+Mac Catalyst 13.1+macOS 10.7+tvOS 9.0+visionOS 1.0+ 视觉操作系统 1.0+watchOS 2.0+

```
optional func centralManager(
    _ central: CBCentralManager,
    willRestoreState dict: [String : Any]
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:willrestorestate:)#parameters)

- `central`

  The central manager that provides this information. 提供此信息的中央管理器。

- `dict`

  A dictionary that contains information about the central manager preserved by the system when it terminated the app. For the available keys to this dictionary, see [Central Manager State Restoration Options](https://developer.apple.com/documentation/corebluetooth/central-manager-state-restoration-options). 一个字典，其中包含有关系统在终止应用时保留的中央管理器的信息。有关此字典的可用键，请参阅Central Manager 状态还原选项。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:willrestorestate:)#Discussion)

This method only applies to apps that opt in to the state preservation and restoration feature of Core Bluetooth. The system invokes this method when relaunching your app into the background to complete some Bluetooth-related task. Use this method to synchronize the state of your app with the state of the Bluetooth system.
此方法仅适用于选择加入 Core Bluetooth 状态保留和恢复功能的应用。在后台重新启动应用以完成某些与蓝牙相关的任务时，系统会调用此方法。使用此方法将应用的状态与蓝牙系统的状态同步。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:willrestorestate:)#see-also)

### [Monitoring the Central Manager’s State 监视中央管理器的状态](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanager(_:willrestorestate:)#Monitoring-the-Central-Managers-State)

[`func centralManagerDidUpdateState(CBCentralManager)`](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate/centralmanagerdidupdatestate(_:))

Tells the delegate the central manager’s state updated.
告知委托中央经理的状态已更新。

**Required 必填**
