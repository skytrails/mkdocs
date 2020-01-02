# 表字段含义说明

## TBL_SLOT表

###burnstate

- DISC_EMPTY = 0  **空盘**
- DISC_INCOMPLETE = 1    
- DISC_FINALIZED = 2    **用于极光MHL状态，刻录完成（包括失败）**
- DISC_OTHERS = 3  
- DISC_SETVOLUE = 4  **设置光盘volue信息**
- DISC_NEEDVERIFY = 5  **待校验**
- DISC_READY = 6  **刻录完成**
- DISC_FAILED = 7    **刻录失败**
- DISC_TOTAL = 8   

- 现在状态2用于MHL，4，5，6，7用于ZL系列

## TBL_LVM

### state

- 0  LVM_STATE_ASSIGNING  # 正在向MW_Devmanager申请slot
- 1  LVM_STATE_IDEL   #   向MW_Devmanager申请slot成功，状态空闲可用
- 2  LVM_STATE_WRITING_FILE    # slot分配了给一个bucket，文件正在写入
- 3  LVM_STATE_FULL         #slot 满了
- 4  LVM_STATE_FINALIZING  #     udf slot 封盘（就是做MD文件）
- 5  LVM_STATE_FINALIZED  #    udf slot 封盘完成
- 6  LVM_STATE_MAKING_MD  #    未用
- 7  LVM_STATE_MAKED_MD  #    未用
- 8  LVM_STATE_BURNING    # 刻录，流程是：打开slot(移盘)->刻录->校验
- 9  LVM_STATE_BURNT    # 上述刻录流程完成
- 10 LVM_STATE_VERIFING  # 校验文件
- 11 LVM_STATE_VERIFIED  # 未用
- 12 LVM_STATE_COMPLETE   # 刻录完成后，将会进行其他操作，例如弹出盘，通知其他模块生成存根，若这些都完成，则完成
- 13 LVM_STATE_ERROR    #
- 14 LVM_STATE_FINALIZE_ERR    #udf slot 封盘错误
- 15 LVM_STATE_BURN_ERR  # 刻录失败，通用刻录错误，可能是移盘失败，可能是没可用光驱，会重试
- 16 LVM_STATE_MEDIUM_ERR  # 刻录失败，并且是光盘刻录过程中失败，将会换盘重刻
- 17 LVM_STATE_REDO  # 各种数据损坏丢失时，lvm 重做
- 18 LVM_STATE_REDO_SUCC  # lvm 重做成功
- 19         # 最终成功
- 20      # 刻录失败，需人为重试
- 21         # 刻录完成，未校验。
- 22 LVM_STATE_FINALIZE_FAIL     # 封盘失败
- 23 LVM_STATE_OPENING_SLOT     # 正在打开slot
- 24 LVM_STATE_AWAIT_BURN         # 等待刻录
- 25 LVM_STATE_REPLACING               # 换盘中

  

## odd

### phystate

HAL_DRV_ODD_UNKNOW_STATE = 0;    

HAL_DRV_ODD_EMPTY,                    空光驱

HAL_DRV_EJECT,								    hold a slot, but ejected

HAL_DRV_INJECT,						          hold a slot, injected		  

HAL_DRV_UMOUNT,                             hold a slot, but not mount

HAL_DRV_MOUNT								mounted

### devstate

### runstate

ODD_IDLE,

ODD_RESERVED,

ODD_ERROR

## state

slot_nearline_idle = 0;

slot_nearline_mounted = 1;

slot_offline

slot_outlib

slot_state_not



## PLC ErrCode

1    未完成

2    内部错误

3    不支持的操作

4    需要初始化

5    初始化失败

6    校验

7    send错误

8    设备故障，初始化失败

9    已关机poweroff

10    设备忙

11    设备忙

12    超时

13    无碟片

14    光驱未弹出

15    光驱未收回

16    盘匣弹出失败

17    多盘匣弹出

18    机械臂故障

19    光盘库roll

20    碟片丢失

21    卡碟(disc in arm)

22    

31     碟片数据不对

32    无效addr

33    no such entry

34    cart not ready

39   SRCEMPTY

40   DSTFULL

52 LOSDISP

50 非法参数



in_queue

write_fail





1、进度：



