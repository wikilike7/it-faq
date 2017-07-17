# Bitlocker指南

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.03.29|

## 在未完成解密的情况下对分区进行扩展导致系统无法启动
> 这个情况很特殊，用户的c分区开启了bitlocker且未完成解密，又将e分区的空余空间挪至c分区，重启后系统停留在Lenovo Logo的界面，光标一直在左上角闪烁。

1. 从`Windows安装光盘`引导启动，进入修复并开启命令行。
2. 用`dir`确定哪个是系统分区，在命令行下c分区的标识符即可能是c，也可能是d，这个需要当时分析。
3. 输入：`manage-bde -off d:`, 这条命令的作用是解密系统分区的解密。
4. 输入`manage-bde -status`, 查看解密的状态，当解密完成后重启。
5. 重启完成后进入`PE`, 修复系统引导和设置系统分区为当前激活分区。

参考链接: https://technet.microsoft.com/en-us/library/ee706522(v=ws.10).aspx