# 快连VPN相关问题
## 一.Mac，Windows上开启VPN但是访问不了bitmart.com?

1. Mac，Windows端开启了VPN，但是依然访问不上bitmart.com，提示链接失败或者提示禁止访问(denied)
   访问YouTube，NetFlix 看是否成功，如果不成功，说明vpn代理失败，请检查vpn是否欠费等。
   
![](./images/zh_41.png)


2. Mac，Windows端开启了VPN，访问YouTube正常，依然访问不上bitmart.com
   这说明你的vpn是正常工作的，但是bitmart.com没有经过代理。所以这时候你可以打开全局代理或者将bitmart.com加入到默认代理规则中。（不同vpn设置会有一些区别，但是功能是一样的）

![](./images/zh_42.png)


3. Mac，Windows端开启了VPN，访问YouTube正常，也开启了全局模式，还是访问不了 bitmart.com, 那是因为有些VPN只代理 IPv4，不代理 IPv6 (类似快连VPN) ，需要设置禁用ipv6

* 3.1 下面是不支持IPv6的VPN：

| 工具/VPN 名称                                | IPv6 代理支持      | 特点                  |
|------------------------------------------|----------------|---------------------|
| 快连VPN                                    | ❌ 不代理 IPv6     |                     | 国人常用，易泄露真实 IPv6 地址             |
| 蓝灯 Lantern                               | 	❌ 不代理 IPv6    | 	自动配置，兼容性好，但易漏 IPv6 |
| 赛风 Psiphon                               | 	❌ 不代理 IPv6    | 	类似蓝灯，注重“穿墙”，但非全局   |
| Turbo VPN（免费版）                           | 	❌ 不代理 IPv6    | 	手机上常见广告 VPN，风险高    |
| 一些浏览器插件类代理（如 SwitchyOmega 配 ShadowSocks） | 	❌ 默认不处理 IPv6	 | 需要手动设置或禁用 IPv6      |
| 大部分免费的 Shadowsocks 公共节点	                 | ❌ 默认不代理 IPv6	  | 如果服务端没配 IPv6，客户端直连  |

* 3.2下面是支持IPv6的VPN：

| 工具/框架                             | IPv6 代理支持         | 特点                            |
|-----------------------------------|-------------------|-------------------------------|
| Clash / Clash Verge / Clash Meta	 | ✅ 支持 IPv6 策略	     | 推荐配置 “tun 模式 + 阻断 IPv6” 或显式代理 |
| Shadowrocket（iOS）                 | 	✅ 可设置 IPv6 全局代理	 | 可选项中设置「代理 IPv6」或「阻止 IPv6」     |
| WireGuard	                        | ✅ 完美支持 IPv6	      | 安全、轻量、跨平台，需服务端配置支持            |
| V2Ray / Xray-core                 | 	✅ 可配置 IPv6 路由	   | 高级玩法，支持度强，但配置稍复杂              |

* 3.3 我都没有使用上面的VPN，我该如何检查是否遗漏 IPv6没有代理？
   打开这个网站测试：https://ipleak.net/
 
  ![](./images/zh_433.png)

如果你看到：

    - 一个是 VPN 的 IPv4 地址（如日本/香港）
    - 另一个是 你运营商真实 IPv6 地址（中国） → 说明你 VPN 没代理 IPv6，真实地址被泄了。

**如果IPv6没有代理的问题，可以参考这个视频来禁用IPv6，让电脑只使用IPv4： https://www.youtube.com/watch?v=G7ON-rCDDw8**


4. Mac，Windows，手机浏览器，不使用VPN是否可以访问BM官网吗？
不可以，需要使用VPN。


## 二.为什么在手机中点击邀请链接，会打不开或者提示网络连接失败、访问无效等
因为打开邀请链接是使用的手机浏览器，在app外访问还是需要开启vpn


