# Core Bluetooth Overview 核心蓝牙概述

The Core Bluetooth framework lets your iOS and Mac apps communicate with Bluetooth low energy devices. For example, your app can discover, explore, and interact with low energy peripheral devices, such as heart rate monitors, digital thermostats, and even other iOS devices.
Core蓝牙框架可让您的iOS和Mac应用程序与低功耗蓝牙设备进行通信。例如，您的应用程序可以发现、探索低功耗外围设备并与之交互，例如心率监测器、数字恒温器甚至其他iOS设备。

The framework is an abstraction of the Bluetooth 4.0 specification for use with low energy devices. That said, it hides many of the low-level details of the specification from you, the developer, making it much easier for you to develop apps that interact with Bluetooth low energy devices. Because the framework is based on the specification, some concepts and terminology from the specification have been adopted. This chapter introduces you to the key terms and concepts that you need to know to begin developing great apps using the Core Bluetooth framework.
该框架是用于低功耗设备的蓝牙4.0规范的抽象。也就是说，它向开发人员隐藏了规范的许多低级细节，使您更容易开发与蓝牙低功耗设备交互的应用程序。由于框架是基于规范的，因此采用了规范中的一些概念和术语。本章将向您介绍开始使用Core Bluetooth框架开发出色应用程序所需了解的关键术语和概念。



**Important:** An iOS app linked on or after iOS 10.0 must include in its `Info.plist` file the usage description keys for the types of data it needs to access or it will crash. To access Bluetooth peripheral data specifically, it must include [NSBluetoothPeripheralUsageDescription](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW20).
重要提示：在iOS 10.0上或之后链接的iOS应用必须在其 `Info.plist` 文件中包含其需要访问的数据类型的使用说明键，否则将崩溃。要访问蓝牙外设数据，必须包含NSB蓝牙外设使用说明。





## Central and Peripheral Devices and Their Roles in Bluetooth Communication 蓝牙通信中的中心设备和外围设备及其作用

There are two major players involved in all Bluetooth low energy communication: the central and the peripheral. Based on a somewhat traditional client-server architecture, a *peripheral* typically has data that is needed by other devices. A *central* typically uses the information served up by peripherals to accomplish some particular task. As Figure 1-1 shows, for example, a heart rate monitor may have useful information that your Mac or iOS app may need in order to display the user’s heart rate in a user-friendly way.
所有蓝牙低功耗通信都涉及两个主要参与者：中央和外围设备。基于有点传统的客户端-服务器架构，外围设备通常具有其他设备所需的数据。中心设备通常使用外围设备提供的信息来完成某些特定的任务。例如，如图1-1所示，心率监测器可能包含Mac或iOS应用程序可能需要的有用信息，以便以用户友好的方式显示用户的心率。

**Figure 1-1** Central and peripheral devices
图1-1中央和外围设备![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/CBDevices1_2x.png)



### Centrals Discover and Connect to Peripherals That Are Advertising 中心发现并连接到正在做广告的外围设备

Peripherals broadcast some of the data they have in the form of advertising packets. An *advertising packet* is a relatively small bundle of data that may contain useful information about what a peripheral has to offer, such as the peripheral’s name and primary functionality. For instance, a digital thermostat may advertise that it provides the current temperature of a room. In Bluetooth low energy, advertising is the primary way that peripherals make their presence known.
外围设备以广告包的形式广播它们所拥有的一些数据。广告数据包是一个相对较小的数据包，其中可能包含有关外围设备必须提供什么的有用信息，例如外围设备的名称和主要功能。例如，数字恒温器可以通告它提供房间的当前温度。在低功耗蓝牙中，广告是外设使其存在已知的主要方式。

A central, on the other hand, can scan and listen for any peripheral device that is advertising information that it’s interested in, as shown in Figure 1-2. A central can ask to connect to any peripheral that it has discovered advertising.
另一方面，一个中心，可以扫描和监听任何外围设备，是广告信息，它感兴趣的，如图1-2所示。中心设备可以请求连接到它发现广告的任何外围设备。

**Figure 1-2** Advertising and discovery
图1-2广告和发现![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/AdvertisingAndDiscovery_2x.png)



### How the Data of a Peripheral Is Structured 外围设备的数据是如何构造的

The purpose of connecting to a peripheral is to begin exploring and interacting with the data it has to offer. Before you can do this, however, it helps to understand how the data of a peripheral is structured.
连接到外围设备的目的是开始探索它必须提供的数据并与之交互。但是，在执行此操作之前，了解外围设备的数据是如何结构化的会有所帮助。

Peripherals may contain one or more services or provide useful information about their connected signal strength. A *service* is a collection of data and associated behaviors for accomplishing a function or feature of a device (or portions of that device). For example, one service of a heart rate monitor may be to expose heart rate data from the monitor’s heart rate sensor.
外围设备可能包含一个或多个服务或提供有关其连接信号强度的有用信息。服务是用于完成设备（或该设备的部分）的功能或特征的数据和相关联的行为的集合。例如，心率监测器的一个服务可以是暴露来自监测器的心率传感器的心率数据。

Services themselves are made up of either characteristics or included services (that is, references to other services). A *characteristic* provides further details about a peripheral’s service. For example, the heart rate service just described may contain one characteristic that describes the intended body location of the device’s heart rate sensor and another characteristic that transmits heart rate measurement data. Figure 1-3 illustrates one possible structure of a heart rate monitor’s service and characteristics.
服务本身由特性或包含的服务（即对其他服务的引用）组成。特性提供有关外围设备服务的进一步详细信息。例如，刚刚描述的心率服务可以包含描述设备的心率传感器的预期身体位置的一个特性和发送心率测量数据的另一特性。图1-3说明了心率监测器的服务和特性的一种可能结构。

**Figure 1-3** A peripheral’s service and characteristics
图1-3 A外设的服务和特性![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/CBPeripheralData_Example_2x.png)



### Centrals Explore and Interact with the Data on a Peripheral 中心设备在外围设备上探索数据并与之交互

After a central has successfully established a connection to a peripheral, it can discover the full range of services and characteristics the peripheral has to offer (advertising data might contain only a fraction of the available services).
在中心设备成功建立到外围设备的连接之后，它可以发现外围设备必须提供的全部服务和特性（广告数据可能只包含可用服务的一小部分）。

A central can also interact with a peripheral’s service by reading or writing the value of that service’s characteristic. For example, your app may request the current room temperature from a digital thermostat, or it may provide the thermostat with a value at which to set the room’s temperature.
中心设备还可以通过阅读或写入外围设备的服务的特征值来与该服务交互。例如，您的应用可能会向数字恒温器请求当前的室温，或者它可能会向恒温器提供一个用于设置室温的值。



## How Centrals, Peripherals, and Peripheral Data Are Represented 如何表示中心设备、外围设备和外围设备数据

The major players and data involved in Bluetooth low energy communication are mapped onto the Core Bluetooth framework in a simple, straightforward way.
蓝牙低功耗通信中涉及的主要参与者和数据以简单直接的方式映射到Core蓝牙框架。



### Objects on the Central Side 中央侧的物体

When you are using a local central to interact with a remote peripheral, you are performing actions on the central side of Bluetooth low energy communication. Unless you are setting up a local peripheral device—and using it to respond to requests by a central—most of your Bluetooth transactions will take place on the central side.
当您使用本地中心设备与远程外围设备交互时，您是在蓝牙低功耗通信的中心设备端执行操作。除非您正在设置本地外围设备并使用它来响应中心的请求，否则大多数蓝牙事务都将在中心端进行。

For information about how to implement the central role in your app, see [Performing Common Central Role Tasks](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonCentralRoleTasks/PerformingCommonCentralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH3-SW1) and [Best Practices for Interacting with a Remote Peripheral Device](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForInteractingWithARemotePeripheralDevice/BestPracticesForInteractingWithARemotePeripheralDevice.html#//apple_ref/doc/uid/TP40013257-CH6-SW1)
有关如何在应用中实施中心角色的信息，请参阅执行常见中心角色任务和与远程外围设备交互的最佳做法



#### Local Centrals and Remote Peripherals 本地中心和远程外围设备

On the central side, a local central device is represented by a `CBCentralManager` object. These objects are used to manage discovered or connected remote peripheral devices (represented by `CBPeripheral` objects), including scanning for, discovering, and connecting to advertising peripherals. Figure 1-4 shows how local centrals and remote peripherals are represented in the Core Bluetooth framework.
在中心侧，本地中心设备由 `CBCentralManager` 对象表示。这些对象用于管理发现或连接的远程外围设备（由 `CBPeripheral` 对象表示），包括扫描、发现和连接到广告外围设备。图1-4显示了本地中心设备和远程外围设备在Core Bluetooth框架中的表示方式。

**Figure 1-4** Core Bluetooth objects on the central side
图1-4中央侧的核心蓝牙对象![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/CBObjects_CentralSide_2x.png)



#### A Remote Peripheral’s Data Are Represented by CBService and CBCharacteristic Objects 用CBService和CBCharacteristic对象表示远程外设数据

When you are interacting with the data on a remote peripheral (represented by a `CBPeripheral` object), you are dealing with its services and characteristics. In the Core Bluetooth framework, the services of a remote peripheral are represented by `CBService` objects. Similarly, the characteristics of a remote peripheral’s service are represented by `CBCharacteristic` objects. Figure 1-5 illustrates the basic structure of a remote peripheral’s services and characteristics.
当您与远程外围设备（由 `CBPeripheral` 对象表示）上的数据交互时，您正在处理其服务和特征。在核心蓝牙框架中，远程外设的服务由 `CBService` 对象表示。类似地，远程外围设备的服务的特征由 `CBCharacteristic` 对象表示。图1-5说明了远程外设的服务和特性的基本结构。

**Figure 1-5** A remote peripheral’s tree of services and characteristics
图1-5远程外设的服务和特征树![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/TreeOfServicesAndCharacteristics_Remote_2x.png)



### Objects on the Peripheral Side 外围侧的对象

As of macOS 10.9 and iOS 6, Mac and iOS devices can function as Bluetooth low energy peripherals, serving data to other devices, including other Mac, iPhone, and iPad devices. When setting up your device to implement the peripheral role, you are performing actions on the peripheral side of Bluetooth low energy communication.
从macOS 10.9和iOS 6开始，Mac和iOS设备可以用作蓝牙低功耗外设，为其他设备提供数据，包括其他Mac、iPhone和iPad设备。设置设备以实现外设角色时，您正在低功耗蓝牙通信的外设端执行操作。



#### Local Peripherals and Remote Centrals 本地外围设备和远程中心

On the peripheral side, a local peripheral device is represented by a `CBPeripheralManager` object. These objects are used to manage published services within the local peripheral device’s database of services and characteristics and to advertise these services to remote central devices (represented by `CBCentral` objects). Peripheral manager objects are also used to respond to read and write requests from these remote centrals. Figure 1-6 shows how local peripherals and remote centrals are represented in the Core Bluetooth framework.
在外围设备侧，本地外围设备由 `CBPeripheralManager` 对象表示。这些对象用于管理本地外围设备的服务和特性数据库内的已发布服务，并将这些服务通告给远程中央设备（由 `CBCentral` 对象表示）。外围设备管理器对象还用于响应来自这些远程中心的读写请求。图1-6显示了本地外围设备和远程中心设备在核心蓝牙框架中的表示方式。

**Figure 1-6** Core Bluetooth objects on the peripheral side
图1-6外设侧的核心蓝牙对象![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/CBObjects_PeripheralSide_2x.png)



#### A Local Peripheral’s Data Are Represented by CBMutableService and CBMutableCharacteristic Objects 用CBMutableService和CBMutableCharacteristic对象表示本地外设的数据

When you are setting up and interacting with the data on a local peripheral (represented by a `CBPeripheralManager` object), you are dealing with mutable versions of its services and characteristics. In the Core Bluetooth framework, the services of a local peripheral are represented by `CBMutableService` objects. Similarly, the characteristics of a local peripheral’s service are represented by `CBMutableCharacteristic` objects. Figure 1-7 illustrates the basic structure of a local peripheral’s services and characteristics.
当您在本地外围设备（由 `CBPeripheralManager` 对象表示）上设置和交互数据时，您正在处理其服务和特征的可变版本。在核心蓝牙框架中，本地外设的服务由 `CBMutableService` 对象表示。类似地，本地外围设备的服务的特征由 `CBMutableCharacteristic` 对象表示。图1-7说明了本地外设的服务和特性的基本结构。

**Figure 1-7** A local peripheral’s tree of services and characteristics
图1-7本地外设的服务和特征树![img](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/Art/TreeOfServicesAndCharacteristics_Local_2x.png)

For more information about how to set up your local device to implement the peripheral role, see [Performing Common Peripheral Role Tasks](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW1) and [Best Practices for Setting Up Your Local Device as a Peripheral](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral/BestPracticesForSettingUpYourIOSDeviceAsAPeripheral.html#//apple_ref/doc/uid/TP40013257-CH5-SW1).