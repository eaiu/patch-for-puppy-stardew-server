# patch-for-puppy-stardew-server

>[!important]
>
>修复的相关issue链接:
>1. [夏季地震之后无法等待host醒来]([https://github.com/truman-world/puppy-stardew-server/issues/14#issue-3619530443](https://github.com/truman-world/puppy-stardew-server/issues/14#issuecomment-3619771521))
>2. [节日活动无法正常参加](https://github.com/truman-world/puppy-stardew-server/issues/15#issue-3628806259)
>3. [熬夜到凌晨2点，所有加入晚间会触发自动休息，但是主机不会，导致整体卡住](https://github.com/truman-world/puppy-stardew-server/issues/17#issue-3663800001)
>
>！敬告：不知道对其他有什么影响，后果未知。

确实是对话框处理的问题，作者之前在v1.40添加了关于地震等 ReadyCheckDialog 对话框的判断，但不知道为什么没生效。

我简单修改了一下，把对话框的处理从关闭隐藏改为了点击确认，现在地震可以正常过。

后续：发现节日主机可以正常离开，凌晨两点晕倒也可以度过夜晚，还有意外收获😄

--- 

使用方法：
1. 找到volume的位置，一般和docker-compose.yml在同一目录下
```bash
cd ./data/game/Mods/AutoHideHost
```

2. 把`AutoHideHost/`目录下的`AutoHideHost.dll`替换为本项目的`AutoHideHost.dll`
3. 重新启动
```bash
docker compose down
docker compose up -d
```
