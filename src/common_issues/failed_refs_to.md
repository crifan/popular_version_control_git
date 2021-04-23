# error failed to push some refs to

**背景**

在gitee上已经新建了git的repo仓库，且创建了一个README.md

而本地也新建了个git仓库，且加了内容：

```bash
git init
git add
git commit
```

然后去提交：

```bash
git push --set-upstream origin master
```

结果报错：

```bash
➜  youtubeSubtitle git:(master) ✗ git push –set-upstream origin master
To https://gitee.com/xxx/xxx.git
! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to ‘https://gitee.com/xxx/xxx.git‘
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: ‘git pull …’) before pushing again.
hint: See the ‘Note about fast-forwards’ in ‘git push –help’ for details.
```

**原因**：本地的内容，和远端仓库内容冲突了。

**解决办法**：如果像我此处一样，远端在线git仓库中内容是空的，被覆盖也无所谓的。则可以采用：强制上传本地内容到在线仓库

**操作步骤**：

```bash
git push -u origin master -f
```
