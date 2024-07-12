Initializer

# init(type:primary:) 

Creates a newly initialized mutable service specified by UUID and service type.
创建一个由UUID和服务类型指定的新初始化的可变服务。

iOS 6.0+ ｜ iPadOS 6.0+ ｜ Mac Catalyst 13.1+ ｜ macOS 10.9+ 

```
init(
    type UUID: CBUUID,
    primary isPrimary: Bool
)
```



## [Parameters  参数](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/init(type:primary:)#parameters)

- `UUID`

  A 128-bit UUID that identifies the service. 

  标识服务的128位UUID。

- `isPrimary`

  A Boolean value that indicates whether the type of service is primary or secondary. If the value is [`true`](https://developer.apple.com/documentation/swift/true), the type of service is primary. If the value is [`false`](https://developer.apple.com/documentation/swift/false), the type of service is secondary. 
  
  一个布尔值，指示服务类型是主服务还是辅助服务。如果值为 `true` ，则服务类型为primary。如果值为 `false` ，则服务类型为次要。



## [Return Value 返回值](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/init(type:primary:)#return-value)

A newly initialized mutable service.
新初始化的可变服务。



## [Discussion 讨论](https://developer.apple.com/documentation/corebluetooth/cbmutableservice/init(type:primary:)#discussion)

For more information, see [Core Bluetooth Programming Guide](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/CoreBluetooth_concepts/AboutCoreBluetooth/Introduction.html#//apple_ref/doc/uid/TP40013257).
有关详细信息，请参阅Core Bluetooth Programming Guide。
