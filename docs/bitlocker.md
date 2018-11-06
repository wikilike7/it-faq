# Bitlocker指南

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.03.29|
|0.02|Shichao Wang|2018.11.06|

## 在未完成解密的情况下对分区进行扩展导致系统无法启动

> 这个情况很特殊，用户的c分区开启了bitlocker且未完成解密，又将e分区的空余空间挪至c分区，重启后系统停留在Lenovo Logo的界面，光标一直在左上角闪烁。

1. 从`Windows安装光盘`引导启动，进入修复并开启命令行。
2. 用`dir`确定哪个是系统分区，在命令行下c分区的标识符即可能是c，也可能是d，这个需要当时分析。
3. 输入：`manage-bde -off d:`, 这条命令的作用是解密系统分区的解密。
4. 输入`manage-bde -status`, 查看解密的状态，当解密完成后重启。
5. 重启完成后进入`PE`, 修复系统引导和设置系统分区为当前激活分区。

[参考链接](https://technet.microsoft.com/en-us/library/ee706522(v=ws.10).aspx)

## 没有本地管理员权限，已经脱离域时如何格式化数据且删除Bitlocker

前提概要：
> 公司的安全策略很严格，IT也是没有本地管理员权限，且此计算机已经脱离域，无法登陆，计算机有一块磁盘且只有一个分区，磁盘已经做了Bitlocker加密

1. 尝试从公司的定制的PE来启动计算机，但是总是失败
2. 从自己下载的PE启动，进入PE
3. 用分区助手可以格式化分区，达到删除数据的目的
4. 从硬盘重新启动计算机，因为分区已经删除，所以计算机会进入修复模式，此时选择进入高级修复模式，选择命令行
5. 下面列出使用的相关命令（如遇到不懂的命令请自行查找）：

    ``` batch
    manage-bde -status ##返回的是没有加密的分区

    diskpart
    list disk
    select disk 0  ## 也可能是1，具体看下硬盘大小
    clean
    create part primary
    select part 1
    format fs=ntfs quick label=system
    active
    assgin
    exit
    ```

6. 再从PE进入发现原来的Bitlocker已经没有了，分区也是空的