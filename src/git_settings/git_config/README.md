# git的config

* git的配置
  * 配置类型有2种
    * 本地的
      * 对应文件：`.git/config`
        * 即当前`.git`目录下的`config`文件
      * 命令行设置方式：不加`--global`
        * 举例
          * 查看本地配置
            ```bash
            git config --list
            ```
          * 取消本地代理
            ```bash
            git config --unset http.proxy
            ```
            * 会把`.git/config`中的`http`的`proxy`部分删除掉
    * 全局的
      * 对应文件：`~/.gitconfig`
      * 命令行设置方式：加`--global`
      * 举例
        * 查看全局配置
          ```bash
          git config --global --list
          ```
        * 取消全局代理
          ```bash
          git config --global --unset http.proxy
          ```
          * 会把`~/.gitconfig`中的`http`的`proxy`部分删除掉
  * 生效关系
    * 优先级：**本地** > **全局**
      * 即：本地的配置会覆盖全局的配置
  * 配置的修改方式也有2种
    * 直接修改配置文件
      * 本地配置：修改`.git/config`
      * 全局配置：修改`~/.gitconfig`
    * 命令行方式设置参数
      * 添加代理
        * 添加本地代理
            ```bash
            git config http.proxy socks5://127.0.0.1:1086
            ```
        * 添加全局代理
            ```bash
            git config --global http.proxy socks5://127.0.0.1:1086
            ```
      * 取消代理
        * 取消本地代理
            ```bash
            git config --unset http.proxy
            ```
        * 取消全局代理
            ```bash
            git config --global --unset http.proxy
            ```

