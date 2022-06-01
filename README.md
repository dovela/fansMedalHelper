<p align="center">
  <img src="https://s1.ax1x.com/2022/05/24/XPx1tx.png" width="200" height="200" alt="">
</p>
<div align="center">
<h1> 新 B 站粉丝牌助手
</h1>
<p>当前版本：0.3.3</p>

 </div>

**TODO**

-   [x] 每日直播区签到
-   [x] 每日点赞 3 次直播间 （200\*3 亲密度）
-   [x] 每日分享 5 次直播间 （100\*5 亲密度）
-   [x] 每日弹幕打卡 （100 亲密度）
-   [x] 每日观看 30 分钟 （100 亲密度）
-   [x] 多账号支持
-   [x] 微信推送通知

<small>ps: 新版 B 站粉丝牌的亲密度每一个牌子都将单独计算  </small>

---

### 使用说明  

详细文档在这里 👉 [文档](https://xiaomiku01.github.io/fansMedalHelperVersion/)  
**请细心阅读**

---

### Docker

```
docker run -d \
  --name=fansMedalHelper \
  -e PUID=1000 \
  -e PGID=1000 \
  -e TZ=Asia/Shanghai \
  -v /var/fansMedalHelperConfig:/fansMedalHelper/config \
  --restart no \
docker.io/dovela/fansmedalhelper:latest
```

config文件默认挂载到主机`/var/fansMedalHelperConfig`下

主机还需要下载config至/var/fansMedalHelperConfig:

`wget https://github.com/dovela/fansMedalHelper/raw/master/config/users.yaml -O /var/fansMedalHelperConfig/users.yaml`

config修改请参照上面原版文档

### 定时运行
由于是docker，原版自带的定时器不能生效，这里使用cron来实现

`crontab -e`尾部追加

```shell
#分 时 天 月 周 这里每天5:10启动容器
10 5 * * * docker start fansMedalHelper 
```

---

### 问题反馈  
- docker问题提issue就行

---
### 赞助
（[原作者](https://github.com/XiaoMiku01)留）

<img src="http://i0.hdslb.com/bfs/album/c267037c9513b8e44bc6ec95dbf772ff0439dce6.jpg" width="500" />
