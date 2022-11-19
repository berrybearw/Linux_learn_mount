# Linux_learn_mount
mount 介紹

參考 : 

* [https://richarlin.tw/blog/linux-mount/](https://richarlin.tw/blog/linux-mount/)

* [https://unix.stackexchange.com/questions/30637/mount-error-is-not-a-block-device](https://unix.stackexchange.com/questions/30637/mount-error-is-not-a-block-device)

何時會需要此指令
---
1. 離線升級套件
2. 磁碟區共享
```
有時要更新一些 套件
會用 yum 等指令 
不過有時沒網路 或是 找不到更新包網站
這時可以用離線方式
離線需要準備 os 相關安裝光碟
把安裝光碟掛載到主機上 就可以使用
離線安裝套件
```

常用
---

`mount 來源磁碟目錄 要掛載到哪一個目錄`

轉移 mount 目錄
---

`mount --bind <olddir> <mountpoint>`

異常
---
`錯誤 : mount error "is not a block device"`

```
mount error "is not a block device"

mount 將包含文件系統的塊存儲設備附加到目錄，這不是您要嘗試執行的操作，因此會出現錯誤消息。您想要的是創建從新目錄名稱到舊現有名稱的鏈接

可以改使用 ln 或是 

移轉 : mount --bind <olddir> <mountpoint>

mount 與 ln 區別

如果需要目錄的用戶無法訪問它，或者磁盤不支持軟鏈接

掛載綁定很有用。綁定更強大，會更頻繁地工作。綁定工作是因為內核對應用程序“撒謊”，並告訴它一個目錄包含實際上在其他地方的內容。但是，除非您將綁定添加到/etc/fstab. 如果有疑問，我們ln -s- 它更容易，更靈活，不需要 root，會告訴您實際目錄在哪裡等。您通常不需要綁定
```

mount hang 住 , 卡住 ... 等 會造成甚麼影響
---
df 卡住大多是掛載磁碟異常 ( mount )

可以改使用 df -l ( 查看本地磁碟 )

查看掛載磁碟 mount | column -t

參考 : 
* https://www.gushiciku.cn/pl/pIst/zh-tw

取消掛載磁碟 umount 位置

umount /T100_gr

umount -f /T100_gr
