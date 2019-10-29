安装OpenCC实现繁体字转简体字
===

Open Chinese Convert (OpenCC, 开放中文转换)

中文简繁转换开源项目，支持词汇级别的转换、异体字转换和地区习惯用词转换（中国大陆、台湾、香港）。

https://github.com/BYVoid/OpenCC

* `s2t.json` Simplified Chinese to Traditional Chinese 简体到繁体
* `t2s.json` Traditional Chinese to Simplified Chinese 繁体到简体
* `s2tw.json` Simplified Chinese to Traditional Chinese (Taiwan Standard) 简体到台湾正体
* `tw2s.json` Traditional Chinese (Taiwan Standard) to Simplified Chinese 台湾正体到简体
* `s2hk.json` Simplified Chinese to Traditional Chinese (Hong Kong Standard) 简体到香港繁体（香港小学学习字词表标准）
* `hk2s.json` Traditional Chinese (Hong Kong Standard) to Simplified Chinese 香港繁体（香港小学学习字词表标准）到简体
* `s2twp.json` Simplified Chinese to Traditional Chinese (Taiwan Standard) with Taiwanese idiom 简体到繁体（台湾正体标准）并转换为台湾常用词汇
* `tw2sp.json` Traditional Chinese (Taiwan Standard) to Simplified Chinese with Mainland Chinese idiom 繁体（台湾正体标准）到简体并转换为中国大陆常用词汇
* `t2tw.json` Traditional Chinese (OpenCC Standard) to Taiwan Standard 繁体（OpenCC 标准）到台湾正体
* `t2hk.json` Traditional Chinese (OpenCC Standard) to Hong Kong Standard 繁体（OpenCC 标准）到香港繁体（香港小学学习字词表标准）


## Linux

install

```
git clone git@github.com:afterThirtyDev/Notes.git
cd OpenCC

sudo make
sudo make install
```

### Q&A:

- 执行 opencc --version后提示：opencc: error while loading shared libraries: libopencc.so.2: cannot open shared object file: No such file or directory

通过 [sudo]**find / -name libopencc.so.2** 找到libopencc.so.2的路径，设置软链接。

```
ln -s /usr/lib/libopencc.so.2 /usr/lib64/libopencc.so.2
```

## Mac

install

```
brew install opencc
```

## 使用

命令行转换文件(繁->简)
```
opencc -i /tmp/t -o /tmp/s -c t2s.json
```

