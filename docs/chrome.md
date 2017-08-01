# Chrome指南

|版本|更新人员|更新日期|
|---|-------|-------|
|0.01|Shichao Wang|2017.07.17|
|0.02|Shichao Wang|2017.08.01|

## Chrome无法设为默认浏览器
1. 使用`默认程序`无法将Chrome和HTML格式关联起来
2. 进入`注册表`里修改
   ```` regedit
    1. regedit
    2. 选择至这里：计算机\HKEY_CLASSES_ROOT\.html和计算机\HKEY_CLASSES_ROOT\.htm
    3. 将上面两个项的默认的值修改为htmlfile
   ````
3. 再次尝试步骤一

## Chrome所有的页面崩溃
1. 进入 `C:\Windows\System32\drivers\`
2. 找到 `bd0001.sys,bd002.sys以及其他以bd开头的sys文件`
3. 将以上文件都重命名为类似这样的格式 `bd0001.txt`
4. 重启再打开chrome试试看
5. 我是参考的[这里](https://www.zhihu.com/question/29305453)的文章
