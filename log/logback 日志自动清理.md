# logback 日志自动清理

```xml
<rollingPolicy class="ch.qos.logback.core.rolling.SizeAndTimeBasedRollingPolicy">
    <fileNamePattern>/root/demo/logs/info.%d.%i.log</fileNamePattern>
    <!-- 单个日志文件最大文件大小 -->
    <maxFileSize>100 MB</maxFileSize>
    <!-- 保留日志文件的最大数量 -->
    <maxHistory>15</maxHistory>
    <!-- 单个日志文件最大 100 MB，保留 15 天的历史记录，但最多 20GB -->
    <totalSizeCap>20GB</totalSizeCap>
    <!-- 重启清理日志文件 -->
    <cleanHistoryOnStart>true</cleanHistoryOnStart>
</rollingPolicy>
```

## 注意

1. maxHistory 单位，根据滚动策略决定。如果设置按天滚动，则 maxHistory 单位为天；如果设置按月滚动，则 maxHistory 单位为月。以此类推。
2. logback 清理机制，可查看源码 `TimeBasedRollingPolicy`、`TimeBasedArchiveRemover`类，得出 logback 只能删除【当前时间 - maxHistory 至 当前时间 - maxHistory - 32 天】的日志文件（前提：maxHistory 单位为天，其他单位需根据源码再计算）