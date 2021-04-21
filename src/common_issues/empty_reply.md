# unable to access Empty reply from server

**问题**

在`git pull`或`git push`，报错：

```bash
fatal: unable to access Empty reply from server
```

**原因**

可能的原因有多种，比如网络断了等等。

此处遇到一种情况，其原因是：

当前git仓库是只允许**内网**访问，此处开启了代理，导致无法访问而报错

**解决办法**：去掉代理

**操作步骤**

* 清除git的本地代理
    ```bash
    git config --unset http.proxy
    ```
* 清除git的全局代理
    ```bash
    git config --global --unset http.proxy
    ```

> #### info:: 查看git代理
> * 查看git当前（本地）代理
    ```bash
    git config http.proxy
    ```
> * 查看git全局代理
    ```bash
    git config --global http.proxy
    ```
