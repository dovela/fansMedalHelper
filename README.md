<p align="center">
  <img src="https://s1.ax1x.com/2022/05/24/XPx1tx.png" width="200" height="200" alt="">
</p>
<div align="center">
<h1> 新 B 站粉丝牌助手
</h1>

<p>当前版本：0.3.5</p>

 </div>

**TODO**

-   [x] 每日直播区签到
-   [x] 每日点赞 1 次直播间 （100 亲密度）
-   [x] 每日分享 1 次直播间 （100 亲密度）
-   [x] 每日弹幕打卡 
-   [x] 每日观看 65 分钟 （ 每5分钟100 共1300 亲密度）
-   [x] 每日应援团签到 (如果有的话) （10 亲密度）
-   [x] 多账号支持
-   [x] 微信推送通知
-   [x] 多平台推送通知（可选）

<small>ps: 新版 B 站粉丝牌的亲密度每一个牌子都将单独计算  </small>

---

### 使用说明

详细文档在这里 👉 [文档](https://xiaomiku01.github.io/fansMedalHelperVersion/)  
打不开的用这个镜像文档 👉 [镜像](https://doc.loveava.top/)  
**请细心阅读**

---

### 问题反馈

-   反馈交流群：979245756
-   提 issue
-   B 站私信 [晓小轩 iAVA](https://space.bilibili.com/1772442517)  
    **提之前请明确问题主题和运行日志**

---

### Docker

```
docker run -d \
  --name=fansMedalHelper \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Asia/Shanghai \
  -v /var/fansMedalHelperConfig/users.yaml:/fansMedalHelper/users.yaml \
  -v /etc/localtime:/etc/localtime \
  --restart no \
dovela/fansmedalhelper:latest
```

config文件默认挂载到主机`/var/fansMedalHelperConfig`下

主机还需要下载config至/var/fansMedalHelperConfig:

```
wget https://github.com/XiaoMiku01/fansMedalHelper/raw/master/users.yaml -O /var/fansMedalHelperConfig/users.yaml
```

config修改请参照上面原版文档

***容器已转为基于原作者仓库创建，未使用本项目文件***



### 定时运行
由于是docker，原版自带的定时器不能生效，这里使用cron来实现

`crontab -e`尾部追加

```shell
#分 时 天 月 周 这里每天5:10启动容器
10 5 * * * docker start fansMedalHelper 
```

---

### 友情链接

-   感谢 银弹 的 推送库 [y1ndan/onepush](https://github.com/y1ndan/onepush)
-   此脚本的 Go 语言实现版本 [ThreeCatsLoveFish/MedalHelper](https://github.com/ThreeCatsLoveFish/MedalHelper)
-   AW 的 B 站挂机助手 [andywang425/BLTH](https://github.com/andywang425/BLTH)

---  

###  本项目暂不接受任何 PR 如有问题或者新想法、功能可以通过 Issues 告诉我

### 赞助

<img src="http://i0.hdslb.com/bfs/album/c267037c9513b8e44bc6ec95dbf772ff0439dce6.jpg" width="500" />
