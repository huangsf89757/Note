Instance Property 实例属性

# offset

The zero-based index of the first byte for the read or write request.
读或写请求的第一个字节的从零开始的索引。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var offset: Int { get }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbattrequest/offset#Discussion)

You can use the value of this property to ensure that the ATT request is attempting to read or write within the proper bounds of the characteristic’s value. For an example of how to take a request’s offset property into account when responding to a read or write request, see [Responding to Read and Write Requests from a Central](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/PerformingCommonPeripheralRoleTasks/PerformingCommonPeripheralRoleTasks.html#//apple_ref/doc/uid/TP40013257-CH4-SW6).
您可以使用此属性的值来确保ATT请求尝试在特征值的适当范围内进行读取或写入。有关如何在响应读或写请求时考虑请求的偏移量属性的示例，请参见响应来自中心的读和写请求。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbattrequest/offset#see-also)

### [Requesting to Read and Write Characteristic Values 请求读写特征值](https://developer.apple.com/documentation/corebluetooth/cbattrequest/offset#Requesting-to-Read-and-Write-Characteristic-Values)

[`var central: CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/central)

The remote central device that originated the request.
发起请求的远程中心设备。

[`var characteristic: CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/characteristic)

The characteristic to read or write the value of.
读取或写入值的特性。

[`var value: Data?`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/value)

The data that the central reads from or writes to the peripheral.
中心设备从外围设备读取或向外围设备写入的数据。
