# Ubuntu指南
|版本|更新人员|更新日期|
| ---- | ------------ | ------- |
| 0.01 | Shichao Wang | 2017.04.19 |

## 启动失败并进入*grub rescur>*

1. 执行下面的命令：
``` bash
    grub-rescue> ls  #可以看到很多的类似(hd0,msdos6)之类的
    grub-rescue> ls (hd0,6)/boot #根据上面的列出的找出boot在哪个分区，这个分区每个人的电脑并不相同，可能是(hd0,6), 也可能是(hd0,5)或者其他
    grub-rescue> ls (hd0,5)/boot #下面这个的ls的结果说明这个分区就是我们要找的
    # ... grub ... initrd.img-2.6.32-33-generic ... vmlinuz-2.6.32-33-generic
    grub-rescue> set boot=(hd0,5)
    grub-rescue> set prefix=(hd0,5)/boot/grub
    grub-rescue> insmod normal
    grub-rescue> normal
```

2. 启动后执行如下命令：
`sudo grub-install /dev/sda`

3. [参考链接](https://unix.stackexchange.com/questions/148041/recovering-from-grub-rescue-crash)