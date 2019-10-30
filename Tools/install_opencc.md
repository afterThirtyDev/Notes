安装OpenCC实现繁体字转简体字
===

Open Chinese Convert (OpenCC, 开放中文转换) [GitHub地址](https://github.com/BYVoid/OpenCC)

中文简繁转换开源项目，支持词汇级别的转换、异体字转换和地区习惯用词转换（中国大陆、台湾、香港）。

### 支持转换的配置
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
git clone https://github.com/BYVoid/OpenCC
cd OpenCC

sudo make
sudo make install
```

## Mac

install

```
# 使用brew安装，目录一般在/usr/local/Cellar/opencc/1.0.5/share/opencc/，代码调用时需要注意。
brew install opencc

# 手动安装，目录在/usr/local/share/opencc
make PREFIX=/usr/local
sudo make PREFIX=/usr/local install
```

## Q&A:

- 执行 opencc --version后提示：opencc: error while loading shared libraries: libopencc.so.2: cannot open shared object file: No such file or directory

通过 [sudo]**find / -name libopencc.so.2** 找到libopencc.so.2的路径，设置软链接。

```
ln -s /usr/lib/libopencc.so.2 /usr/lib64/libopencc.so.2
```

- 在make过程，报错：Doxygen is needed to build the documentation.  Please install it correctly

在mac中可以使用 **brew install doxygen** 安装

## 使用

命令行转换(繁->简)
```
#转换指定文字
echo "繁體到簡體" | opencc -c t2s

#转换指定文件
opencc -i /tmp/t -o /tmp/s -c t2s
```

