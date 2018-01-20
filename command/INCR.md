## Redis Incr命令

Redis`Incr`命令将key中储存的数字值增一。

如果key不存在，那么key的值会先被初始化为`0`，然后再执行INCR操作。

如果值包含错误的类型，或字符串类型的值不能表示为数字，那么返回一个错误。

本操作的值限制在64位(bit)有符号数字表示之内。

**语法**

```shell
127.0.0.1:6379> INCR KEY_NAME
```

**返回值**

执行 INCR 命令之后 key 的值

**示例**

```shell
127.0.0.1:6379> SET i 20
OK
127.0.0.1:6379> INCR i
(integer) 21
127.0.0.1:6379> GET i
"21"
```