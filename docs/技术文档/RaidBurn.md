### 

# RaidBurn

| 字段           | 类型          | 说明                                                         | 备注                                                         |
| -------------- | ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| RaidId         | VARCHAR(40)   | 标识Raid组                                                   |                                                              |
| LibraryId      | VARCHAR(40)   | 库ID                                                         |                                                              |
| RaidLevel      | VARCHAR(10)   | 分数值                                                       | k/m                                                          |
| DataVolumeList | VARCHAR(1024) | RAID数据盘                                                   | 以';'分隔                                                    |
| ParityDiscList | VARCHAR(1024) | RAID校验盘                                                   | 以';'分隔                                                    |
| BrokenDiscList | VARCHAR(1024) | RAID错误盘                                                   | 以';'分隔                                                    |
| CreateTime     | timestamp     | 创建时间                                                     | 时间戳                                                       |
| ModifyTime     | timestamp     | 修改时间                                                     | 时间戳                                                       |
| Status         | INT           | 0 未做RAID计算 <br>1 已经做RAID<br>2 数据刻录中 <br>3 数据刻录完成<br>4 校验数据生成中<br>5 校验数据完成<br>6 校验盘刻录中<br>7 校验盘记录完成<br>8 完成 | 103 刻录失败<br>104 生成校验失败<br>105 校验失败<br>106 失败<br>101 恢复中 |

a1cli 恢复接口

加个恢复状态

判断是否为可恢复状态

文件目录oid/raidid/volid

11752-11763