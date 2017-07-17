# Windows update指南

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.03.30|

## error 0x80072ee2
1. 可能是网络问题,最初这个问题是出现在`SHDC1`上的
2. 将IE的代理从自动获取更改为`ChinaIDC`的地址

## error 0x80243004
1. 这个问题的解决方法真是很搞笑
2. 在任务栏的最右侧的通知区域中，单击`显示隐藏的图标` 按钮，然后单击`自定义`
3. 在通知区域的图标中找到`windows update` ， 并选择其通知方式为`显示图标和通知`
4. 重新打开`windows update` 检查更新，一般已经没问题了

## Windows update更新失败正在还原更改
1. `开始` - `运行` - `cmd` - `net stop wuauserv` - `回车`(先不要关闭shell窗口)
2. 打开`C:\Windows\SoftwareDistribution\Download`, 删除里面的所有的文件和目录
3. 在`cmd`的窗口中继续输入: `net start wuauserv`
4. 再次检测下`Windows update`


## 官方路数
1. 如果上面error都和你遇到的不对应, 或者都无效, 那就试试这个[链接](https://support.microsoft.com/en-us/instantanswers/512a5183-ffab-40c5-8a68-021e32467565/windows-update-troubleshooter)