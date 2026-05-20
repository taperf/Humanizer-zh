# Humanizer-zh v3：中文 AI 写作去痕工具

> 基于 [blader/humanizer](https://github.com/blader/humanizer) v2.5.1 **重写适配中文**，不是简单翻译。

## 这是什么

一个 Claude Code / OpenCode / Hermes Agent Skill，用来去除中文文本中的 AI 生成痕迹。

AI 写的中文有固定模式。"赋能""助力""深耕""打造新范式"——你一眼就能认出来。这个 skill 教 LLM 识别并消除这些模式。

## 和旧版（翻译版）的区别

| | 旧版 v1.x | 新版 v3.0 |
|---|---|---|
| 方法 | 翻译英文原版 | 基于英文原版重写 |
| 规则 | 24 条，含多条"中文不适用" | 25 条，全部针对中文 |
| 词库 | 英文 AI 词汇翻译 | 中文特有 AI 高频词 |
| 示例 | 偏学术/百科 | 偏商业/通稿/PR |
| 体积 | 18.5 KB | ~10 KB（精简 45%） |
| 上游同步 | 停在 4 个月前 | 对齐 blader/humanizer v2.5.1 |

## 覆盖的模式

### 内容模式
1. 假大空拔高（"标志着""里程碑意义"）
2. 宣传体/广告体（"赋能""深耕""打造新生态"）
3. 模糊归因（"业内人士指出""专家表示"）
4. "着"结尾的虚假深度（"彰显着""见证着"）
5. 排比三段式
6. "不仅……更……"式否定排比

### 语言模式
7. 中文 AI 高频词（底层逻辑/抓手/赛道/闭环/颗粒度……）
8. 系动词回避（"作为……的重要组成部分"）
9. 公式化"挑战与展望"
10. 同义词循环

### 风格模式
11. 破折号滥用
12. 粗体滥用
13. 项目符号 + 粗体标题列表
14. 表情符号装饰
15. 口号式短句堆叠
16. 数字对称强迫症

### 交流模式
17. 谄媚/讨好语气
18. 协作对话痕迹
19. 知识截止免责声明

### 填充与回避
20. 填充短语
21. 过度限定/对冲
22. 空洞积极结尾
23. 假大范围
24. 被动语态滥用
25. 引述式开头

## 安装

### Claude Code

```bash
mkdir -p ~/.claude/skills/humanizer-zh
git clone https://github.com/taperf/Humanizer-zh.git ~/.claude/skills/humanizer-zh
```

### OpenCode

```bash
mkdir -p ~/.opencode/skills/humanizer-zh
git clone https://github.com/taperf/Humanizer-zh.git ~/.opencode/skills/humanizer-zh
```

### Hermes Agent

```bash
# 复制 SKILL.md 到 skills 目录
mkdir -p ~/.hermes/skills/humanizer-zh
cp SKILL.md ~/.hermes/skills/humanizer-zh/
```

### 手动安装

直接下载 [SKILL.md](./SKILL.md) 放到你的 AI 编程工具的 skills 目录即可。

## 使用

安装后，对你的 AI 助手说：

- "帮我 humanize 这段文字"
- "去掉这篇稿子的 AI 味"
- "用 humanizer 审一下这段"

## 示例

**改写前：**
> 在数字化转型浪潮席卷各行各业的大背景下，公司积极拥抱变革，深耕本地生活服务领域，通过持续的技术创新和模式升级，不断赋能生态合作伙伴。

**改写后：**
> 公司做本地生活服务，主要三块业务：到店团购、外卖到家、出行。给 600 万商户提供线上开店和运营工具。

## 致谢

- [blader/humanizer](https://github.com/blader/humanizer) — 英文原版（⭐ 19.8k）
- [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) — 参考其规则结构
- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — 底层知识来源

## License

MIT
