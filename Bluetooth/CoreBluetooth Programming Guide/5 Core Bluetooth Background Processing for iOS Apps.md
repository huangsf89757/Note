# Core Bluetooth Background Processing for iOS Apps 适用于iOS应用的核心蓝牙后台处理

For iOS apps, it is crucial to know whether your app is running in the foreground or the background. An app must behave differently in the background than in the foreground, because system resources are more limited on iOS devices. For an overall discussion of background operation on iOS, see [Background Execution](https://developer.apple.com/library/archive/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/BackgroundExecution/BackgroundExecution.html#//apple_ref/doc/uid/TP40007072-CH4) in *[App Programming Guide for iOS](https://developer.apple.com/library/archive/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007072)*.
对于iOS应用程序，了解您的应用程序是在前台还是后台运行至关重要。应用程序在后台的行为必须与在前台的行为不同，因为iOS设备上的系统资源更加有限。有关iOS上后台操作的全面讨论，请参阅iOS应用程序编程指南中的后台执行。

By default, many of the common Core Bluetooth tasks—on both the central and peripheral side—are disabled while your app is in the background or in a suspended state. That said, you can declare your app to support the Core Bluetooth background execution modes to allow your app to be woken up from a suspended state to process certain Bluetooth-related events. Even if your app doesn’t need the full range of background processing support, it can still ask to be alerted by the system when important events occur.
默认情况下，当您的应用处于后台或挂起状态时，中央设备和外围设备端的许多常见Core蓝牙任务都会被禁用。也就是说，您可以声明您的应用支持Core蓝牙后台执行模式，以允许您的应用从挂起状态唤醒，从而处理某些蓝牙相关事件。即使您的应用不需要全方位的后台处理支持，它仍然可以在发生重要事件时请求系统发出警报。

Even if your app supports one or both of the Core Bluetooth background execution modes, it can’t run forever. At some point, the system may need to terminate your app to free up memory for the current foreground app—causing any active or pending connections to be lost, for instance. As of iOS 7, Core Bluetooth supports saving state information for central and peripheral manager objects and restoring that state at app launch time. You can use this feature to support long-term actions involving Bluetooth devices.
即使您的应用支持一种或两种Core蓝牙后台执行模式，它也不能永远运行。在某些情况下，系统可能需要终止您的应用程序以释放当前前台应用程序的内存，例如，导致任何活动或挂起的连接丢失。从iOS 7开始，Core Bluetooth支持保存中央和外设管理器对象的状态信息，并在应用启动时恢复该状态。您可以使用此功能来支持涉及蓝牙设备的长期操作。



## Foreground-Only Apps 仅前台应用程序

As with most iOS apps, unless you request permission to perform specific background tasks, your app transitions to the suspended state shortly after entering the background state. While in the suspended state, your app is unable to perform Bluetooth-related tasks, nor is it aware of any Bluetooth-related events until it resumes to the foreground.
与大多数iOS应用一样，除非您请求执行特定后台任务的权限，否则您的应用在进入后台状态后会立即转换为挂起状态。处于挂起状态时，您的应用无法执行与蓝牙相关的任务，也无法感知任何与蓝牙相关的事件，直到恢复到前台。

On the central side, foreground-only apps—apps that have not declared to support either of the Core Bluetooth background execution modes—cannot scan for and discover advertising peripherals while in the background or while suspended. On the peripheral side, advertising is disabled, and any central trying to access a dynamic characteristic value of one of the app’s published services receives an error.
在中央端，仅前台应用程序（未声明支持任何一种Core蓝牙后台执行模式的应用程序）无法在后台或挂起时扫描和发现广告外设。在外围设备方面，广告被禁用，任何试图访问应用程序发布的服务之一的动态特征值的中心都会收到错误。

Depending on the use case, this default behavior can affect your app in several ways. As an example, imagine that you are interacting with the data on a peripheral that you’re currently connected to. Now imagine that your app moves to the suspended state (because, for example, the user switches to another app). If the connection to the peripheral is lost while your app is suspended, you won’t be aware that any disconnection occurred until your app resumes to the foreground.
根据使用情形，此默认行为可能会以多种方式影响您的应用。例如，假设您正在与当前连接的外围设备上的数据进行交互。现在假设您的应用移动到挂起状态（例如，因为用户切换到另一个应用）。如果在应用挂起时与外围设备的连接丢失，则在应用恢复到前台之前，您不会意识到发生了任何断开连接。



### Take Advantage of Peripheral Connection Options 充分利用外设连接选项

All Bluetooth-related events that occur while a foreground-only app is in the suspended state are queued by the system and delivered to the app only when it resumes to the foreground. That said, Core Bluetooth provides a way to alert the user when certain central role events occur. The user can then use these alerts to decide whether a particular event warrants bringing the app back to the foreground.
仅前台应用处于挂起状态时发生的所有蓝牙相关事件都由系统排队，仅当应用恢复到前台时才交付给应用。也就是说，核心蓝牙提供了一种在发生某些中心角色事件时提醒用户的方法。然后，用户可以使用这些警报来决定特定事件是否需要将应用程序带回前台。

You can take advantage of these alerts by including one of the following peripheral connection options when calling the `connectPeripheral:options:` method of the `CBCentralManager` class to connect to a remote peripheral:
通过在调用 `CBCentralManager` 类的 `connectPeripheral:options:` 方法连接到远程外围设备时包含以下外围设备连接选项之一来利用这些警报：

- `CBConnectPeripheralOptionNotifyOnConnectionKey`—Include this key if you want the system to display an alert for a given peripheral if the app is suspended when a successful connection is made.
  `CBConnectPeripheralOptionNotifyOnConnectionKey` -如果您希望系统在成功连接时应用程序挂起时显示给定外设的警报，请包含此键。
- `CBConnectPeripheralOptionNotifyOnDisconnectionKey`—Include this key if you want the system to display a disconnection alert for a given peripheral if the app is suspended at the time of the disconnection.
  `CBConnectPeripheralOptionNotifyOnDisconnectionKey` -如果您希望系统在应用程序在断开连接时挂起时显示给定外设的断开连接警报，请包含此键。
- `CBConnectPeripheralOptionNotifyOnNotificationKey`—Include this key if you want the system to display an alert for all notifications received from a given peripheral if the app is suspended at the time.
  `CBConnectPeripheralOptionNotifyOnNotificationKey` -如果您希望系统在应用程序暂停时为从给定外围设备接收的所有通知显示警报，请包含此键。

For more information about the peripheral connection options, see the `Peripheral Connection Options` constants, detailed in *[CBCentralManager Class Reference](https://developer.apple.com/documentation/corebluetooth/cbcentralmanager)*.
有关外围设备连接选项的更多信息，请参见CBCentralManager类参考中详细介绍的 `Peripheral Connection Options` 常量。



## Core Bluetooth Background Execution Modes 核心蓝牙后台执行模式

If your app needs to run in background to perform certain Bluetooth-related tasks, it must declare that it supports a Core Bluetooth background execution mode in its Information property list (`Info.plist`) file. When your app declares this, the system wakes it up from a suspended state to allow it to handle Bluetooth-related events. This support is important for apps that interact with Bluetooth low energy devices that deliver data at regular intervals, such as a heart rate monitor.
如果您的应用需要在后台运行以执行某些蓝牙相关任务，则必须在其信息属性列表（ `Info.plist` ）文件中声明它支持Core蓝牙后台执行模式。当您的应用声明此选项时，系统会将其从挂起状态唤醒，以允许其处理蓝牙相关事件。此支持对于与定期传输数据的蓝牙低功耗设备（如心率监测器）交互的应用非常重要。

There are two Core Bluetooth background execution modes that an app may declare—one for apps implementing the central role, and another for apps implementing the peripheral role. If your app implements both roles, it may declare that it supports both background execution modes. The Core Bluetooth background execution modes are declared by adding the `UIBackgroundModes` key to your `Info.plist` file and setting the key’s value to an array containing one of the following strings:
有两种Core蓝牙后台执行模式可供应用使用-一种用于实现中心角色的应用，另一种用于实现外围角色的应用。如果您的应用同时实现这两种角色，则可以声明它支持这两种后台执行模式。Core Bluetooth后台执行模式通过将 `UIBackgroundModes` 键添加到 `Info.plist` 文件并将键的值设置为包含以下字符串之一的数组来声明：

- `bluetooth-central`—The app communicates with Bluetooth low energy peripherals using the Core Bluetooth framework.
  `bluetooth-central` -应用程序使用Core Bluetooth框架与蓝牙低功耗外设通信。
- `bluetooth-peripheral`—The app shares data using the Core Bluetooth framework.
  `bluetooth-peripheral` -应用程序使用Core Bluetooth框架共享数据。



**Note:** The property list editor in Xcode by default displays human-readable strings for many keys instead of the actual key name. To display the actual key names as they appear in the `Info.plist` file, Control-click any of the keys in the editor window and enable the Show Raw Keys/Values item in the contextual window.
注意：Xcode中的属性列表编辑器默认为许多键显示人类可读的字符串，而不是实际的键名。要显示实际的键名称，就像它们出现在 `Info.plist` 文件中一样，按住Control键点按编辑器窗口中的任何键，并启用上下文窗口中的Show Raw Keys/Values项。



For information about how to configure the contents of your `Info.plist` file, see [Xcode Help](https://help.apple.com/xcode).
有关如何配置 `Info.plist` 文件内容的信息，请参阅Xcode帮助。



### The bluetooth-central Background Execution Mode 蓝牙中心后台执行模式

When an app that implements the central role includes the `UIBackgroundModes` key with the `bluetooth-central` value in its `Info.plist` file, the Core Bluetooth framework allows your app to run in the background to perform certain Bluetooth-related tasks. While your app is in the background you can still discover and connect to peripherals, and explore and interact with peripheral data. In addition, the system wakes up your app when any of the `CBCentralManagerDelegate` or `CBPeripheralDelegate` delegate methods are invoked, allowing your app to handle important central role events, such as when a connection is established or torn down, when a peripheral sends updated characteristic values, and when a central manager’s state changes.
当实现中心角色的应用在其 `Info.plist` 文件中包含带有 `bluetooth-central` 值的 `UIBackgroundModes` 键时，Core Bluetooth框架允许您的应用在后台运行以执行某些蓝牙相关任务。当您的应用处于后台时，您仍然可以发现并连接到外围设备，探索外围设备数据并与之交互。此外，当调用任何 `CBCentralManagerDelegate` 或 `CBPeripheralDelegate` 委托方法时，系统会唤醒您的应用，从而允许您的应用处理重要的中心角色事件，例如建立或断开连接时、外设发送更新的特征值时以及中心管理器的状态更改时。

Although you can perform many Bluetooth-related tasks while your app is in the background, keep in mind that scanning for peripherals while your app is in the background operates differently than when your app is in the foreground. In particular, when your app is scanning for device while in the background:
虽然您可以在应用处于后台时执行许多与蓝牙相关的任务，但请记住，在应用处于后台时扫描外围设备的操作方式与应用处于前台时不同。特别是，当您的应用在后台扫描设备时：

- The `CBCentralManagerScanOptionAllowDuplicatesKey` scan option key is ignored, and multiple discoveries of an advertising peripheral are coalesced into a single discovery event.
  `CBCentralManagerScanOptionAllowDuplicatesKey` 扫描选项键被忽略，并且对通告外围设备的多个发现被合并到单个发现事件中。
- If all apps that are scanning for peripherals are in the background, the interval at which your central device scans for advertising packets increases. As a result, it may take longer to discover an advertising peripheral.
  如果正在扫描外围设备的所有应用都在后台运行，则中央设备扫描广告数据包的间隔会增加。结果，发现广告外围设备可能需要更长的时间。

These changes help minimize radio usage and improve the battery life on your iOS device.
这些更改有助于最大限度地减少无线电使用，并延长iOS设备的电池寿命。



### The bluetooth-peripheral Background Execution Mode 蓝牙外设后台执行模式

To perform certain peripheral role tasks while in the background, you must include the `UIBackgroundModes` key with the `bluetooth-peripheral` value in your app’s `Info.plist` file. When this key-value pair is included in the app’s `Info.plist` file, the system wakes up your app to process read, write, and subscription events.
要在后台执行某些外围角色任务，您必须在应用的 `Info.plist` 文件中包含带有 `bluetooth-peripheral` 值的 `UIBackgroundModes` 键。当此键值对包含在应用的 `Info.plist` 文件中时，系统会唤醒应用以处理读、写和订阅事件。

In addition to allowing your app to be woken up to handle read, write, and subscription requests from connected centrals, the Core Bluetooth framework allows your app to advertise while in the background state. That said, you should be aware that advertising while your app is in the background operates differently than when your app is in the foreground. In particular, when your app is advertising while in the background:
除了允许您的应用被唤醒以处理来自连接的中心的读、写和订阅请求外，Core Bluetooth框架还允许您的应用在后台状态下进行广告。也就是说，你应该知道，当你的应用程序在后台运行时，广告的操作方式与你的应用程序在前台运行时不同。特别是，当您的应用在后台进行广告时：

- The `CBAdvertisementDataLocalNameKey` advertisement key is ignored, and the local name of peripheral is not advertised.
  忽略 `CBAdvertisementDataLocalNameKey` 通告键，不通告外设的本地名称。
- All service UUIDs contained in the value of the `CBAdvertisementDataServiceUUIDsKey` advertisement key are placed in a special “overflow” area; they can be discovered only by an iOS device that is explicitly scanning for them.
  所有包含在 `CBAdvertisementDataServiceUUIDsKey` 广告密钥值中的服务UUID都被放置在一个特殊的“溢出”区域中;它们只能被显式扫描它们的iOS设备发现。
- If all apps that are advertising are in the background, the frequency at which your peripheral device sends advertising packets may decrease.
  如果所有广告应用都在后台运行，外围设备发送广告数据包的频率可能会降低。



## Use Background Execution Modes Wisely 明智地使用后台执行模式

Although declaring your app to support one or both of the Core Bluetooth background execution modes may be necessary to fulfill a particular use case, you should always perform background processing responsibly. Because performing many Bluetooth-related tasks require the active use of an iOS device’s onboard radio—and, in turn, radio usage has an adverse effect on an iOS device’s battery life—try to minimize the amount of work you do in the background. Apps woken up for any Bluetooth-related events should process them and return as quickly as possible so that the app can be suspended again.
虽然声明您的应用支持一种或两种Core蓝牙后台执行模式对于满足特定用例可能是必要的，但您应始终负责任地执行后台处理。由于执行许多与蓝牙相关的任务需要主动使用iOS设备的板载无线电，而无线电的使用反过来会对iOS设备的电池寿命产生不利影响，因此请尽量减少您在后台执行的工作量。因任何蓝牙相关事件而唤醒的应用应尽快处理这些事件并返回，以便应用可以再次暂停。

Any app that declares support for either of the Core Bluetooth background executions modes must follow a few basic guidelines:
任何声明支持任何一种Core蓝牙后台执行模式的应用程序都必须遵循一些基本准则：

- Apps should be session based and provide an interface that allows the user to decide when to start and stop the delivery of Bluetooth-related events.
  应用程序应该是基于会话的，并提供一个界面，允许用户决定何时开始和停止蓝牙相关事件的交付。
- Upon being woken up, an app has around 10 seconds to complete a task. Ideally, it should complete the task as fast as possible and allow itself to be suspended again. Apps that spend too much time executing in the background can be throttled back by the system or killed.
  在被唤醒后，一个应用程序有大约10秒的时间来完成一个任务。理想情况下，它应该尽可能快地完成任务，并允许自己再次挂起。花费太多时间在后台执行的应用程序可能会被系统限制或终止。
- Apps should not use being woken up as an opportunity to perform extraneous tasks that are unrelated to why the app was woken up by the system.
  应用不应利用被唤醒的机会执行与应用被系统唤醒的原因无关的无关任务。

For more-general information about how your app should be behave in the background state, see [Being a Responsible Background App](https://developer.apple.com/library/archive/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/BackgroundExecution/BackgroundExecution.html#//apple_ref/doc/uid/TP40007072-CH4-SW8) in *[App Programming Guide for iOS](https://developer.apple.com/library/archive/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40007072)*.
有关应用在后台状态下应如何行为的更一般信息，请参阅App Programming Guide for iOS中的Being a Responsible Background App。



## Performing Long-Term Actions in the Background 在后台执行长期操作

Some apps may need to use the Core Bluetooth framework to perform long-term actions in the background. As an example, imagine you are developing a home security app for an iOS device that communicates with a door lock (equipped with Bluetooth low energy technology). The app and the lock interact to automatically lock the door when the user leaves home and unlock the door when the user returns—all while the app is in the background. When the user leaves home, the iOS device may eventually become out of range of the lock, causing the connection to the lock to be lost. At this point, the app can simply call the `connectPeripheral:options:` method of the `CBCentralManager` class, and because connection requests do not time out, the iOS device will reconnect when the user returns home.
某些应用可能需要使用Core Bluetooth框架在后台执行长期操作。举个例子，假设您正在为iOS设备开发一个家庭安全应用程序，该应用程序与门锁（配备蓝牙低功耗技术）进行通信。应用程序和锁相互作用，当用户离开家时自动锁门，当用户返回时自动解锁-所有这些都是在应用程序处于后台时完成的。当用户离开家时，iOS设备最终可能会超出锁的范围，导致与锁的连接丢失。此时，应用程序可以简单地调用 `CBCentralManager` 类的 `connectPeripheral:options:` 方法，并且由于连接请求不会超时，因此当用户返回家中时，iOS设备将重新连接。

Now imagine that the user is away from home for a few days. If the app is terminated by the system while the user is away, the app will not be able to reconnect to the lock when the user returns home, and the user may not be able to unlock the door. For apps like these, it is critical to be able to continue using Core Bluetooth to perform long-term actions, such as monitoring active and pending connections.
现在假设用户离家几天。如果应用在用户外出时被系统终止，则应用将无法在用户回家时重新连接到锁，并且用户可能无法解锁门。对于此类应用，能够继续使用Core Bluetooth执行长期操作（例如监控活动和挂起的连接）至关重要。



### State Preservation and Restoration 国家保护和恢复

Because state preservation and restoration is built in to Core Bluetooth, your app can opt in to this feature to ask the system to preserve the state of your app’s central and peripheral managers and to continue performing certain Bluetooth-related tasks on their behalf, even when your app is no longer running. When one of these tasks completes, the system relaunches your app into the background and gives your app the opportunity to restore its state and to handle the event appropriately. In the case of the home security app described above, the system would monitor the connection request, and re-relaunch the app to handle the `centralManager:didConnectPeripheral:` delegate callback when the user returned home and the connection request completed.
由于Core Bluetooth内置了状态保留和恢复功能，因此您的应用可以选择加入此功能，以要求系统保留应用的中央管理器和外围管理器的状态，并代表它们继续执行某些与蓝牙相关的任务，即使您的应用不再运行。当其中一项任务完成时，系统会将您的应用重新启动到后台，并让您的应用有机会恢复其状态并适当处理事件。在上述家庭安全应用的情况下，系统将监视连接请求，并且当用户返回家庭并且连接请求完成时重新启动应用以处理 `centralManager:didConnectPeripheral:` 委托回调。

Core Bluetooth supports state preservation and restoration for apps that implement the central role, peripheral role, or both. When your app implements the central role and adds support for state preservation and restoration, the system saves the state of your central manager object when the system is about to terminate your app to free up memory (if your app has multiple central managers, you can choose which ones you want the system to keep track of). In particular, for a given `CBCentralManager` object, the system keeps track of:
Core Bluetooth支持实现中心角色、外围角色或两者兼有的应用的状态保存和恢复。当您的应用实现中心角色并添加对状态保留和恢复的支持时，系统将在即将终止您的应用以释放内存时保存中心管理器对象的状态（如果您的应用有多个中心管理器，您可以选择希望系统跟踪哪些中心管理器）。特别地，对于给定的 `CBCentralManager` 对象，系统跟踪：

- The services the central manager was scanning for (and any scan options specified when the scan started)
  中央管理器正在扫描的服务（以及扫描开始时指定的任何扫描选项）
- The peripherals the central manager was trying to connect to or had already connected to
  中央管理器正在尝试连接或已经连接的外围设备
- The characteristics the central manager was subscribed to
  中央管理器订阅的特性

Apps that implement the peripheral role can likewise take advantage of state preservation and restoration. For `CBPeripheralManager` objects, the system keeps track of:
实现外围角色的应用程序同样可以利用状态保存和恢复。对于 `CBPeripheralManager` 对象，系统跟踪：

- The data the peripheral manager was advertising
  外围设备管理器通告的数据
- The services and characteristics the peripheral manager published to the device’s database
  外设管理器发布到设备数据库的服务和特性
- The centrals that were subscribed to your characteristics’ values
  那些与你的性格价值观相一致的中心人物

When your app is relaunched into the background by the system (because a peripheral your app was scanning for is discovered, for instance), you can reinstantiate your app’s central and peripheral managers and restore their state. The following section describes in detail how to take advantage of state preservation and restoration in your app.
当您的应用被系统重新启动到后台时（例如，因为发现了应用正在扫描的外围设备），您可以重新启动应用的中央和外围管理器并恢复其状态。以下部分详细介绍如何在应用中利用状态保留和恢复。



### Adding Support for State Preservation and Restoration 支持状态保存和恢复

State preservation and restoration in Core Bluetooth is an opt-in feature and requires help from your app to work. You can add support for this feature in your app by following this process:
Core Bluetooth中的状态保存和恢复是一项可选择加入的功能，需要您的应用提供帮助才能正常工作。您可以按照以下流程在应用中添加对此功能的支持：

1. (Required) Opt in to state preservation and restoration when you allocate and initialize a central or peripheral manager object. This step is described in Opt In to State Preservation and Restoration.
   （必需）在分配和初始化中央或外围管理器对象时选择状态保留和恢复。此步骤在选择加入国家保存和恢复中进行了描述。
2. (Required) Reinstantiate any central or peripheral manager objects after your app is relaunched by the system. This step is described in [Reinstantiate Your Central and Peripheral Managers](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW13).
   系统重新启动应用后，重新实例化任何中央或外围设备管理器对象。重新实例化中央管理器和外围管理器中介绍了此步骤。
3. (Required) Implement the appropriate restoration delegate method. This step is described in [Implement the Appropriate Restoration Delegate Method](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW14).
   实现适当的恢复委托方法。此步骤在实现适当的恢复委托方法中进行了说明。
4. (Optional) Update your central and peripheral managers’ initialization process. This step is described in [Update Your Initialization Process](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW15).
   （可选）更新中央和外围管理器的初始化过程。此步骤在更新您的Oracle Process中进行了说明。



#### Opt In to State Preservation and Restoration 选择国家保护和恢复

To opt in to the state preservation and restoration feature, simply provide a unique restoration identifier when you allocate and initialize a central or peripheral manager. A *restoration identifier* is a string that identifies the central or peripheral manager to Core Bluetooth and to your app. The value of the string is significant only to your code, but the presence of this string tells Core Bluetooth that it needs to preserve the state of the tagged object. Core Bluetooth preserves the state of only those objects that have a restoration identifier.
要选择状态保留和恢复功能，只需在分配和初始化中央或外围管理器时提供唯一的恢复标识符即可。恢复标识符是一个字符串，用于标识Core蓝牙和您的应用程序的中央或外围管理器。该字符串的值仅对您的代码有意义，但该字符串的存在告诉Core蓝牙它需要保留标记对象的状态。核心蓝牙仅保留那些具有恢复标识符的对象的状态。

For example, to opt in to state preservation and restoration in an app that uses only one instance of a `CBCentralManager` object to implement the central role, specify the `CBCentralManagerOptionRestoreIdentifierKey` initialization option and provide a restoration identifier for the central manager when you allocate and initialize it.
例如，要在仅使用 `CBCentralManager` 对象的一个实例来实现中心角色的应用程序中选择状态保留和恢复，请指定 `CBCentralManagerOptionRestoreIdentifierKey` 初始化选项，并在分配和初始化中央管理器时为其提供恢复标识符。

| `    myCentralManager =`                                     |
| ------------------------------------------------------------ |
| `        [[CBCentralManager alloc] initWithDelegate:self queue:nil` |
| `         options:@{ CBCentralManagerOptionRestoreIdentifierKey:` |
| `         @"myCentralManagerIdentifier" }];`                 |

Although the above example does not demonstrate this, you opt in to state preservation and restoration in an app that uses peripheral manager objects in an analogous way: Specify the `CBPeripheralManagerOptionRestoreIdentifierKey` initialization option, and provide a restoration identifier when you allocate and initialize each peripheral manager object.
虽然上面的示例没有演示这一点，但您可以选择在以类似方式使用外设管理器对象的应用中进行状态保留和恢复：指定 `CBPeripheralManagerOptionRestoreIdentifierKey` 初始化选项，并在分配和初始化每个外设管理器对象时提供恢复标识符。



**Note:** Because apps can have multiple instances of `CBCentralManager` and `CBPeripheralManager` objects, be sure each restoration identifier is unique, so that the system can properly distinguish one central (or peripheral) manager object from another.
注意：由于应用可能具有 `CBCentralManager` 和 `CBPeripheralManager` 对象的多个实例，因此请确保每个恢复标识符都是唯一的，以便系统可以正确区分中央（或外围）管理器对象。





#### Reinstantiate Your Central and Peripheral Managers 重新实例化中央管理器和外围管理器

When your app is relaunched into the background by the system, the first thing you need to do is reinstantiate the appropriate central and peripheral managers with the same restoration identifiers as they had when they were first created. If your app uses only one central or peripheral manager, and that manager exists for the lifetime of your app, there is nothing more you need to do for this step.
当您的应用被系统重新启动到后台时，您需要做的第一件事是使用与首次创建时相同的恢复标识符重新初始化相应的中央和外围管理器。如果您的应用仅使用一个中央或外围管理器，并且该管理器在您的应用生命周期内存在，则此步骤无需再执行任何操作。

If your app uses more than one central or peripheral manager or if it uses a manager that isn’t around for the lifetime of your app, your app needs to know which managers to reinstantiate when it is relaunched by the system. You can access a list of all the restoration identifiers for the manager objects the system was preserving for your app when it was terminated, by using the appropriate launch option keys (`UIApplicationLaunchOptionsBluetoothCentralsKey` or `UIApplicationLaunchOptionsBluetoothPeripheralsKey`) when implementing your app delegate’s `application:didFinishLaunchingWithOptions:` method.
如果您的应用使用多个中央或外围管理器，或者如果它使用的管理器在应用的生命周期内不存在，则您的应用需要知道在系统重新启动时要重新启用哪些管理器。在实现应用委托的 `application:didFinishLaunchingWithOptions:` 方法时，您可以使用适当的启动选项键（ `UIApplicationLaunchOptionsBluetoothCentralsKey` 或 `UIApplicationLaunchOptionsBluetoothPeripheralsKey` ）访问系统在应用终止时为应用保留的管理器对象的所有恢复标识符的列表。

For example, when your app is relaunched by system, you can retrieve all the restoration identifiers for the central manager objects the system was preserving for your app, like this:
例如，当您的应用由系统重新启动时，您可以检索系统为您的应用保留的中央管理器对象的所有恢复标识符，如下所示：

| `- (BOOL)application:(UIApplication *)application`           |
| ------------------------------------------------------------ |
| `didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {` |
| ` `                                                          |
| `    NSArray *centralManagerIdentifiers =`                   |
| `        launchOptions[UIApplicationLaunchOptionsBluetoothCentralsKey];` |
| `    ...`                                                    |

After you have the list of restoration identifiers, simply loop through it and reinstantiate the appropriate central manager objects.
获得恢复标识符列表后，只需循环遍历它并重新实例化适当的中央管理器对象。



**Note:** When your app is relaunched, the system provides restoration identifiers only for central and peripheral managers for which it was performing some Bluetooth-related task (while the app was no longer running). These launch option keys are described in more detail in *[UIApplicationDelegate Protocol Reference](https://developer.apple.com/documentation/uikit/uiapplicationdelegate)*.
注意：当您的应用重新启动时，系统仅为正在为其执行某些蓝牙相关任务（应用不再运行时）的中央和外围设备管理器提供恢复标识符。这些启动选项键在UIApplicationDelegate Protocol Reference中有更详细的描述。





#### Implement the Appropriate Restoration Delegate Method 实施适当的恢复委托方法

After you have reinstantiated the appropriate central and peripheral managers in your app, restore them by synchronizing their state with the state of the Bluetooth system. To bring your app up to speed with what the system has been doing on its behalf (while it was not running), you must implement the appropriate restoration delegate method. For central managers, implement the `centralManager:willRestoreState:` delegate method; for peripheral managers, implement the `peripheralManager:willRestoreState:` delegate method.
在应用中恢复相应的中央管理器和外设管理器后，通过将其状态与蓝牙系统的状态同步来恢复它们。要使您的应用跟上系统代表其执行的操作（在应用未运行时），您必须实现适当的恢复委托方法。对于中央管理器，实现 `centralManager:willRestoreState:` delegate方法;对于外围管理器，实现 `peripheralManager:willRestoreState:` delegate方法。



**Important:** For apps that opt in to the state preservation and restoration feature of Core Bluetooth, these are the *first* methods (`centralManager:willRestoreState:` and `peripheralManager:willRestoreState:`) invoked when your app is relaunched into the background to complete some Bluetooth-related task. For apps that don’t opt in to state preservation (or if there is nothing to restore upon launch), the `centralManagerDidUpdateState:` and `peripheralManagerDidUpdateState:` delegate methods are invoked first instead.
重要提示：对于选择加入Core Bluetooth的状态保留和恢复功能的应用程序，这些是当您的应用程序重新启动到后台以完成某些蓝牙相关任务时调用的第一个方法（ `centralManager:willRestoreState:` 和 `peripheralManager:willRestoreState:` ）。对于不选择状态保留的应用（或者如果在启动时没有任何东西要恢复），则会首先调用 `centralManagerDidUpdateState:` 和 `peripheralManagerDidUpdateState:` 委托方法。



In both of the above delegate methods, the last parameter is a dictionary that contains information about the managers that were preserved at the time the app was terminated. For a list of the available dictionary keys, see the `Central Manager State Restoration Options` constants in *[CBCentralManagerDelegate Protocol Reference](https://developer.apple.com/documentation/corebluetooth/cbcentralmanagerdelegate)* and the `Peripheral_Manager_State_Restoration_Options` constants in *[CBPeripheralManagerDelegate Protocol Reference](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerdelegate)*.
在上述两种委托方法中，最后一个参数是一个字典，其中包含有关应用终止时保留的管理器的信息。有关可用字典键的列表，请参见CBCentralManagerDelegate Protocol Reference中的 `Central Manager State Restoration Options` 常量和CBPeripheralManagerDelegate Protocol Reference中的 `Peripheral_Manager_State_Restoration_Options` 常量。

To restore the state of a `CBCentralManager` object, use the keys to the dictionary that is provided in the `centralManager:willRestoreState:` delegate method. As an example, if your central manager object had any active or pending connections at the time your app was terminated, the system continued to monitor them on your app’s behalf. As the following shows, you can use the `CBCentralManagerRestoredStatePeripheralsKey` dictionary key to get of a list of all the peripherals (represented by `CBPeripheral` objects) the central manager was connected to or was trying to connect to:
要恢复 `CBCentralManager` 对象的状态，请使用 `centralManager:willRestoreState:` delegate方法中提供的字典的键。例如，如果您的中央管理器对象在您的应用终止时有任何活动或挂起的连接，系统会代表您的应用继续监控这些连接。如下所示，您可以使用 `CBCentralManagerRestoredStatePeripheralsKey` 字典键获取中央管理器连接到或试图连接到的所有外围设备（由 `CBPeripheral` 对象表示）的列表：

| `- (void)centralManager:(CBCentralManager *)central`         |
| ------------------------------------------------------------ |
| `      willRestoreState:(NSDictionary *)state {`             |
| ` `                                                          |
| `    NSArray *peripherals =`                                 |
| `        state[CBCentralManagerRestoredStatePeripheralsKey];` |
| `    ...`                                                    |

What you do with the list of restored peripherals in the above example depends on the use case. For instance, if your app keeps a list of the peripherals the central manager discovers, you may want to add the restored peripherals to that list to keep references to them. As described in [Connecting to a Peripheral Device After You’ve Discovered It](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW4), be sure to set a peripheral’s delegate to ensure that it receives the appropriate callbacks.
在上面的示例中，您如何处理已恢复的外围设备列表取决于用例。例如，如果您的应用保留了中央管理器发现的外围设备列表，您可能希望将已恢复的外围设备添加到该列表中，以保留对它们的引用。如发现外围设备后连接到外围设备中所述，请确保设置外围设备的委托，以确保它接收适当的回调。

You can restore the state of a `CBPeripheralManager` object in a similar way by using the keys to the dictionary that is provided in the `peripheralManager:willRestoreState:` delegate method.
您可以使用 `peripheralManager:willRestoreState:` delegate方法中提供的字典键以类似的方式恢复 `CBPeripheralManager` 对象的状态。



#### Update Your Initialization Process 更新您的客户服务流程

After you have implemented the previous three required steps, you may want to take a look at updating your central and peripheral managers’ initialization process. Although this is an optional step, it can be important in ensuring that things run smoothly in your app. As an example, your app may have been terminated while it was in the middle of exploring the data of a connected peripheral. When your app is restored with this peripheral, it won’t know how far it made it the discovery process at the time it was terminated. You’ll want to make sure you’re starting from where you left off in the discovery process.
在实现了前面三个必需的步骤之后，您可能想看看如何更新中央管理器和外围管理器的初始化过程。虽然这是一个可选步骤，但它对于确保应用程序中的操作顺利运行非常重要。例如，您的应用程序可能在探索连接的外围设备的数据时被终止。当您的应用使用此外围设备恢复时，它将不知道在终止时将其设置为发现进程的距离。您需要确保从发现过程中停止的地方开始。

For example, when initializing your app in the `centralManagerDidUpdateState:` delegate method, you can find out if you successfully discovered a particular service of a restored peripheral (before your app was terminated), like this:
例如，在 `centralManagerDidUpdateState:` delegate方法中初始化应用时，您可以查看是否成功发现了已恢复外设的特定服务（在应用终止之前），如下所示：

| `    NSUInteger serviceUUIDIndex =`                          |
| ------------------------------------------------------------ |
| `        [peripheral.services indexOfObjectPassingTest:^BOOL(CBService *obj,` |
| `        NSUInteger index, BOOL *stop) {`                    |
| `            return [obj.UUID isEqual:myServiceUUIDString];` |
| `        }];`                                                |
| ` `                                                          |
| `    if (serviceUUIDIndex == NSNotFound) {`                  |
| `        [peripheral discoverServices:@[myServiceUUIDString]];` |
| `        ...`                                                |

As the above example shows, if the system terminated your app before it finished discovering the service, begin the exploring the restored peripheral’s data at that point by calling the `discoverServices:`. If your app discovered the service successfully, you can then check to see whether the appropriate characteristics were discovered (and whether you already subscribed to them). By updating your initialization process in this manner, you’ll ensure that you’re calling the right methods at the right time.
如上例所示，如果系统在完成服务发现之前终止了应用，请在此时通过调用 `discoverServices:` 开始开始探索已恢复的外设数据。如果您的应用成功发现了服务，则可以检查是否发现了相应的特征（以及您是否已经订阅了这些特征）。通过以这种方式更新初始化过程，您将确保在正确的时间调用正确的方法。