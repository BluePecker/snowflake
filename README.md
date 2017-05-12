## snowflake 算法

---

#### UniqueId结构

```
    1 符号位  |  39 时间戳                                     | 5 区域  |  9 节点      | 10 （毫秒内）自增ID
    0        |  0000000 00000000 00000000 00000000 00000000  | 00000  | 000000 000   |  000000 0000
```

#### 生成单个UniqueId

```
    var NodeId int64 = 1
    IdWorker, _ := snowflake.NewIdWorker(NodeId)
    UniqueId, _ := IdWorker.NextId()
```

#### 批理生成UniqueId

```
    var NodeId int64 = 1
    IdWorker, _ := snowflake.NewIdWorker(NodeId)
    UniqueIds, _ := IdWorker.NextIds()
```