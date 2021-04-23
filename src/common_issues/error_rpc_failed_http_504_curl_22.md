# error RPC failed HTTP 504 curl 22

**现象**：Mac中用`SourceTree`去clone克隆代码结果出错：

```bash
git -c filter.lfs.smudge= -c filter.lfs.required=false -c diff.mnemonicprefix=false -c core.quotepath=false -c credential.helper=sourcetree clone https://git.oschina.net/saicgroup/saicgroup_srt-ios.git /Users/minglong/saicgroup_srt-ios
Cloning into ‘/Users/minglong/saicgroup_srt-ios’…
error: RPC failed; HTTP 504 curl 22 The requested URL returned error: 504 Gateway Time-out
fatal: The remote end hung up unexpectedly
Completed with errors, see above
```

**原因**：git代码仓库中有大文件，网络不够好，始终无法下载下来，所以报错

**解决办法**：跳过大文件，此处该大文件在历史旧版本中，最新版中没有大文件。所以可以用只下载当前最新版的方式实现跳过旧版本，从而跳过改大文件。

**操作步骤**：

```bash
git clone https://git.oschina.net/xxxxxxx/xxx.git --depth=1
```
