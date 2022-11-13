# Linux_learn_mount
mount 介紹

df 卡住大多是掛載磁碟異常 ( mount )

可以改使用 df -l ( 查看本地磁碟 )

查看掛載磁碟 mount | column -t

參考 : 
* https://www.gushiciku.cn/pl/pIst/zh-tw

取消掛載磁碟 umount 位置

umount /T100_gr

umount -f /T100_gr
