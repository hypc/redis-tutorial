## Redis Expireat命令

Redis`Expireat`命令用于以Unix时间戳格式设置键的到期时间。 在到期时间后，键将在Redis中失效不可用。

**语法**

```bash
127.0.0.1:6379> EXPIREAT KEY_NAME TIME_IN_UNIX_TIMESTAMP
```

**返回值**

一个整数：

* 如果成功地为该键设置了超时时间，返回`1`
* 如果键不存在或无法设置超时时间，返回`0`

**示例**

```bash
127.0.0.1:6379> SET my_key redis
OK
127.0.0.1:6379> EXPIREAT my_key 1516080509
(integer) 1
127.0.0.1:6379> EXISTS my_key
(integer) 0
127.0.0.1:6379> SET my_key redis
OK
127.0.0.1:6379> EXPIREAT my_key 1616080509
(integer) 1
127.0.0.1:6379> EXISTS my_key
(integer) 1
```
