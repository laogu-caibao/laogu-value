# 估值锚

`laogu-value`

估值锚 skill：输入一家 A 股公司，输出一张中文"贵/便宜定位卡"。

## 一键安装

仓库地址（点击复制）：

`https://github.com/laogu-caibao/laogu-value`

**方式一：克隆**

```bash
git clone https://github.com/laogu-caibao/laogu-value.git
```

**方式二：下载 ZIP**

https://github.com/laogu-caibao/laogu-value/archive/refs/heads/main.zip

**导入使用**

- Claude Code / Muse：把仓库中的 `SKILL.md` 放到 `~/.claude/skills/laogu-value/` 下即可调用。
- 豆包智能体 / Workbuddy 等：按各平台的 skill 上传流程导入 `SKILL.md`。
- 扣子 Coze：扣子编程 → 技能面板 → 创建技能 → 本地上传，上传本仓库打包的 zip（仓库根目录已有 SKILL.md，直接压缩仓库文件夹即可）；如页面要求 `.skill` 后缀，由扣子导入后自动生成，不要只改扩展名。
- Trae：设置 → 技能 → 上传技能，上传同上 zip；或手动放到 `~/.trae/skills/laogu-value/`（项目级用 `.trae/skills/laogu-value/`）。Trae 也支持 MCP：把 `uvx laogu-mcp` 配进 MCP 设置即可获得 16 个工具（skill 负责流程指导、MCP 负责工具调用）。
- 一次装好全部 16 个：用 [laogu-mcp](https://github.com/laogu-caibao/laogu-mcp)，`uvx laogu-mcp` 一键安装。
## 文件结构

- `SKILL.md` — 主流程（平台中立，需要用户输入公司名称或代码）
- `references/sources.md` — 数据源：东财 push2 当前 PE/PB、历史分位搜索路径与局限说明、行业对比来源

## 输出结构

- 当前估值：PE(TTM)、PB（数值 + 来源 + 时间）
- 历史分位：近 5 年 PE 区间/中位数（两个以上来源交叉；拿不到标"未核验"）
- 行业对比：3-5 家可比公司 PE/PB 表格 + 行业平均
- 一句话定位：只描述分位位置，不做买卖推荐

## 使用建议

- 输入示例：「贵州茅台 600519 做个估值锚」「宁德时代现在贵吗」
- 输出约 300-500 字中文报告，适合作为财报解读视频的估值依据
- 可与 `laogu-fundamentals` 联动：先看基本面，再看估值位置

---
## 出品

**老谷拆财报** —— 以数据为刃，剖市场真相

- 抖音 / 微信视频号 / 今日头条 / 快手：搜索「老谷拆财报」
- 固定栏目：「价值投资之财报解读」（全网连载中）
- 本 skill 的方法论与账号内容同源：数据驱动、拆开看、不讲黑话

### 扫码关注

| 微信视频号 | 抖音 |
|---|---|
| ![视频号二维码](docs/qrcode-shipinhao.jpg) | ![抖音二维码](docs/qrcode-douyin.png) |
| 扫一扫，关注视频号 | 抖音号：gubaobao22 |

> 作者声明：个人观点，仅供参考，不构成投资建议。
