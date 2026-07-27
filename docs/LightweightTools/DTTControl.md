---
sidebar_label: DTT Control
sidebar_class_name: lightweight tools
---

# DTT Control

为方便进行自动化测试，这个改程序将DTT在网页上才可以进行修改参数的操作，现在使用一个exe携带参数运行即可完成。

它通过DTT提供的Websocket通道，向DTT Server发送控制指令，可以修改生效不同的配置参数。

## 功能

1. 理论上来说，localhost:8888这个网页上能干的事情，它都可以干

## 前置条件

1. 不同平台、不同BIOS、不同DTT版本都可能会因命令不一致导致执行失败，使用前应与liuty24共同测试确认
2. 目前测试可用的DTT版本为：Software Version: 9.0.11700.43962

## 使用方法


```
DTTControl.exe [Function] <Param>
```

### Set EPO Gear

示例：
```
DTTControl.exe setepo 1
```
![](./DTTControl/example.png)

## 脚本集成示例

```
:runTest

    "%AutoCharge%" %socketport%

    "%AutoCharge%" %socketport% 0

    for /L %%j IN (1, 1, 7) do (
        "\\VM-SERVER\lnvpe-share\TOOL\DTTControl.exe" setepo %%j
        for /L %%i IN (1, 1, %looptimes%) do (
            call :runBench "EPO%%j-%%i" "%logpath%"
        )
    )

    "%AutoCharge%" %socketport% 1
```

## 项目地址

[Github仓库]（https://github.com/ltycn/DTTControl）