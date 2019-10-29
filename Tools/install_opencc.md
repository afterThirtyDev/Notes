安装OpenCC实现繁体字转简体字
===

## Linux

install

```
git clone git@github.com:afterThirtyDev/Notes.git
cd OpenCC

sudo make
sudo make install
```

Q&A:
---
- opencc: error while loading shared libraries: libopencc.so.2: cannot open shared object file: No such file or directory

通过 **find / -name libopencc.so.2** 找到libopencc.so.2的路径，设置软链接。

```
ln -s /usr/lib/libopencc.so.2 /usr/lib64/libopencc.so.2
```

## Mac

install

```
brew install opencc
```
