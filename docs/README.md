# The X-Files Research Institute Coding Space

## 当前状态

- [x] 开放注册
- [x] 开放用户创建组织权限
- [x] 用户仓库数量: 不限
- [x] SSH
- [x] Migration
- [x] WebHook
- [x] Two-factor Authentication 

欢迎，这里是X档案研究所内部的代码托管平台，基于Gogs提供简洁快速的git服务，用于：

- 内部开发
- 备份源码
- 学习研究

当前ip: [8.134.192.36](http://8.134.192.36)
- 有效期至 2024-11-09

如果你所见，直接使用ip并不是一个好的选择，我们建议在任何仓库的操作过程中使用固定的域名：`x-fri.club`

例如，你要为现有的仓库添加一个我们平台的remote, 应该使用:
```
git remote add xfri git@x-fri.club:用户/仓库
```

而不是:
```
git remote add xfri git@8.134.192.36:用户/仓库
```

## SSH

平台禁止用户使用HTTP进行Push / Pull等远程操作，必须走SSH，配置方法为：`User -> Your Settings -> SSH Keys -> Add Key` 然后将你的SSH公钥复制粘贴并添加。

__Tips:__
- Linux下，SSH公钥一般在 `~/.ssh/id_rsa.pub`，如果不存在，则通过 `ssh-key-gen` 生成
- Windows下，SSH公钥一般在 `C:\Users\用户名/.ssh/id_rsa.pub`，如果不存在，则通过 `ssh-key-gen` 生成


## 备份

如果你只是想让自己的仓库有一份备份，可以通过在本地添加新的 remote url 来保持多个仓库同步，每次push, pull都会同步多个remote:

```
git remote set-url --add remote git@x-fri.club:用户/仓库
```

## 同步

上面说的备份也可以做到同步的功能，但如果你只是想让研究所的平台按时同步其他git平台的仓库，可以使用 Migration 功能， New Migration 时填写对应平台的仓库，账户和密码（也可能是token）后，勾选 `This repository will be a mirror`， 平台将会每个小时自动同步目标平台的仓库。

支持的平台:

- [x] Github
- [x] Gitee
- [x] Gitlab
- [x] Bitbucket
- [x] Sr.ht
- [x] Coding.net