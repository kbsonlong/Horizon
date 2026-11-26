---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 36 条内容中筛选出 4 条重要资讯。

---

**科技新闻**
1. [Scott Aaronson 称 AI 揭示数学新大陆，矩阵乘法指数 9/4 结果待验证](#item-tech-news-1) ⭐️ 9.0/10
2. [OpenAI 押注网络安全，称其将成比编程更大业务板块](#item-tech-news-2) ⭐️ 7.0/10
3. [美国收紧芯片出口漏洞，亚洲数据中心争向美国客户转售算力](#item-tech-news-3) ⭐️ 7.0/10
4. [OpenAI 面向少量客户测试私有推理服务](#item-tech-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Scott Aaronson 称 AI 揭示数学新大陆，矩阵乘法指数 9/4 结果待验证](https://scottaaronson.blog/?p=10379) ⭐️ 9.0/10

11 月 25 日，理论计算机科学家 Scott Aaronson 发表博文宣称，AI 带来的将不再是针对个别复杂度问题的一次性解答，而是一整片此前只能隔着雾窥见的数学真理新大陆，并将其比作伽利略首次把望远镜对准星空、范·列文虎克首次用显微镜观察池水。这一讨论与一项据称把矩阵乘法指数定为 9/4（即 2.25，意味着 n×n 矩阵乘法可在 O\(n^2.25\) 时间内完成）的论文相关，该指数是算法理论中的长期公开问题，直接关系矩阵运算的渐近复杂度。但据关联的 Hacker News 讨论，该证明尚未完成验证，能否成立仍待确认；新大陆之说属于 Aaronson 的个人判断，而非已被独立证实的成果。

hackernews · Kotlopou · 11月25日 19:11 · [社区讨论](https://news.ycombinator.com/item?id=50646108)

**「背景：矩阵乘法指数 ω 与 OpenAI 预印本」** 矩阵乘法指数 ω 指的是计算两个 n×n 矩阵乘积所需运算量 O\(n^ω\) 中理论上可达到的最小指数，其精确值长期悬而未决，对它的追逐已持续约 57 年。这篇博文所回应的直接事件是：OpenAI 一个未公开名称的内部模型于 2026 年 11 月 24 日发布预印本，主张 ω 在任意域上都恰好等于 9/4。论文附有 Lean 形式化版本，已有外部作者将其与 LaTeX 原文对照，并在 M1 Max 上构建全部 592 个依赖模块以核对公理、陈述一致性与 leanchecker 验证，但该结果是否成立仍待完整的独立评审。

**「社区讨论」** 评论区最主要的分歧在于如何外推这一进展：nickysielicki 明确反对实验室已经攻破密码系统的流行猜测，理由是这些机构如今规模庞大，如此重大的秘密不可能长期无人泄密，而目前并无此类证据。Nevermark 则认为人类在演化上不具备对这种量级变化做出恰当反应的能力，因而会持续严重低估其影响；jsLavaGoat 同时提醒，AI 擅长公理化数学并不能推出它能解决其他学科或必然带来科幻式风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/openai-preprint-claims-matrix-multiplication-exponent-is-94">OpenAI preprint claims matrix multiplication exponent is 9/4</a></li>
<li><a href="https://lilting.ch/en/articles/matrix-multiplication-exponent-nine-fourths-openai">Checking OpenAI&#x27;s 9/4 Matrix Multiplication Exponent Paper ...</a></li>
<li><a href="https://geekblog.net/ai-software/openai-matrix-multiplication-exponent-9-4-proof-explained/">OpenAI&#x27;s 9/4 Matrix Multiplication Proof, Explained</a></li>

</ul>
</details>

**标签**: `#theoretical-computer-science`, `#matrix-multiplication`, `#artificial-intelligence`, `#algorithms`, `#mathematics`

---

<a id="item-tech-news-2"></a>
### [OpenAI 押注网络安全，称其将成比编程更大业务板块](https://www.theinformation.com/newsletters/ai-agenda/openais-roadmap-making-cyber-bigger-coding-remains-blurry) ⭐️ 7.0/10

据 The Information 报道（本条目为其中文转述），OpenAI 正将网络安全视为可能超过编程业务的下一个增长引擎：总裁格雷格·布罗克曼称网络安全将成为比编程更大的业务板块，CFO 则表示外界对网络安全市场超 3000 亿美元的估算仍被严重低估。具体动作上，公司已推出面向安全研究的 GPT-6 Cyber，并持续扩大网络安全受信访问计划 Daybreak——截至今年 9 月已覆盖数千名经核验的防御者及约 2000 个获批组织与工作空间，支持漏洞发现、代码库分析和二进制逆向。需要注意区分的是，“比编程更大”与市场规模判断属于 OpenAI 高管的前瞻表态而非已验证结果，报道同时指出其与 Anthropic、Google 的竞争态势及规模化商业化前景仍不清晰，且原始信源为付费通讯，相关数字无法从本条目独立核实。

telegram · zaihuapd · 11月25日 04:51

**「背景」** OpenAI 的安全布局并非从零开始：面向安全研究的 GPT-6 Cyber 模型与受信访问计划 Daybreak 均已上线运行。漏洞发现、代码库分析与二进制逆向这类能力因兼具被用于攻击的潜力，通常需要通过“受信访问”机制向经验证的防御者定向开放，而非像普通模型那样公开发布。此次高管表态的参照系是 OpenAI 现有的编程业务板块，这也是“网络安全将超过编程”这一说法的分量所在。

**标签**: `#OpenAI`, `#cybersecurity`, `#AI industry strategy`, `#LLM applications`, `#vulnerability research`

---

<a id="item-tech-news-3"></a>
### [美国收紧芯片出口漏洞，亚洲数据中心争向美国客户转售算力](https://www.bloomberg.com/news/articles/2026-11-25/asia-data-centers-sound-out-us-clients-to-replace-china-demand) ⭐️ 7.0/10

据彭博社 11 月 25 日报道，美国政府堵上了一项此前允许中国科技公司获取英伟达最先进 AI 芯片的漏洞，并针对向亚洲地区出口先进 AI 加速器出台新规。这些新规冲击了原本指望把算力出租给中国客户的亚洲多地数据中心服务商，后者目前正争相将过剩算力转售给美国买家。Liquid Compute 首席执行官 Ronit Jain 表示，针对该地区先进 AI 加速器出口的新规正在冲击这类数据中心业务。需要说明的是，本条为付费原文的简短转述，摘要中未提供新规的具体条款或转售交易的规模等细节。

telegram · zaihuapd · 11月25日 11:35

**「背景」** 此前，中国 AI 公司可以通过新加坡等第三国的云服务远程调用英伟达先进芯片，从而绕开美国出口管制，这一“云访问缺口”自 2026 年 8 月起引发美国立法者关注。为封堵该漏洞，美国商务部于 11 月 16 日发布临时最终规则，限制经第三国远程访问先进 AI 芯片，并要求东南亚数据中心在采购先进 AI 芯片前必须获得美方批准，直接威胁了当地原本大量依赖中国需求的算力建设扩张。

**「影响」** 新规使亚洲数据中心原本指望中国租户消化的大量先进算力面临闲置风险，运营商被迫紧急转向美国客户以填补需求缺口。市场已作出反应：管制公布后，东南亚数据中心及芯片供应链公司股价应声下跌，区域规模逾 1000 亿美元的 AI 产业受到威胁（tool-3-3）；新加坡、马来西亚等地的运营商今后向英伟达等美国厂商采购先进 AI 芯片需先申领许可证（tool-3-2），当地数据中心建设热潮可能因此放缓（tool-3-1）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/08/19/china-ai-nvidia-chips-us-export-controls.html">China AI firms tap Nvidia power overseas as U.S ... - CNBC</a></li>
<li><a href="https://www.forbes.com/sites/zacharyfolk/2026/11/16/us-closes-loophole-that-allowed-china-to-remotely-access-nvidia-chips/">US Closes Loophole That Allowed China To Remotely Access ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U.S. chip curbs put Southeast Asia&#x27;s data center ... - CNBC</a></li>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U.S. chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/asia-s-data-center-hotbed-hit-by-us-chip-curbs-as-trump-visits">Asia’s Data Center Hotbed Hit by US Chip Curbs as Trump ...</a></li>
<li><a href="https://www.reuters.com/world/asia-pacific/us-ai-chip-curbs-threaten-southeast-asia-data-centre-boom-shares-tumble-2026-11-17/">US AI chip curbs threaten Southeast Asia data centre boom ...</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#data centers`, `#compute market`, `#tech industry`

---

<a id="item-tech-news-4"></a>
### [OpenAI 面向少量客户测试私有推理服务](https://x.com/sama/status/2125638790593274259) ⭐️ 7.0/10

萨姆·奥尔特曼在 X 上发文宣布，OpenAI 正在与少量客户测试“私有推理”（Private Inference）服务，这是其 OpenAI Private Intelligence 系列的最新产品。据该帖子称，在零数据保留（ZDR）方案中启用“私有安全处理”（Private Safety Processing）后，安全审查可以自动完成，且 OpenAI 员工无法接触底层内容。奥尔特曼表示，更强的隐私保护将让前沿 AI 适用于更多工作场景，并称企业数据隐私对健康的产业生态很重要。需要注意，该能力目前仅处于小范围测试阶段，且只通过一条简短帖子披露，帖子未说明隐私保护与自动安全审查的具体技术机制、定价或正式上线时间。

telegram · zaihuapd · 11月26日 01:44

**「背景」** OpenAI 已于 2026 年 8 月 19 日宣布向符合条件的 API 客户提供前沿模型的零数据保留（ZDR）方案，并在同一公告中预告了“私有安全处理”（Private Safety Processing，PSP）。根据其开发者文档，ZDR 与 PSP 结合后可在不保留客户提示词及响应的前提下离线、自动完成安全审查，客户需自行承担相应的运维责任。

**「影响」** 对已符合零数据保留（ZDR）资格的企业 API 客户而言，关键变化在安全审查环节：ZDR 此前已允许合格组织在处理后不保留客户内容，而私有安全处理据外部报道可在多轮交互中自动完成安全监控且不暴露客户内容，使企业不必在数据隐私与滥用检测之间二选一。金融、医疗、法律等隐私敏感行业因此多了一条合规使用前沿模型的路径；有需求的企业可关注随该功能推出的技术白皮书并向 OpenAI 申请接入，但该服务目前仅面向少量测试客户、未披露技术实现细节，尚不应据此调整生产环境配置。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/offering-zero-data-retention-for-frontier-models/">Offering Zero Data Retention for frontier models - OpenAI</a></li>
<li><a href="https://developers.openai.com/api/docs/guides/private-safety-processing">ZDR with Private Safety Processing | OpenAI API</a></li>
<li><a href="https://www.linkedin.com/posts/paritosh-dagar-a5bb7119_offering-zero-data-retention-for-frontier-activity-7496138682236846082-KbVM">OpenAI Zero Data Retention for Enterprise AI Models | LinkedIn</a></li>
<li><a href="https://www.brocker.org/openai-previews-private-safety-processing-zero-data-retention">OpenAI Previews Private Safety Processing for ZDR Enterprise ...</a></li>
<li><a href="https://www.contentgrip.com/openai-zero-data-retention/">Can zero - retention AI still catch harmful use?</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#AI privacy`, `#enterprise AI`, `#zero data retention`, `#inference services`

---