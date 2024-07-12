Instance Property 实例属性

# value

The data that the central reads from or writes to the peripheral.
中心设备从外围设备读取或向外围设备写入的数据。

iOS 6.0+iPadOS 6.0+Mac Catalyst 13.1+macOS 10.9+tvOS 9.0+visionOS 1.0+watchOS 2.0+

```
var value: Data? { get set }
```



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbattrequest/value#Discussion)

The value of this property depends on whether the request type is read or write. For read requests, the property is `nil,` and you should set it before responding to the remote central through the [`respond(to:withResult:)`](https://developer.apple.com/documentation/corebluetooth/cbperipheralmanager/respond(to:withresult:)) method. For write requests, the value is the data to write to the characteristic’s value.
此属性的值取决于请求类型是读还是写。对于读取请求，属性为 `nil,` ，您应在通过 `respond(to:withResult:)` 方法响应远程中心之前设置该属性。对于写请求，该值是要写入特征值的数据。



## [See Also 另见](https://developer.apple.com/documentation/corebluetooth/cbattrequest/value#see-also)

### [Requesting to Read and Write Characteristic Values 请求读写特征值](https://developer.apple.com/documentation/corebluetooth/cbattrequest/value#Requesting-to-Read-and-Write-Characteristic-Values)

[`var central: CBCentral`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/central)

The remote central device that originated the request.
发起请求的远程中心设备。

[`var characteristic: CBCharacteristic`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/characteristic)

The characteristic to read or write the value of.
读取或写入值的特性。

[`var offset: Int`](https://developer.apple.com/documentation/corebluetooth/cbattrequest/offset)

The zero-based index of the first byte for the read or write request.
读或写请求的第一个字节的从零开始的索引。
