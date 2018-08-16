# Office installing & uninstalling

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.03.27|
|0.02|Shichao Wang|2018.08.16|

## Installing error 1935

1. 参考了[微软的支持](https://support.microsoft.com/en-us/kb/926804)和[问答页面的答案](http://answers.microsoft.com/en-us/office/forum/office_2010-office_install/error-1935-or-2908-when-installing-office-2010/99d5c577-49af-4e95-afba-f5af7061f50e)，问题是由 `.net framework` 没有安装引起的。
   
2. 点击[此处](https://www.microsoft.com/en-us/download/details.aspx?id=17718)下载`.net framwork` 并完成安装。

3. 尝试重新安装Office

## Uninstall office completely

1. Download Microsoft Fix-IT from: https://aka.ms/diag_officeuninstall
   
2. Run the “o15-ctrremove.diagcab”

3. Follow the Instructions on the screen to remove all Office Installations and Components


4. Restart Computer


5. After the required reboot check manually for any leftovers of “Microsoft Office” Folders under “C:\Program Files (x86)” and “C:\Program Files” delete the folders if found.
   
6. Retry installation via software center again. 
