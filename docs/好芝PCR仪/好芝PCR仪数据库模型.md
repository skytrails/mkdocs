# 数据库模型

## 用户表(SYS_ACCOUNT)

| 字段名称   | 数据类型   | 值       | 备注     |
| ---------- | ---------- | -------- | -------- |
| USERNAME   | char(255)  | not null | 用户名   |
| PASSWD     | char(255)  | 不为空   |          |
| USERTYPE   | INT        | 不为空   |          |
| CREATETIME | DATETIME   | 不为空   | 创建时间 |
| MODIFYTIME | DATETIME   |          | 修改时间 |
| EXPTIME    | DATETIME   |          |          |
| COMMENT    | CHAR(1024) | 可为空   | 说明     |



## 实验数据表（SYS_PROGRAM）

| 字段名称     | 数据类型  | 值                                 | 备注                             |
| ------------ | --------- | ---------------------------------- | -------------------------------- |
| ROWID        | INTEGER   | 从0自增                            |                                  |
| NAME         | CHAR(255) | NOT NULL                           | 实验名称                         |
| FILENAME     | CHAR(255) |                                    | 文件名                           |
| AREA         | CHAR(8)   |                                    | 反应区                           |
| PORE         | CHAR(8)   |                                    | 反应孔                           |
| S_NAME       | CHAR(255) |                                    | 样本名称                         |
| S_COL        | INTEGER   |                                    | 样本颜色                         |
| S_TYPE       | INTEGER   |                                    | 样本类型                         |
| T_NAME       | CHAR(255) |                                    | 靶标名称                         |
| T_COL        | INTEGER   |                                    | 靶标颜色                         |
| CHANNEL      | INTEGER   |                                    | 通道                             |
| DIM          | CHAR(32)  |                                    | 二维码ID<br />0 新建<br />1 导入 |
| TEMPID       | INTEGER   | NOT NULL DEFAULT -1                | 报告模板ID                       |
| DETECTMETHOD | CHAR(255) |                                    | 检测方法                         |
| DETECTSEN    | CHAR(255) |                                    | 检测灵敏度                       |
| DETECTITEM   | CHAR(255) |                                    | 检测项目                         |
| CREATETIME   | TIMESTAMP | NOT NULL DEFAULT CURRENT_TIMESTAMP | 创建时间                         |

​                                                   

## 设置程序列表（EXP_LISTVIEW）

| 字段名称     | 数据类型   | 值       | 备注               |
| ------------ | ---------- | -------- | ------------------ |
| EXPNAME      | CHAR(255)  | NOT NULL | 程序名称           |
| EXPMODELNAME | CHAR(255)  | NOT NULL | 模块名称(不使用)   |
| EXPTYPE      | INT        | NOT NULL | 程序类型           |
| STAGECOUNT   | INT        | NOT NULL | 阶段数量           |
| STATUS       | INT        | NOT NULL | 状态（不使用）     |
| CURSTAGE     | CHAR       |          | 当前阶段           |
| CURSTEP      | CHAR(255)  |          | 当前步骤           |
| LASTRESULT   | CHAR(4096) |          | 结果表，废弃不使用 |
| STARTTIME    | DATETIME   |          | 开始时间           |
| MODIFYTIEM   | DATETIME   |          | 修改时间           |
| COMMENT      | CHAR(1024) |          | 说明               |

​                                                                                   

## 程序阶段列表（EXP_STAGEDATA）

| 字段名称   | 数据类型   | 值   | 备注                   |
| ---------- | ---------- | ---- | ---------------------- |
| EXPNAME    | CHAR(255)  |      | 程序名                 |
| EXPTYPE    | INT        |      | 类型                   |
| STAGENAME  | CHAR(255)  |      | 阶段名                 |
| STEPCOUNT  | INT        |      | 步骤数量               |
| SERIALID   | INT        |      | 步骤序号               |
| CYCLECOUNT | INT        |      | 循环数                 |
| STATUS     | INT        |      | 当前状态               |
| LASTRESULT | CHAR(4096) |      | 结果数据（废弃不使用） |
| STARTTIME  | DATETIME   |      | 创建时间               |
| MODIFYTIME | DATETIME   |      | 修改时间               |
| COMMENT    | CHAR(1024) |      | 说明                   |



## 程序步骤列表（EXP_STEPDATA）

| 字段名称     | 数据类型   | 值   | 备注       |
| ------------ | ---------- | ---- | ---------- |
| EXPNAME      | CHAR(255)  |      | 程序名     |
| EXPTYPE      | INT        |      | 类型       |
| STAGENAME    | CHAR(255)  |      | 阶段名     |
| STEPNAME     | CHAR(255)  |      | 步骤名     |
| SERIALID     | INT        |      | 步骤序号   |
| SPEED        | DOUBLE     |      | 升温速率   |
| TEMPERATURE  | INT        |      | 温度       |
| MINUTES      | INT        |      | 分钟       |
| SECONDS      | INT        |      | 秒         |
| BECOLLECTION | BOOLEAN    |      | 采集标识   |
| STATUS       | INT        |      | 状态       |
| BIASSTAUS    | BOOLEAN    |      | 废弃不使用 |
| LASTRESULT   | CHAR(4096) |      | 废弃不使用 |
| STARTTIME    | DATETIME   |      | 创建时间   |
| MODIFYTIME   | DATETIME   |      | 修改时间   |
| COMMENT      | CHAR(1024) |      | 说明       |



##实验报告模板表(EXP_REPORTTEMPLATE)

| 字段名称     | 数据类型   | 值        | 备注     |
| ------------ | ---------- | --------- | -------- |
| REPTEMPID    | INT        | NOT NULL  | 报告ID   |
| REPNAME      | CHAR(1024) | NOT NULL  | 报告名   |
| REPFLAG      | INT        | DEFAULT 0 | 标识     |
| ORGNAME      | CHAR(1024) |           | 机构名   |
| PROJID       | INT        |           | 项目ID   |
| REPCOMID     | INT        |           |          |
| SUBSTARTTIME | DATETIME   |           | 提交时间 |
| SUBENDTIME   | DATETIME   |           | 结果时间 |
| MODIFYTIME   | DATETIME   |           | 创建时间 |
| COMMENT      | CHAR(1024) |           | 说明     |

​    

## 实验机构表(EXP_REPORG)

| 字段名称   | 数据类型   | 值   | 备注       |
| ---------- | ---------- | ---- | ---------- |
| REPORGID   | INT        |      | 实验机构ID |
| REPORGNAME | CHAR(1024) |      | 机构名     |
| MODIFYTIME | DATETIME   |      | 修改时间   |
| COMMENT    | CHAR(1024) |      | 说明       |



## 实验报告备注信息表(EXP_REPORTCOMMENTS)

| 字段名称      | 数据类型   | 值       | 备注     |
| ------------- | ---------- | -------- | -------- |
| REPCOMID      | INT        |          | 报告ID   |
| NIT           | INT        | NOT NULL | 备注ID   |
| REPCOMNAME    | CHAR(1024) | NOT NULL | 备注名   |
| REPCOMCONTENT | CHAR(4096) | NOT NULL | 备注详情 |
| COMMENT       | CHAR(1024) |          | 说明     |



## 扩增曲线表（SYS_APPLICURVE）

| 字段名称 | 数据类型  | 值       | 备注       |
| -------- | --------- | -------- | ---------- |
| NAME     | CHAR(255) | NOT NULL | 实验名称   |
| FILENAME | CHAR(255) | NOT NULL | 实验文件名 |
| PORE     | INTEGER   |          | 反应孔     |
| SAMPLE   | CHAR(255) | NOT NULL | 样本名称   |
| TARGET   | CHAR(255) | NOT NULL | 靶标名称   |
| ROWID    | INTEGER   | 自增     |            |
| XROW     | INTEGER   |          | 横坐标     |
| YROW     | INTEGER   |          | 纵坐标     |



## 熔解曲线表（SYS_MELTCURVE）

| 字段名称 | 数据类型  | 值       | 备注       |
| -------- | --------- | -------- | ---------- |
| NAME     | CHAR(255) | NOT NULL | 实验名称   |
| FILENAME | CHAR(255) | NOT NULL | 实验文件名 |
| PORE     | INTEGER   |          | 反应孔     |
| SAMPLE   | CHAR(255) | NOT NULL | 样本名称   |
| TARGET   | CHAR(255) | NOT NULL | 靶标名称   |
| ROWID    | INTEGER   | 自增     |            |
| XROW     | INTEGER   |          | 横坐标     |
| YROW     | INTEGER   |          | 纵坐标     |

