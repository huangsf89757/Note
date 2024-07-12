Instance Method Instance 方法

# setDesiredConnectionLatency(_:for:) 

Sets the desired connection latency for an existing connection to a central device.
为与中央设备的现有连接设置所需的连接延迟。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
func setDesiredConnectionLatency(
    _ latency: CBPeripheralManagerConnectionLatency,
    for central: CBCentral
)
```



## [Parameters 参数](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/setdesiredconnectionlatency(_:for:)#parameters)

- `latency`

  The desired connection latency. For a list of the possible connection latency values that you may set for the peripheral manager, see [`CBPeripheralManagerConnectionLatency`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency). 

  所需的连接延迟。有关可以为外设管理器设置的可能连接延迟值的列表，请参见 `CBPeripheralManagerConnectionLatency` 。

- `central`

  The central to which the peripheral manager is currently connected. 

  外设管理器当前连接到的中央。

  

## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/setdesiredconnectionlatency(_:for:)#Discussion)

The latency of a peripheral-central connection controls how frequently the peripheral and the peripheral’s connected central can exchange messages. By setting a desired connection latency, you manage the relationship between the frequency of the data exchange and the resulting battery performance of the peripheral device. When you call this method to set the connection latency, note that connection latency changes aren’t guaranteed. As a result, the latency may vary. If you don’t explicitly set a latency, the central device uses the connection latency it chose when establishing the connection. Typically, you don’t need to change the connection latency.
外设-中央连接的延迟控制外设和外设连接的中央交换消息的频率。通过设置所需的连接延迟，可以管理数据交换频率与外围设备产生的电池性能之间的关系。调用该方法设置连接延迟时，请注意，不能保证连接延迟更改。因此，延迟可能会有所不同。如果未显式设置延迟，中央设备将使用在建立连接时选择的连接延迟。通常，您不需要更改连接延迟。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/setdesiredconnectionlatency(_:for:)#see-also)

### [Setting Connection Latency 设置连接延迟](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/setdesiredconnectionlatency(_:for:)#Setting-Connection-Latency)

[`enum CBPeripheralManagerConnectionLatency`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanagerconnectionlatency)

Values representing the connection latency of the peripheral manager.
表示外设管理器的连接延迟的值。
