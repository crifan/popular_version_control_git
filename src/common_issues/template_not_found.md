# warning templates not found

**现象**：`Mac`中用`git`的工具`SourceTree`去clone下载代码，报错：

```bash
git -c filter.lfs.smudge= -c filter.lfs.required=false -c diff.mnemonicprefix=false -c core.quotepath=false -c credential.helper=sourcetree clone https://git.oschina.net/saicgroup/saicgroup_srt-ios.git /Users/minglong/saicgroup_srt-ios
Cloning into ‘/Users/minglong/saicgroup_srt-ios’…
warning: templates not found /usr/local/git/share/git-core/templates
error: RPC failed; HTTP 504 curl 22 The requested URL returned error: 504 Gateway Time-out
fatal: The remote end hung up unexpectedly
Completed with errors, see above
```

**原因**：相关目录不存在

**解决办法**：创建对应目录，且加上权限

**操作步骤**：

```bash
mkdir -p /usr/local/git/share/git-core/templates
sudo chmod -R 755 /usr/local/git/share/git-core/templates
```
