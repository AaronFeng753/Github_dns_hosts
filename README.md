# Github_dns_hosts
#### 一篇关于修复github图片加载问题的文章之备份
---
## 问题

最近一周时间内，突然发现 GitHub 上各种图片都无法加载，不仅仅是头像，包括各个仓库中的图片也是。开始以为是科学上网的问题，又或者是图片本身失效，可是验证下来都是无关的。

后来搜索了一下相关问题，目前来说可能是 DNS 被污染导致的。

## 解决方法

通过查看头像等文件的访问地址，了解到这些地址的域名都是 `githubusercontent.com`，然后通过[IP 地址查询](https://www.ipaddress.com/)可以找到其对应的 IP 地址，并将其相关二级域名一起配置到 Hosts 文件中去。

`Hosts` 文件中添加以下内容后，保存。
```sh
199.232.28.133 gist.githubusecontent.com
199.232.28.133 user-images.githubusercontent.com
199.232.28.133 raw.githubusercontent.com
199.232.28.133 camo.githubusercontent.com
199.232.28.133 cloud.githubusercontent.com
199.232.28.133 avatars0.githubusercontent.com
199.232.28.133 avatars1.githubusercontent.com
199.232.28.133 avatars2.githubusercontent.com
199.232.28.133 avatars3.githubusercontent.com
199.232.28.133 avatars4.githubusercontent.com
199.232.28.133 avatars5.githubusercontent.com
199.232.28.133 avatars6.githubusercontent.com
199.232.28.133 avatars7.githubusercontent.com
199.232.28.133 avatars8.githubusercontent.com
```

修改完成后，刷新页面，就恢复正常了。
