# VPN指南

| 版本   | 更新人员         | 更新日期    |
| ---- | ------------ | ------- |
| 0.01 | Shichao Wang | 2016.10 |


## 不允许登陆，请与管理员联系

1. 打开`IE` -- `工具` -- `Internet 选项` -- `安全` -- `受信任的站点`
2. 点击`站点` -- 将**https://ras.renesas.com/login/china** 添加进去


## 会话已终止，是否重新连接

1. 查看是否有`百度系`的产品，包括： 浏览器，安全产品，杀毒软件..等等
2. 控制面板里卸载以上产品，然后去 `%userprofile%\appdata\local%`和`%ProgramData%`里删除`baidu`开头的目录
>  打开任意一个目录，将%userprofile%\appdata\local%拷贝至地址栏，然后回车即可打开对应目录，%programdata%也是相同原理
3. 控制面版里找到以`Pulse`开头的程序，一般来说是三个, 卸载之
   1. `Pulse secure host checker`
   2. `Pulse secure network connect 8.1`
   3. `Pulse secure setup client`
4. 重新登陆[VPN](https://ras.renesas.com/login/china) 

## 来自HQ给出的指南(英文)
> 如果上面的方法不能解决问题，可以尝试按照下面的步骤来解决

* Uninstall
   Start > Controll Panel > Programs and Functions
   Delete all of the applications that start with "Juniper" and "Pulse Secure"

* Related folders & delete files
   1) Remove the "C: \ Users \ [target user] \ AppData \ Roaming \ Juniper Networks" folder.
   2) Remove the "C: \ Program Files \ Juniper Networks" folder.
   3) Delete all files in the "C: \ Windows \ Downloaded Program"
     - Files that start with Juniper
     - Files that start with Smx
     - Files that start with Pulse Secure

* Delete Network Adaptor
   - Control Panel > Management Tool > Computer Management
   - Click the device manager, click "View" in Tool bar and enable "Show hidden devices".
   - Expand "network adaptor", right click the network adaptor which is not use, then choose uninstall or click properties and choose disable .
   Please UNINSTALL adaptors which start with Juniper Network and Pulse Secure. They will be reinstalled automatically.

* Delete Browse cache(Internet temporally file) and Cookie
   How to delete the cache and Cookie
   - Tools> Internet Options> "General" tab window
   - Click on the "Delete" button in Browsing history,
      Please put check "Temporary Internet file" and "Cookie", then delete them.

* Initialization of browser setting
   Tools -> Internet Options -> Click "Advanced" tab and "Reset" button.

* Entry in the "Trusted sites" of IE
   Please register the following 4 URL to Internet Options -> Security -> Trusted sites -> Site
 
  1. https://ras.renesas.com
  2. https://ras-jp.renesas.com
  3. https://ras-as.renesas.com
  4. https://ras-cn.renesas.com

* Restart Terminal
   Please restart the terminal and access to RAS again.

