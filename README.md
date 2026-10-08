# MyClash

Mihomo（Clash Meta）分流配置，开箱即用。

> 基于 [AIsouler/MyClash](https://github.com/AIsouler/MyClash) 二次修改，
> 核心改动：**AI 分组的规则集替换为 [viewer12/OverseasAI.list](https://github.com/viewer12/OverseasAI.list)**，
> 覆盖更全（OpenAI / Claude / Gemini / Copilot / Civitai 等 600+ 条规则）。

## 🚀 快速开始

把下面对应链接填进客户端的「订阅 / 配置 URL」即可（以 FlClash 为例：配置 → 新建 → URL 导入）。

| 版本 | 说明 | 订阅链接 |
|---|---|---|
| 全量版 | 完整分组：AI / 流媒体 / 游戏 / 电报 / 苹果 / 微软 / 谷歌等 | `https://raw.githubusercontent.com/wjj-bit-kriz/MyClash/main/Config/mihomoConfig.yaml` |
| 精简版 | 保留常用分组，体积更小，低内存设备友好 | `https://raw.githubusercontent.com/wjj-bit-kriz/MyClash/main/Config/mihomoConfigLite.yaml` |

> ⚠️ 导入后**必须**在配置里填入自己的机场订阅链接：
> 找到 `proxy-providers` → `provider1` → `url: ''`，把订阅链接填进单引号里。
> 如需添加第二个订阅，复制 `provider1` 整块改名为 `provider2` 即可（文件里有注释示例）。

## 🤖 AI 分组说明

AI 分组默认走「美国」节点（可在策略组里手动切换）。

| 项目 | 内容 |
|---|---|
| 规则源 | [viewer12/OverseasAI.list](https://github.com/viewer12/OverseasAI.list) |
| 规则数 | 约 618 条（DOMAIN 50 / DOMAIN-SUFFIX 553 / DOMAIN-KEYWORD 11 / IP-CIDR 2 / IP-ASN 2） |
| 更新频率 | 规则源每天更新，配置每天自动拉取（`interval: 86400`） |
| 覆盖范围 | OpenAI、Claude、Anthropic、Gemini、Copilot、Civitai，以及 Stripe、PayPal、Nvidia、JetBrains AI 等 |
| 技术细节 | `behavior: classical` + `format: text`（该规则集为混合类型文本规则，不能用原来的 `domain` / `mrs` 二进制格式） |

## 📱 在 FlClash 中使用

1. 侧边栏 → 配置 → 右上角 ＋ → **URL**，粘贴上面的订阅链接
2. 等待下载完成，点击设为当前配置
3. 点右上角 ✏️ 编辑配置，找到 `proxy-providers.provider1.url`，填入机场订阅链接后保存
4. 回到首页 → 代理 → 选择各分组节点（AI 分组默认美国，可按需切换）

其他 Mihomo 内核客户端（Clash Verge、NekoBox 等）同理：导入 URL → 填订阅 → 选节点。

## 🔄 与原版的区别

| | 原版 AIsouler/MyClash | 本仓库 |
|---|---|---|
| AI 规则集 | `category-ai-!cn.mrs`（geosite 二进制） | `OverseasAI.list`（classical 文本，规则更多更全） |
| 图标 | 原仓库 CDN | 沿用原仓库 CDN（稳定，暂不迁移） |
| 其余分组/规则 | — | 与原版一致 |

## 🙏 致谢与授权

- 配置框架：[AIsouler/MyClash](https://github.com/AIsouler/MyClash)（MIT License，原作者署名保留，见 [LICENSE](./LICENSE)）
- AI 规则集：[viewer12/OverseasAI.list](https://github.com/viewer12/OverseasAI.list)
- 其他规则源：[appshubcc/bett-rules](https://github.com/appshubcc/bett-rules)

本仓库同样以 MIT 协议发布，可自由使用、修改和分享。
