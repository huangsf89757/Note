Instance Property 实例属性

# characteristic

The characteristic to read or write the value of.
读取或写入值的特性。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ ｜ tvOS 9.0+ ｜ visionOS 1.0+ ｜ watchOS 2.0+ 

```
var characteristic: CBCharacteristic { get }
```



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbattrequest/characteristic#see-also)

### [Requesting to Read and Write Characteristic Values 请求读写特征值](https://developer.apple.com/documentation/corebluetooth/cbattrequest/characteristic#Requesting-to-Read-and-Write-Characteristic-Values)

[`var central: CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/central)

The remote central device that originated the request.
发起请求的远程中心设备。

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/value)

The data that the central reads from or writes to the peripheral.
中心设备从外围设备读取或向外围设备写入的数据。

[`var offset: Int`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/offset)

The zero-based index of the first byte for the read or write request.
读或写请求的第一个字节的从零开始的索引。
