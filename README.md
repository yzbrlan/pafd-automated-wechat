⚠注意：最近 opencv 突然报错，已解决，更新代码即可。具体请看 [opencv-python突然更新无法识别验证码](https://github.com/FDUCSLG/pafd-automated/issues/20#issuecomment-1002902899)

因为 [Limour-dev/daily_fudan_core](https://github.com/Limour-dev/daily_fudan_core) 识别验证码非免费，
所以结合了两份代码，主要在 [FDUCSLG/pafd-automated](https://github.com/FDUCSLG/pafd-automated) 的基础上加入了 [Limour-dev/daily_fudan_core](https://github.com/Limour-dev/daily_fudan_core) 的微信消息推送的功能 

以下说明大部分归原作者 [daily_fudan](https://zhuanlan.zhihu.com/p/136340395) 和 [Limour-dev/daily_fudan_core](https://github.com/Limour-dev/daily_fudan_core) 所有，微信消息推送部分来自于 [Limour-dev/daily_fudan_core](https://github.com/Limour-dev/daily_fudan_core) 所有。

## 📐部署
<details>
<summary>查看教程</summary>

### 1. Fork 仓库代码
- 项目地址：[yzbrlan/pafd-automated-wechat](https://github.com/yzbrlan/pafd-automated-wechat)
- 点击右上角`Fork`到自己的账号下

![fork](https://i.loli.net/2020/10/28/qpXowZmIWeEUyrJ.png)

- 将仓库默认分支设置为 master 分支


### 2. 添加 账号密码 至 Secrets

- 回到项目页面，依次点击`Settings`-->`Secrets`-->`New secret`

![new-secret.png](https://i.loli.net/2020/10/28/sxTuBFtRvzSgUaA.png)

然后创建三个值
- secret 名字为 `STD_ID` 的在 Value 里填入 `学号`
- secret 名字为 `PASSWORD` 的在 Value 里填入 `UIS密码`。这里可以不用担心安全性问题，这些 scecrets 的值只有你能看见，此外因为背后是 GitHub 为你保障安全——GitHub 的安全性应该比复旦的 UIS 要高
- secret 名字为 `IYUU_TOKEN` 的在 Value 中填入 `token`，在 http://iyuu.cn/ 申请 `token` 

### 3. 启用 Actions

> Actions 默认为关闭状态，Fork 之后需要手动执行一次，若成功运行其才会激活。

返回项目主页面，点击上方的`Actions`，再点击左侧的`Go`，再点击`Run workflow`
    
![run](https://i.loli.net/2020/10/28/5ylvgdYf9BDMqAH.png)

</details>

至此，部署完毕。每天早晨十点会自动运行脚本帮你填写上一次的位置，微信公众号收到打卡的结果。
