# 安装

你可以从 PyPI 安装：

```
$ pip install TA-Lib
```

或者自行检出源码并运行 ``setup.py``：

```
$ python setup.py install
```

### 安装错误排查

```
func.c:256:28: fatal error: ta-lib/ta_libc.h: 没有那个文件或目录
编译终止。
```

如果你遇到类似的构建错误，通常意味着找不到底层的 ``TA-Lib`` 库，需要先安装它：

# 依赖项
要使用 Python 的 TA-Lib，你需要已经安装了 [TA-Lib](https://ta-lib.org/hdr_dw.html)：

#### Mac OS X
```
$ brew install ta-lib
```

#### Windows
下载 [ta-lib-0.4.0-msvc.zip](https://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-msvc.zip)
并解压到 ``C:\ta-lib``

#### Linux
下载 [ta-lib-0.4.0-src.tar.gz](https://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz) 并执行：
```
$ tar zxvf ta-lib-0.4.0-src.tar.gz
$ cd ta-lib
$ ./configure --prefix=/usr
$ make
$ sudo make install
```

> 如果你使用 ``make -jX`` 来构建 ``TA-Lib``，它可能会失败，但这是正常的！
> 只需重新运行 ``make -jX``，然后运行 ``[sudo] make install``。

[文档目录](doc_index.md)
[FLOAT_RIGHT 下一步：使用函数 API](func.md)