# 理解虚拟DOM及key属性的作用

### 为什么不能用index属性作为key值？

```
测试发现，最好不要用index作为key，用index作为key有时候还会导致bug，尤其是item是具有某种状态的时候。。举个简单的例子，如果有ABC三个item，其中第一个A是选中的，这个时候如果我在A前面添加D，如果用index作为key就会变成D是选中的了，建议用唯一id来作为key
--吴银春
```



