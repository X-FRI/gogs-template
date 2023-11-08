# The X-Files Research Institute Coding Space

## 当前状态

- [x] 开放注册
- [x] 用户创建组织
- [x] 用户仓库数量
- [x] SSH
- [x] Mirror interval
- [x] WebHook (gogs slack discord dingtalk)

欢迎，这里是X档案研究所内部的代码托管平台，基于Gogs提供简洁快速的git服务，用于：

- 内部开发
- 备份源码
- 学习研究

当前ip: [47.120.40.160](http://47.120.40.160)
- 有效期至 2024-03-07

如果你所见，直接使用ip并不是一个好的选择，我们建议在任何仓库的操作过程中使用固定的域名：`x-fri.club`

例如，你要为现有的仓库添加一个我们平台的remote, 应该使用:
```
git remote add xfri git@x-fri.club:用户/仓库
```

而不是:
```
git remote add xfri git@47.120.40.160:用户/仓库
```

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