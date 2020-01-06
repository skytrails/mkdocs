# AW_Archiver

[TOC]

##接口

###allocArchive

- 生成文件名，重名则递归
- getPendingBuffer 创建tbl_sfodata_id_timestamp，更新tbl_sfodata_index记录
- doWrite 查一些数据表，更新tbl_sfodata_id_timestamp数据，不做tar操作，这……

##表结构

##TBL_SFOARCHIVE

* 保存压缩文件路径信息

##TBL_SFODATA_INDEX

* 保存sfo表数据

## TBL_SFODATA_$ID_TIMESTAMP

* 保存小文件数据

## C++

- C++ 函数返回值的不同常量引用，引用，正常值

https://blog.csdn.net/u012814856/article/details/84099328

```c++
#include <iostream>
int main() {
  int a = 0;
  int b = 9;
  return 0;
}
int i = 0;
int b = 9;
```







| 范毅 |      |      |      |      |      |
| ---: | :--: | ---- | ---- | ---- | ---- |
|      |      |      |      |      |      |

