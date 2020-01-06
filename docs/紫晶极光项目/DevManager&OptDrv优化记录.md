# devManager&OptDrv优化方案



[TOC]

## 说明

- 针对recovery 恢复进行优化
- 

| 3-2      NSA设置/API（NFS/CIFS）            |      | 2019年7月15日 | 2019年7月19日 | 5    |
| ------------------------------------------- | ---- | ------------- | ------------- | ---- |
| 3-3      文件接口（用户权限）               | #3-3 | 2019年6月20日 | 2019年7月12日 | 17   |
| 4-3      刻录作业查询/API                   |      | 2019年7月22日 | 2019年7月26日 | 5    |
| 4-4        光盘库与控制服务器的日志查询/API |      | 2019年5月27日 | 2019年6月19日 | 17   |

## 光盘库与控制服务器日志查询

###数据库模型

#### systemevents

- 说明

  > 1. 收集系统日志

- 结构

  | 字段名             | 类型                        | 值   | 备注 |
  | ------------------ | --------------------------- | ---- | ---- |
  | id                 | integer                     |      |      |
  | customerid         | bigint                      |      |      |
  | receivedat         | timestamp without time zone |      |      |
  | devicereportedtime | timestamp without time zone |      |      |
  | facility           | smallint                    |      |      |
  | priority           | smallint                    |      |      |
  | fromhost           | character varying(60)       |      |      |
  | message            | text                        |      |      |
  | ntseverity         | integer                     |      |      |
  | importance         | integer                     |      |      |
  | eventsource        | character varying(60)       |      |      |
  | eventuser          | character varying(60)       |      |      |
  | eventcategory      | integer                     |      |      |
  | eventid            | integer                     |      |      |
  | eventbinarydata    | text                        |      |      |
  | maxavailable       | integer                     |      |      |
  | currusage          | integer                     |      |      |
  | minusage           | integer                     |      |      |
  | maxusage           | integer                     |      |      |
  | infounitid         | integer                     |      |      |
  | syslogtag          | character varying(60)       |      |      |
  | eventlogtype       | character varying(60)       |      |      |
  | genericfilename    | character varying(60)       |      |      |
  | systemid           | integer                     |      |      |
  |                    |                             |      |      |
  |                    |                             |      |      |

  