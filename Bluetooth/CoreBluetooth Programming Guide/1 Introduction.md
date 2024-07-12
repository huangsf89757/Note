# About Core Bluetooth 



The Core Bluetooth framework provides the classes needed for your iOS and Mac apps to communicate with devices that are equipped with Bluetooth low energy wireless technology. For example, your app can discover, explore, and interact with low energy peripheral devices, such as heart rate monitors and digital thermostats. As of macOS 10.9 and iOS 6, Mac and iOS devices can also function as Bluetooth low energy peripherals, serving data to other devices, including other Mac and iOS devices.
Core Bluetooth框架提供了iOS和Mac应用程序与配备低功耗蓝牙无线技术的设备进行通信所需的类。例如，您的应用可以发现、探索低能耗外围设备并与之交互，例如心率监测器和数字恒温器。从macOS 10.9和iOS 6开始，Mac和iOS设备还可以用作蓝牙低功耗外设，为其他设备（包括其他Mac和iOS设备）提供数据。

![../Art/CBTechnologyFramework_2x.png](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/CBTechnologyFramework_2x.png)



## At a Glance 一眼

Bluetooth low energy wireless technology is based on the Bluetooth 4.0 specification, which, among other things, defines a set of protocols for communicating between low energy devices. The Core Bluetooth framework is an abstraction of the Bluetooth low energy protocol stack. That said, it hides many of the low-level details of the specification from you, the developer, making it much easier for you to develop apps that interact with Bluetooth low energy devices.
蓝牙低功耗无线技术基于蓝牙4.0规范，该规范定义了一组用于低功耗设备之间通信的协议。核心蓝牙框架是蓝牙低功耗协议栈的抽象。也就是说，它向开发人员隐藏了规范的许多低级细节，使您更容易开发与蓝牙低功耗设备交互的应用程序。



### Centrals and Peripherals Are the Key Players in Core Bluetooth 核心设备和外围设备是核心蓝牙的关键参与者

In Bluetooth low energy communication, there are two key players: the central and the peripheral. Each player has a different role. A peripheral typically has data that is needed by other devices. A central typically uses the information served up by a peripheral to accomplish some task. For example, a digital thermostat equipped with Bluetooth low energy technology might provide the temperature of a room to an iOS app that then displays the temperature in a user-friendly way.
在蓝牙低功耗通信中，有两个关键角色：中央和外围设备。每个玩家都有不同的角色。外围设备通常具有其他设备所需的数据。中心设备通常使用外围设备提供的信息来完成某些任务。例如，配备蓝牙低功耗技术的数字恒温器可能会向iOS应用程序提供房间的温度，然后以用户友好的方式显示温度。

Each player performs a different set of tasks when carrying out its role. Peripherals make their presence known by advertising the data they have over the air. Centrals scan for nearby peripherals that might have data they’re interested in. When a central discovers such a peripheral, the central requests to connect to the peripheral and begins exploring and interacting with the peripheral’s data. The peripheral is responsible for responding to the central in appropriate ways.
每个玩家在执行其角色时执行不同的任务。外围设备通过广播他们所拥有的数据来让人们知道他们的存在。中心设备扫描附近可能有他们感兴趣的数据的外围设备。当中心设备发现这样的外围设备时，中心设备请求连接到外围设备，并开始探索外围设备的数据并与之交互。外围设备负责以适当的方式响应中央设备。



**Relevant Chapters:** [Core Bluetooth Overview](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothOverview/CoreBluetoothOverview.html#//apple_ref/doc/uid/TP40013257-CH2-SW1)
相关章节：核心蓝牙概述





### Core Bluetooth Simplifies Common Bluetooth Tasks 核心蓝牙简化常见蓝牙任务

The Core Bluetooth framework abstracts away the low-level details from the Bluetooth 4.0 specification. As a result, many of the common Bluetooth low energy tasks you need to implement in your app are simplified. If you are developing an app that implements the central role, Core Bluetooth makes it easy to discover and connect with a peripheral, and to explore and interact with the peripheral’s data. In addition, Core Bluetooth makes it easy to set up your local device to implement the peripheral role.
核心蓝牙框架从蓝牙4.0规范中抽象出了低级细节。因此，您需要在应用中执行的许多常见蓝牙低功耗任务都得到了简化。如果您正在开发一款实现核心角色的应用，Core Bluetooth可让您轻松发现外设并与之连接，以及探索外设数据并与之交互。此外，Core Bluetooth还可以轻松设置您的本地设备以实现外设角色。



**Relevant Chapters:** [Performing Common Central Role Tasks](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW1), [Performing Common Peripheral Role Tasks](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW1)
相关章节：执行常见中心角色任务、执行常见外围角色任务





### iOS App States Affect Bluetooth Behavior iOS应用程序状态影响蓝牙行为

When your iOS app is in the background or in a suspended state, its Bluetooth-related capabilities are affected. By default, your app is unable to perform Bluetooth low energy tasks while it is in the background or in a suspended state. That said, if your app needs to perform Bluetooth low energy tasks while in the background, you can declare it to support one or both of the Core Bluetooth background execution modes (there’s one for the central role, and one for the peripheral role). Even when you declare one or both of these background execution modes, certain Bluetooth tasks operate differently while your app is in the background. You want to take these differences into account when designing your app.
当您的iOS应用处于后台或挂起状态时，其蓝牙相关功能会受到影响。默认情况下，您的应用在后台或处于挂起状态时无法执行低功耗蓝牙任务。也就是说，如果您的应用需要在后台执行蓝牙低功耗任务，您可以声明它支持一种或两种Core蓝牙后台执行模式（一种用于中心角色，一种用于外围角色）。即使您声明了其中一种或两种后台执行模式，某些蓝牙任务在您的应用处于后台时的运行方式也会有所不同。在设计应用程序时，您需要考虑这些差异。

Even apps that support background processing may be terminated by the system at any time to free up memory for the current foreground app. As of iOS 7, Core Bluetooth supports saving state information for central and peripheral manager objects and restoring that state at app launch time. You can use this feature to support long-term actions involving Bluetooth devices.
即使是支持后台处理的应用程序也可能随时被系统终止，以便为当前的前台应用程序释放内存。从iOS 7开始，Core Bluetooth支持保存中央和外设管理器对象的状态信息，并在应用程序启动时恢复该状态。您可以使用此功能来支持涉及蓝牙设备的长期操作。



**Relevant Chapters:** [Core Bluetooth Background Processing for iOS Apps](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW1)
相关章节：iOS应用的核心蓝牙后台处理





### Follow Best Practices to Enhance the User Experience 遵循最佳实践以增强用户体验

The Core Bluetooth framework gives your app control over many of the common Bluetooth low energy transactions. Follow best practices to harness this level of control in a responsible way and enhance the user’s experience.
核心蓝牙框架让您的应用可以控制许多常见的蓝牙低功耗事务。遵循最佳实践，以负责任的方式利用这一级别的控制，并增强用户体验。

For example, many of the tasks you perform when implementing the central or the peripheral role use your device’s onboard radio to transmit signals over the air. Because your device’s radio is shared with other forms of wireless communication, and because radio usage has an adverse effect on a device’s battery life, always design your app to minimize how much it uses the radio.
例如，在实现中心或外围角色时执行的许多任务都使用设备的板载无线电通过空中传输信号。由于设备的无线电与其他形式的无线通信共享，并且无线电的使用会对设备的电池寿命产生不利影响，因此在设计应用时应尽量减少无线电的使用量。



**Relevant Chapters:** [Best Practices for Interacting with a Remote Peripheral Device](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW1), [Best Practices for Setting Up Your Local Device as a Peripheral](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral.html#//apple_ref/doc/uid/TP40013257-CH5-SW1)
相关章节：与远程外围设备交互的最佳实践，将本地设备设置为外围设备的最佳实践





## How to Use This Document 如何使用本文档

If you have never used the Core Bluetooth framework, or if you are unfamiliar with basic Bluetooth low energy concepts, read this document in its entirety. In [Core Bluetooth Overview](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothOverview/CoreBluetoothOverview.html#//apple_ref/doc/uid/TP40013257-CH2-SW1), you learn the key terms and concepts that you need to know for the remainder of the book.
如果您从未使用过Core Bluetooth框架，或者不熟悉基本的低功耗蓝牙概念，请完整阅读本文档。在核心蓝牙概述中，您将学习本书剩余部分需要了解的关键术语和概念。

After you understand the key concepts, read [Performing Common Central Role Tasks](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW1) to learn how to develop your app to implement the central role on your local device. Similarly, to learn how to develop your app to implement the peripheral role on your local device, read [Performing Common Peripheral Role Tasks](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW1).
了解关键概念后，请阅读执行常见中心角色任务，了解如何开发应用以在本地设备上实现中心角色。同样，要了解如何开发应用以在本地设备上实现外围设备角色，请阅读执行常见外围设备角色任务。

To ensure that your app is performing well and adhering to best practices, read the later chapters: [Core Bluetooth Background Processing for iOS Apps](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/CoreBluetoothBackgroundProcessingForIOSApps/PerformingTasksWhileYourAppIsInTheBackground.html#//apple_ref/doc/uid/TP40013257-CH7-SW1), [Best Practices for Interacting with a Remote Peripheral Device](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW1), and [Best Practices for Setting Up Your Local Device as a Peripheral](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral.html#//apple_ref/doc/uid/TP40013257-CH5-SW1).
要确保您的应用运行良好并遵循最佳实践，请阅读后面的章节：iOS应用的核心蓝牙后台处理、与远程外围设备交互的最佳实践以及将本地设备设置为外围设备的最佳实践。



## See Also 另见

The official [Bluetooth Special Interest Group (SIG) website](http://www.bluetooth.org/) provides the definitive information about Bluetooth low energy wireless technology. There, you can also find the [Bluetooth 4.0 specification](https://www.bluetooth.org/en-us/specification/adopted-specifications).
蓝牙特别兴趣小组（SIG）的官方网站提供了有关蓝牙低功耗无线技术的权威信息。在那里，您还可以找到蓝牙4.0规范。

If you are designing hardware accessories that use Bluetooth low energy technology to communicate with Apple products, including Mac, iPhone, iPad, and iPod touch models, read [Bluetooth Accessory Design Guidelines for Apple Products](https://developer.apple.com/hardwaredrivers/BluetoothDesignGuidelines.pdf). If your Bluetooth accessory (that connects to an iOS device through a Bluetooth low energy link) needs access to notifications that are generated on iOS devices, read *[Apple Notification Center Service (ANCS) Specification](https://developer.apple.com/library/archive/documentation/CoreBluetooth/Reference/AppleNotificationCenterServiceSpecification/Introduction/Introduction.html#//apple_ref/doc/uid/TP40013460)*.
如果您正在设计使用低功耗蓝牙技术与Apple产品（包括Mac、iPhone、iPad和iPod touch机型）通信的硬件配件，请阅读适用于Apple产品的蓝牙配件设计指南。如果您的蓝牙配件（通过蓝牙低功耗链接连接到iOS设备）需要访问iOS设备上生成的通知，请阅读Apple通知中心服务（ANCS）规范。