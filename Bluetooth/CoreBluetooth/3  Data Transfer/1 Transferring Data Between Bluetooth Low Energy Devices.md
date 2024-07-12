Sample Code 示例代码

# Transferring Data Between Bluetooth Low Energy Devices 

Create a Bluetooth low energy central and peripheral device, and allow them to discover each other and exchange data.
创建低功耗蓝牙中央和外围设备，并允许它们相互发现并交换数据。

[Download  下载](https://docs-assets.developer.apple.com/published/68b84653b34e/TransferringDataBetweenBluetoothLowEnergyDevices.zip)

iOS 12.0+ ｜ iPadOS 12.0+ ｜ Xcode 11.1+ 



## [Overview 概述](https://developer.apple.com/documentation/corebluetooth/transferring-data-between-bluetooth-low-energy-devices#Overview)

This sample shows how to transfer data between two iOS devices, with one acting as a Bluetooth central and the other as a peripheral, by using a [`CBCharacteristic`](https://developer.apple.com/documentation/CoreBluetooth/CBCharacteristic) on the peripheral side that changes its value. The value change is automatically picked up on the central side. The sample also shows how the central side can write data to a [`CBCharacteristic`](https://developer.apple.com/documentation/CoreBluetooth/CBCharacteristic) on the peripheral side.
此示例显示如何在两台iOS设备之间传输数据，其中一台设备作为蓝牙中心设备，另一台设备作为外设，方法是在外设端使用 `CBCharacteristic` 更改其值。值的变化在中心侧自动拾取。该示例还显示了中心端如何将数据写入外围端的 `CBCharacteristic` 。

This sample shows how to handle flow control in this scenario. It also covers a rudimentary way to use the Received Signal Strength Indicator (RSSI) value to determine whether data transfer is feasible.
此示例说明如何处理此方案中的流控制。它还介绍了使用接收信号强度指示符（RSSI）值来确定数据传输是否可行的基本方法。



### [Configure the Sample Code Project 配置示例代码项目](https://developer.apple.com/documentation/corebluetooth/transferring-data-between-bluetooth-low-energy-devices#Configure-the-Sample-Code-Project)

1. Run the sample on two devices that support Bluetooth LE.
   在两台支持蓝牙LE的设备上运行示例。
2. On one device, tap the “Central” button. This device will be the central mode device. The device will begin scanning for a peripheral device that is advertising the Transfer Service.
   在一台设备上，点击“中央”按钮。此设备将是中央模式设备。设备将开始扫描通告传输服务的外围设备。
3. On the other device, tap the “Peripheral” button. This device will be the peripheral mode device.
   在另一台设备上，点击“外围设备”按钮。此设备将是外围模式设备。
4. On the peripheral mode device, tap the advertise on/off switch, to enable peripheral mode advertising of the data in the text field.
   在外设模式设备上，点击广告开/关开关，以启用文本字段中数据的外设模式广告。
5. Bring the two devices close to each other.
   将两个设备靠近。



### [Discover Bluetooth Peripherals and Connect to Them 发现蓝牙外设并连接到它们](https://developer.apple.com/documentation/corebluetooth/transferring-data-between-bluetooth-low-energy-devices#Discover-Bluetooth-Peripherals-and-Connect-to-Them)

The device running in central mode creates a [`CBCentralManager`](https://developer.apple.com/documentation/CoreBluetooth/CBCentralManager), assigning the `CentralViewController` as the manager’s delegate. It calls [`scanForPeripherals`](https://developer.apple.com/documentation/CoreBluetooth/CBCentralManager/scanForPeripherals(withServices:options:)) to discover other Bluetooth devices, passing in the UUID of the service it’s searching for.
在中央模式下运行的设备创建 `CBCentralManager` ，将 `CentralViewController` 分配为管理器的代表。它调用 `scanForPeripherals` 来发现其他蓝牙设备，并传递它正在搜索的服务的UUID。

```
centralManager.scanForPeripherals(withServices: [TransferService.serviceUUID],
                                   options: [CBCentralManagerScanOptionAllowDuplicatesKey: true])
```

When the central manager discovers a peripheral with a matching service UUID, it calls [`centralManager(_:didDiscover:advertisementData:rssi:)`](https://developer.apple.com/documentation/CoreBluetooth/CBCentralManagerDelegate/centralManager(_:didDiscover:advertisementData:rssi:)). The sample’s implementation of this method uses the `rssi` (Received Signal Strength Indicator) parameter to determine whether the signal is strong enough to transfer data. RSSI values are provided as negative numbers, with a theortetical maximum of `0`. The sample proceeds with transfer if the `rssi` is greater than or equal to `-50`. If the peripheral’s signal is strong enough, the method saves the peripheral as the property `discoveredPeripheral` and calls [`connect`](https://developer.apple.com/documentation/CoreBluetooth/CBCentralManager/connect(_:options:)) to connect to it.
当中央管理器发现具有匹配服务UUID的外围设备时，它调用 `centralManager(_:didDiscover:advertisementData:rssi:)` 。此方法的示例实现使用 `rssi` （接收信号强度指示符）参数来确定信号是否足够强以传输数据。RSSI值以负数形式提供，理论上最大值为 `0` 。如果 `rssi` 大于或等于 `-50` ，则样本继续传送。如果外围设备的信号足够强，该方法将外围设备保存为属性 `discoveredPeripheral` ，并调用 `connect` 连接到它。

```
func centralManager(_ central: CBCentralManager, didDiscover peripheral: CBPeripheral,
                    advertisementData: [String: Any], rssi RSSI: NSNumber) {
    
    // Reject if the signal strength is too low to attempt data transfer.
    // Change the minimum RSSI value depending on your app’s use case.
    guard RSSI.intValue >= -50
        else {
            os_log("Discovered perhiperal not in expected range, at %d", RSSI.intValue)
            return
    }
    
    os_log("Discovered %s at %d", String(describing: peripheral.name), RSSI.intValue)
    
    // Device is in range - have we already seen it?
    if discoveredPeripheral != peripheral {
        
        // Save a local copy of the peripheral, so CoreBluetooth doesn't get rid of it.
        discoveredPeripheral = peripheral
        
        // And finally, connect to the peripheral.
        os_log("Connecting to perhiperal %@", peripheral)
        centralManager.connect(peripheral, options: nil)
    }
}
```



### [When the Peripheral Receives a Connection, Send the Data 当外设接收到连接时，发送数据](https://developer.apple.com/documentation/corebluetooth/transferring-data-between-bluetooth-low-energy-devices#When-the-Peripheral-Receives-a-Connection-Send-the-Data)

The device running in peripheral mode creates a [`CBPeripheralManager`](https://developer.apple.com/documentation/CoreBluetooth/CBPeripheralManager) and assigns its `PeripheralViewController` as the manager’s delegate.
在外设模式下运行的设备创建 `CBPeripheralManager` 并将其 `PeripheralViewController` 分配为管理器的委托。

When the [`peripheralManagerDidUpdateState`](https://developer.apple.com/documentation/CoreBluetooth/CBPeripheralManagerDelegate/peripheralManagerDidUpdateState(_:)) method indicates that Bluetooth has powered on, the sample calls a private `setupPeripheral()` method to create a [`CBMutableCharacteristic`](https://developer.apple.com/documentation/CoreBluetooth/CBMutableCharacteristic) called `transferCharacteristic`. It then creates a [`CBMutableService`](https://developer.apple.com/documentation/CoreBluetooth/CBMutableService) from the characteristic and adds the service to the [`CBPeripheralManager`](https://developer.apple.com/documentation/CoreBluetooth/CBPeripheralManager).
当 `peripheralManagerDidUpdateState` 方法指示蓝牙已通电时，示例调用私有 `setupPeripheral()` 方法以创建名为 `transferCharacteristic` 的 `CBMutableCharacteristic` 。然后，它从特征创建 `CBMutableService` ，并将服务添加到 `CBPeripheralManager` 。

```
private func setupPeripheral() {
    
    // Build our service.
    
    // Start with the CBMutableCharacteristic.
    let transferCharacteristic = CBMutableCharacteristic(type: TransferService.characteristicUUID,
                                                     properties: [.notify, .writeWithoutResponse],
                                                     value: nil,
                                                     permissions: [.readable, .writeable])
    
    // Create a service from the characteristic.
    let transferService = CBMutableService(type: TransferService.serviceUUID, primary: true)
    
    // Add the characteristic to the service.
    transferService.characteristics = [transferCharacteristic]
    
    // And add it to the peripheral manager.
    peripheralManager.add(transferService)
    
    // Save the characteristic for later.
    self.transferCharacteristic = transferCharacteristic


}
```



The user interface provides a [`UISwitch`](https://developer.apple.com/documentation/uikit/uiswitch) that starts or stops advertising of the peripheral’s service UUID.
用户界面提供了一个 `UISwitch` ，用于启动或停止外围设备服务UUID的通告。

```
@IBAction func switchChanged(_ sender: Any) {
    // All we advertise is our service's UUID.
    if advertisingSwitch.isOn {
        peripheralManager.startAdvertising([CBAdvertisementDataServiceUUIDsKey: [TransferService.serviceUUID]])
    } else {
        peripheralManager.stopAdvertising()
    }
}
```

Once the central device discovers and connects to the peripheral, the peripheral side sends the data from the text field to the central. `PeripheralViewController` sends the data in chunks — each sized to the maximum value the central can receive — by setting the value of its `transferCharacteristic` property to the latest chunk. When finished, it sends the value `EOM` (for “end of message”).
一旦中心设备发现并连接到外围设备，外围设备侧将数据从文本字段发送到中心设备。 `PeripheralViewController` 通过将其 `transferCharacteristic` 属性的值设置为最新的块，以块的形式发送数据-每个块的大小为中心可以接收的最大值。完成后，它发送值 `EOM` （表示“消息结束”）。



### [When the Central Receives the Data, Update the User Interface 当中心接收到数据时，更新用户界面](https://developer.apple.com/documentation/corebluetooth/transferring-data-between-bluetooth-low-energy-devices#When-the-Central-Receives-the-Data-Update-the-User-Interface)

Back on the central device, a call to the central manager delegate’s [`peripheral(_:didDiscoverCharacteristicsFor:Error:`](https://developer.apple.com/documentation/CoreBluetooth/CBPeripheralDelegate/peripheral(_:didDiscoverCharacteristicsFor:error:)) tells the app that it has discovered the peripheral’s transfer characteristic. The sample’s implementation of this method calls [`setNotifyValue(_:for:)`](https://developer.apple.com/documentation/CoreBluetooth/CBPeripheral/setNotifyValue(_:for:)) to start receiving updates to the characteristic’s value.
回到中央设备上，调用中央管理器委托的 `peripheral(_:didDiscoverCharacteristicsFor:Error:` 会告诉应用它已发现外围设备的传输特征。此方法的示例实现调用 `setNotifyValue(_:for:)` 以开始接收对特征值的更新。

When the value does update — meaning text is available — the central manager calls the delegate method [`peripheral(_:didUpdateValueFor:error)`](https://developer.apple.com/documentation/CoreBluetooth/CBPeripheralDelegate/peripheral(_:didUpdateValueFor:error:)-1xyna). The sample looks to see if the data is a chunk or an end-of-message marker. If the data is a chunk, the code appends the chunk to an internal buffer containing the peripheral’s message. If the data is an end-of-message marker, it converts the buffer to a string and sets it as the contents of the text field.
当值更新时-意味着文本可用-中央管理器调用委托方法 `peripheral(_:didUpdateValueFor:error)` 。该示例查看数据是块还是消息结束标记。如果数据是块，则代码将块附加到包含外围设备消息的内部缓冲区。如果数据是消息结束标记，则将缓冲区转换为字符串，并将其设置为文本字段的内容。

```
func peripheral(_ peripheral: CBPeripheral, didUpdateValueFor characteristic: CBCharacteristic, error: Error?) {
    // Deal with errors (if any)
    if let error = error {
        os_log("Error discovering characteristics: %s", error.localizedDescription)
        cleanup()
        return
    }
    
    guard let characteristicData = characteristic.value,
        let stringFromData = String(data: characteristicData, encoding: .utf8) else { return }
    
    os_log("Received %d bytes: %s", characteristicData.count, stringFromData)
    
    // Have we received the end-of-message token?
    if stringFromData == "EOM" {
        // End-of-message case: show the data.
        // Dispatch the text view update to the main queue for updating the UI, because
        // we don't know which thread this method will be called back on.
        DispatchQueue.main.async() {
            self.textView.text = String(data: self.data, encoding: .utf8)
        }
        
        // Write test data
        writeData()
    } else {
        // Otherwise, just append the data to what we have previously received.
        data.append(characteristicData)
    }
}
```

Once the transfer is complete, you can press the “Back” button on each device and reassign the central and peripheral roles, to perform the transfer in the opposite direction.
传输完成后，您可以按下每个设备上的“返回”按钮，重新分配中央和外围设备角色，以执行相反方向的传输。
