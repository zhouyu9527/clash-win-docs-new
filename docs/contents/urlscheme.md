# URL Scheme

## 下载配置

CFW 支持使用 URL Scheme 快速导入配置文件：

```
clash://install-config?url=<encoded URI>
```

### 响应头

如果响应头中存在`content-disposition`字段，则使用`filename`对应的值作为配置文件名，否则使用 URL 最后一部分作为配置文件名

如果响应头中存在`profile-update-interval`字段，则配置文件自动更新间隔设置为对应的值，以小时为单位

如果响应头中存在`subscription-userinfo`字段，则其对应的流量及到期信息会显示在 Profiles 模块中

## 退出软件

```
clash://quit
```
