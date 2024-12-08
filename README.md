# clash 规则

自己摸索规则
这个文件用于上传自定义规则和机场文件到 cdn 仓库里
因为是免费机场，每天流量有限额，所以采用黑名单模式。

## 黑名单模式 Rules 配置方式

1. 黑名单模式，意为「只有命中规则的网络流量，才使用代理」，适用于服务器线路网络质量不稳定或不够快，或服务器流量紧缺的用户。通常也是软路由用户、家庭网关用户的常用模式。
2. 以下配置中，除了 DIRECT 和 REJECT 是默认存在于 Clash 中的 policy（路由策略/流量处理策略），其余均为自定义 policy，对应配置文件中 proxies 或 proxy-groups 中的 name。如你直接使用下面的 rules 规则，则需要在 proxies 或 proxy-groups 中手动配置一个 name 为 PROXY 的 policy。

```yaml
rules:
  - RULE-SET,applications,DIRECT
  - DOMAIN,clash.razord.top,DIRECT
  - DOMAIN,yacd.haishan.me,DIRECT
  - RULE-SET,private,DIRECT
  - RULE-SET,reject,REJECT
  - RULE-SET,direct,DIRECT
  - RULE-SET,proxy,🚀 节点选择
  - RULE-SET,tld-not-cn,🚀 节点选择
  - RULE-SET,gfw,🚀 节点选择
  - RULE-SET,telegramcidr,🚀 节点选择
  - MATCH,🐟 漏网之鱼
```

## 规则连接

1.  [applications](https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/applications.txt)：需要直连的常见软件列表
2.  [private](https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/private.txt)：私有网络专用域名列表
3.  [reject](https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/reject.txt)：广告域名列表，拒绝访问
4.  [direct](https://cdn.jsdelivr.net/gh/txp1035/cdn@clash/direct.yaml)：自己填写需要直连的网站
5.  [proxy](https://cdn.jsdelivr.net/gh/txp1035/cdn@clash/proxy.yaml)：自己填写需要代理的网站
6.  [tld-not-cn](https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/tld-not-cn.txt)：非中国大陆使用的顶级域名列表
7.  [gfw](https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/gfw.txt)：GFWList 域名列表
8.  [telegramcidr](https://cdn.jsdelivr.net/gh/Loyalsoldier/clash-rules@release/telegramcidr.txt)：Telegram 使用的 IP 地址列表

## 参考

[GitHub - Loyalsoldier/clash-rules: 🦄️ 🎃 👻 Clash Premium 规则集(RULE-SET)，兼容 ClashX Pro、Clash for Windows 客户端。](https://github.com/Loyalsoldier/clash-rules?tab=readme-ov-file)
