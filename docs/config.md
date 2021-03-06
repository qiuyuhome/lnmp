# 软件配置

自定义软件配置是最重要的一项功能，为了方便本项目升级，严禁直接修改 `./config` 下的原始配置文件。

下面详细介绍如何正确的自定义配置。

## 原则

* 一般情况下使用默认配置即可，如果你需要修改某些配置，方便的话首先请在本项目 GitHub 提出 `issue`，提出优化配置的建议，之后按照本教程正确的自定义配置。

* 以追加方式配置文件

* 一个软件一个配置文件

## 总体步骤

**1.** 进入配置文件所在目录 `./config/SOFT_NAME/`

**2** 复制示例配置文件，并改名为 `*.my.*`。（`my` 只是标识符，你可以使用任意字符，例如 `self` `username` 等等）。

**3** 修改 `.env` 文件 `SOFT_NAME_CONF` 值为文件名或目录名（适用于 NGINX HTTPD）

## MySQL

**1** 示例配置文件：`./config/mysql/conf.d/docker.cnf`

**2** 在示例配置文件夹内 `./config/mysql/conf.d/` 复制 `docker.cnf` 为 `docker.my.cnf`

**3** 在 `.env` 文件内修改 `MYSQL_CONF` 变量值为 `docker.my.cnf`(默认是注释掉的，如果你按照本文方法操作，直接取消注释即可，或者修改为你自己认为合适的文件名)。

> MariaDB 配置差不多，这里不再赘述。

## NGINX HTTPD

这两个软件的配置文件较多，详细说明一下：

**1** 分清主配置文件和子配置文件，假设你已经知道这两个概念，如果你实在不知道，请在本项目 GitHub 提出 `issue`

**2** NGINX 主配置文件位于 `./config/etc/nginx/nginx.conf` HTTPD 主配置文件位于 `./config/etc/httpd/httpd.conf`

**3** 复制 `nginx.conf` 为 `nginx.my.conf` HTTPD 同理

**4** 在 `./config` 目录中新建 `nginx.my` 文件夹

**5** 建议通过 git 管理 `./config/nginx.my` 文件夹，我们以后就在 `nginx.my` 文件夹内新增 NGINX 子配置文件（参照 `nginx` 文件中的示例配置）

**6** 修改 `.env` 文件 `NGINX_CONF=nginx.my.conf` `NGINX_CONF_D=nginx.my`

## 其他软件

不再赘述，如果你还是实在不知道该怎么正确的自定义配置文件，请在本项目 GitHub 提出 `issue`。
