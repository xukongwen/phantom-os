# 一些tty模式下中文输入的设置


## 在纯tty下安装中文输入法

> sudo apt install --no-install-recommends fbterm fcitx-module-dbus dbus-x11 fcitx-fronten-fbterm fcitx-pinyin fonts-wqy-microhei
这一步是下载所有库，主要是可以显示中文的fbterm以及fcitx，正确显示中文的字体等等

> sudo setcap 'cap_sys_tty_config+ep' /usr/bin/fnterm
> sudo adduser $USER video
重启一下

> fcitx
这里第一次运行fcitx我是报错了，但是完全不影响使用。。。
> sudo vim ~/.config/fcitx/profile
这个是编辑fcitx的设置

> fcitx -r
重启fcitx
> fbterm -i fcitx-fbterm
启动fbterm，同时启动输入法

那么应该就成功了

> sudo vim ~/.fbtermrc
这里更改fbterm的字体之类的


## 提高tty颜色范围
将8颜色提高到256颜色
> export TERM=fbterm

## 改变fbterm下灰色字体为白色

> echo -ne "\e]P7ffffff"
