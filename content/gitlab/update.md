---
title: "Update Gitlab"
date: 2020-8-17T18:33:21+08:00
draft: false
tags: ["git", "gitlab"]
categories: ["gitlab"]
---

## Gitlab版本升级
公司目前gitlab版本是9.5.5,因升级服务器顺道把gitlab也升到最新,这里记录下历程。

### 备份Gitlab
```shell script
$ gitlab-rake gitlab:backup:create
```

执行命令进行备份，将会生成一个命名格式为<timestamp>_<date>_<gitlab-version>_gitlab_backup.tar的压缩包

### Gitlab升级
#### 升级历程: 9.5.5 -> 9.5.9 -> 9.5.10 -> 10.8.7 -> 11.11.8 -> 12.0.12 -> 12.10.14 -> 13.0.12 -> 13.2.3
[按照官网升级顺序依次升级](https://docs.gitlab.com/ee/policy/maintenance.html#upgrade-recommendations)

#### 下载deb包(*为版本号)
```shell script
$ wget https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/ubuntu/pool/xenial/main/g/gitlab-ce/gitlab-ce_*-ce.0_amd64.deb
```

#### 安装deb包
```shell script
$ dpkg -i *.deb
```

#### 查看版本
```shell script
$ cat /opt/gitlab/embedded/service/gitlab-rails/VERSION
```

## Gitlab恢复
首先关闭服务
```shell script
$ gitlab-rake gitlab:backup:restore BACKUP 1597233443_2020_08_12_9.3.1
```

## Gitlab 502解决(查看pid)
```shell script
$ gitlab-ctl status
```