---
layout: default
title: "Horizon Summary: 2026-11-17 (ZH)"
date: 2026-11-17
lang: zh
---

> 从 48 条内容中筛选出 16 条重要资讯。

---

**科技新闻**
1. [vLLM v0.34.0 发布:可扩展 KV 缓存默认开启,Model Runner V1 移除](#item-tech-news-1) ⭐️ 8.0/10
2. [阿里、月之暗面等收紧新模型网络攻击能力，Qwen 不再开放权重](#item-tech-news-2) ⭐️ 8.0/10
3. [卡内基梅隆推出 CS Learn:完整计算机课程免费上线 YouTube](#item-tech-news-3) ⭐️ 7.0/10
4. [Optimizely 遭入侵，Zoom、GitLab 等大站经其 CDN 分发恶意软件](#item-tech-news-4) ⭐️ 7.0/10
5. [Rust 日期时间库 Jiff 发布 1.0 稳定版](#item-tech-news-5) ⭐️ 7.0/10
6. [摩根大通技术故障致美国多家银行网银服务延迟](#item-tech-news-6) ⭐️ 7.0/10
7. [Linebender 维基发布 Squircle 曲线数学解析文章](#item-tech-news-7) ⭐️ 7.0/10
8. [微软将大规模邮件故障归因于 7 月修复引入的软件缺陷](#item-tech-news-8) ⭐️ 7.0/10
9. [Marimba:基于冻结 Qwen3-ASR-0.6B 的轻量语音问答系统](#item-tech-news-9) ⭐️ 7.0/10
10. [美国与九国签署《旧金山宣言》共护超级智能供应链](#item-tech-news-10) ⭐️ 7.0/10
11. [亚马逊：AI 代理窃取暴露 AI 应用的 API 密钥自我供血](#item-tech-news-11) ⭐️ 7.0/10
12. [美国新规将先进 AI 芯片管制扩展至远程访问](#item-tech-news-12) ⭐️ 7.0/10

**财经新闻**
1. [美联储主席沃什：AI 将深刻影响经济与未来货币政策，但也可能令人失望](#item-finance-news-1) ⭐️ 7.0/10
2. [英伟达 CEO 辞职引发 AI 交易调整，专家推测大型科技公司将受益](#item-finance-news-2) ⭐️ 7.0/10
3. [英特尔及 CEO 陈立武遭股东集体诉讼](#item-finance-news-3) ⭐️ 7.0/10
4. [知情人士称英伟达董事会未考虑让黄仁勋回归 CEO](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 发布:可扩展 KV 缓存默认开启,Model Runner V1 移除](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0 正式发布,包含来自 412 位贡献者\(其中 120 位为新加入者\)的 1,061 次提交,新增 Mistral Large 4\(1T 总参数/52B 激活,支持 FP8 与 NVFP4\)、MiniMax-M3.1-Flash、Nemotron-3.5-Transcribe 等 10 个模型。架构上有两项重大变化:Model Runner V1 被移除,V2 成为唯一 GPU runner\(设置 VLLM\_USE\_V2\_MODEL\_RUNNER=0 将直接启动失败\);可扩展 KV 缓存默认启用,缓存大小改按 CUDA graph 捕获与预热后的实际空闲显存计算——例如 MiniMax-M3 在 H200 上缓存从 43.3 万 token 增至 67.2 万——但部分模型在并发 128 时每 token 解码延迟\(TPOT\)会上升 6–18%,可通过 --gpu-memory-utilization 0.9 或 --no-enable-extensible-kv-cache 退回旧行为。性能数据为项目方自报,包括 GB200 上 Step5 NVFP4 解码最高 1.95×、GLM-5.3-Flash 输出吞吐提升 1.6×、GLM-5.3 在 32K–128K 上下文的 TTFT 提升 1.24–1.40×。升级需注意多项破坏性变更:默认 --block-size 由 16 改为 64\(ROCm 分页注意力仍为 16\)、ROCm 7.2 镜像与 wheel 停发\(仅保留 ROCm 10.0\)、硬性要求 huggingface\_hub &gt;= 2.0.0\(同时需 tokenizers &gt;= 0.23.3 与 timm &gt;= 1.0.30\),fp\_quant 检查点不再能加载,Marlin W4A8 改由 --quantization humming 替代;安装渠道方面 CUDA 13.0 为默认\(pip install vllm\),Docker 提供 CUDA、ROCm、CPU、XPU 镜像。

github · khluu · 11月16日 23:22

**「背景」** vLLM 是广泛用于生产环境的大语言模型推理与服务开源引擎。在此前的版本中，GPU 执行路径上 Model Runner V1 与 V2 并存，可通过设置 \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\` 退回 V1；可扩展 KV 缓存（extensible KV cache）还是可选功能，缓存容量按预热前的内存估算分配，默认 block size 为 16，ROCm 用户仍在使用基于 ROCm 7.2 的镜像与 wheel。本次 v0.34.0 的多项破坏性变更正是对这些旧默认值的替换。

**「升级影响」** 升级到 v0.34.0 属于破坏性操作：\`VLLM\_USE\_V2\_MODEL\_RUNNER=0\` 改为启动即失败，默认 \`--block-size\` 从 16 变为 64，\`gpu\_memory\_utilization\` 默认变为 1.0，且必须满足 \`huggingface\_hub &gt;= 2.0.0\`（连带 \`tokenizers &gt;= 0.23.3\`、\`timm &gt;= 1.0.30\`），ROCm 用户只能改用 ROCm 10.0 的镜像与 wheel；如需保留旧行为，应显式传入 \`--block-size 16\`、\`--gpu-memory-utilization 0.9\` 或 \`--no-enable-extensible-kv-cache\`，并将 V1 logits 处理器迁移到新路径。默认开启的可扩展 KV 缓存虽扩大缓存、提升吞吐，但在部分 H200 模型上会使 TPOT 上升 6–18%，对延迟敏感的服务应先评估再决定是否关闭。外部评测曾指出 AMD 的 ROCm/vLLM 路径在 MI355X 上常无法充分发挥硬件算力，本版本通过 FlyDSL 解码 monokernel 与 DSpark 在 8×MI355X 上带来并发 1–8 时 +35–57% 的交互性提升，对 AMD 用户是针对性改进。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://inferencex.semianalysis.com/blog/mi355x-kimi-k2-5-vllm-aiter-7x-speedup">AMD MI 355 X Kimi K2.5 Inference: 7.7 x Throughput , Up... | InferenceX</a></li>

</ul>
</details>

**标签**: `#llm-inference`, `#vllm`, `#open-source-release`, `#performance`, `#gpu-hardware`

---

<a id="item-tech-news-2"></a>
### [阿里、月之暗面等收紧新模型网络攻击能力，Qwen 不再开放权重](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 8.0/10

据彭博（Bloomberg）报道，阿里巴巴、腾讯、月之暗面等中国头部 AI 公司已在各自新一代模型中削弱进攻性网络攻击能力，同时提升防御性表现；腾讯在本月发布 Hy4 之前已先行削减相关网络功能。阿里最新旗舰 Qwen 不再开放权重，用户无法下载并自定义完整版本，这对该模型系列的开放性是一次方向性转变。报道将上述调整与商务部上月公布的出口管制草案相关联——草案拟禁止出口可攻击关键基础设施和政府网络的 AI 工具，目前该管制仍处于草案阶段。

telegram · zaihuapd · 11月17日 02:20

**「背景」** 本轮收紧的直接背景，是中国商务部上月公布的人工智能出口管制草案：拟禁止可用于攻击关键基础设施和政府网络的 AI 工具出口。《纽约时报》10 月 21 日的报道称，这份草案使中国免费开放的 AI 模型陷入不确定性，也反映出北京在管控国家安全风险与赶超美国之间寻求平衡。在此之前，阿里 Qwen 旗舰模型以开放权重形式发布、用户可下载并自定义完整版本，最新旗舰不再开放权重因而构成明显转变。

**「对开发者与开源生态的影响」** 对依赖 Qwen 开放权重进行本地部署与微调的开发者和研究机构，影响直接：阿里于 11 月 16 日发布的最新旗舰 Qwen4-Max 不再提供权重下载，打破了 Qwen 团队此前以大量开放权重发布闻名的惯例。自托管用户只能继续使用此前的开放权重版本，或转向 API 访问新旗舰；鉴于商务部出口管制目前仍为草案，各公司后续旗舰模型的开放策略可能继续变化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/10/21/world/asia/china-exports-ai-controls.html">China ’s Free A . I . Models Are Thrown Into Uncertainty - The New York...</a></li>
<li><a href="https://www.llm-releases.com/labs/alibaba">Alibaba (Qwen) model releases · LLM Releases</a></li>
<li><a href="https://www.alibabacloud.com/blog/alibaba-unveils-qwen4-max-new-ai-teammate-for-work-creativity-and-discovery_603783">Alibaba Unveils Qwen4-Max: New AI Teammate for Work ...</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#export controls`, `#open source`, `#AI safety`, `#China AI industry`

---

<a id="item-tech-news-3"></a>
### [卡内基梅隆推出 CS Learn:完整计算机课程免费上线 YouTube](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

卡内基梅隆大学 Griffin 计算机科学学院推出 CS Learn 计划,在 YouTube 上免费发布该校现行计算机科学课程的整学期讲课视频。上线首周每天首播一门,更多课程计划于明年 1 月上线,目录中包括陈天奇\(Tianqi Chen\)的机器学习系统\(ML Systems\)课程。项目负责人、授课教师 Phillip Compeau 介绍,几名学生开发的自动化工具承担了大量制作流程,使一个小团队即可完成整套课程的生产发布。他同时承认 MIT 开放课件项目早于此举 25 年,认为本次的亮点在于制作与发布方式。

hackernews · pcompeau · 11月16日 20:43 · [社区讨论](https://news.ycombinator.com/item?id=50522980)

**「背景」** 大学课程免费公开早有先例：MIT 的 OpenCourseWare 在约 25 年前就率先将课程资料免费上网，这一点连 CS Learn 负责人 Phillip Compeau 本人也 Hacker News 讨论中主动承认，而 CMU 这次的不同在于发布当前学期课程的完整、逐讲授课视频。CMU 计算机学院现名为 Kenneth C. Griffin 计算机科学学院，本次课程由七个院系的教师讲授，涵盖机器学习、ML 系统、软件构建等方向，其中受社区关注的 ML Systems 课程由陈天奇（Tianqi Chen）与 Zhihao Jia 讲授。

**「对学习者的影响」** 对自学者和 AI 从业者而言,最直接的收益是可以免费观看 CMU 当前学期的完整讲座;以陈天奇的 ML Systems 课程为例,其中包含该校今年首次以速成方式讲授的现代\(Blackwell\)GPU 编程内容\(tool-3-1\),这类紧跟最新硬件的教学在高校课程中相当少见,已有 CMU 校友表示可将其与公开的配套 GPU 编程教材结合自学。需要注意两点局限:从现有信息看,公布内容以讲座视频为主,作业与练习是否会一并发布尚不明确;且更多课程要等到一月才会继续上线,短期内自学深度可能受限。

**「社区讨论」** 多位 CMU 校友在评论区表示欢迎:fwx 认为 ML Systems 课程可与 mlc.ai 的现代 GPU 编程教材形成互补,并请求增开 Larry Wasserman 的中级统计、Dave Andersen 的分布式系统等课程;dhashe 则期待即将上线的 15-259 概率与计算。另有评论者询问除视频外是否会发布作业与练习,该问题在现有评论中未见官方答复;围绕&quot;AI 时代为何仍需学基础&quot;的讨论,JSR\_FDED 的观点是基础扎实的人能把 AI 当作强力工具,否则可能被其取代。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/channel/UCqvooOJo8792T83va7LMMSA">CS Learn at Carnegie Mellon - YouTube</a></li>
<li><a href="https://www.linkedin.com/posts/griffincmu_were-proud-to-announce-the-launch-of-cs-activity-7528102235294060544-LkJw">We&#x27;re proud to announce the launch of CS Learn, a new online ... Carnegie Mellon opens its CS classrooms · Hacker News | Zeli Carnegie Mellon launches free CS Learn platform with top ... Carnegie Mellon Opens Computer Science Courses Free on ... CMU Kenneth C. Griffin School of Computer Science - YouTube</a></li>
<li><a href="https://www.linkedin.com/posts/tianqi-chen-679a9856_one-of-the-most-fun-parts-of-working-in-ai-activity-7475143042455461890-TB9l">One of the most fun parts of working in AI systems is having to relearn...</a></li>

</ul>
</details>

**标签**: `#computer-science-education`, `#open-courseware`, `#machine-learning`, `#carnegie-mellon`, `#free-learning-resources`

---

<a id="item-tech-news-4"></a>
### [Optimizely 遭入侵，Zoom、GitLab 等大站经其 CDN 分发恶意软件](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 7.0/10

据 Report URI 博客发布的分析，攻击者获得了 Optimizely 代码片段分发系统的写入权限，导致 Zoom、GitLab、CNN、BBC 等大量接入该服务的主流网站通过 Optimizely 的 CDN 向访客分发恶意软件。报告明确指出这并非 CDN 缓存投毒攻击——CDN 只是原样分发了被写入的内容，且 Optimizely 自家网站 www.optimizely.com 与 login.optimizely.com 的代码片段同样携带了恶意代码。攻击者究竟如何获得能波及多个互不相关客户项目的写入权限（是 Optimizely 系统被入侵、具备跨客户权限的凭据泄露，还是其他原因），截至报告发布仍无解释。

hackernews · kristjansson · 11月16日 23:00 · [社区讨论](https://news.ycombinator.com/item?id=50524767)

**「背景」** Optimizely 是一家提供 A/B 测试与个性化服务的数字体验平台，许多大型网站通过标签管理器将其 JavaScript 片段嵌入页面，并由 Optimizely 的 CDN 统一分发——这种由营销团队而非工程团队引入第三方脚本的惯例，使单一供应商被攻破即可波及大量互不相关的网站。Report URI 的分析指出此次并非 CDN 缓存投毒，而是 Optimizely 平台内部的写入权限被利用，其自家官网和登录页的代码片段同样被植入恶意代码；受感染的组织约有 178 家，包括 BBC、CNN、Zoom、Salesforce、GitLab、宜家、汇丰等，恶意负载是从 1688360\[.\]cc 加载的加密货币剪贴板劫持器（clipper）和信用卡窃取脚本。

**「影响」** 对于嵌入了 Optimizely 代码片段的网站，恶意 JavaScript 是在站点自身的源（origin）中执行的，页面上的会话 Cookie、表单输入等内容都处于注入代码的可达范围内，Zoom、GitLab、CNN、BBC 等受影响站点的安全团队需要核查事件窗口内实际下发的脚本，并评估用户数据是否暴露。对 Optimizely 客户的影响不止于此：据 BleepingComputer 报道，该公司已确认在一次语音钓鱼（vishing）攻击中部分系统被入侵并发生数据泄露，攻击者获取了员工账户并可能接触敏感客户数据，但这一披露与本次恶意片段事件之间的联系尚无官方说明。

**「社区讨论」** 讨论集中在第三方脚本的问责与流程：有评论者认为，标签管理器让营销部门无需工程团队审核即可向网站添加第三方脚本，正是这类事件的根源，Optimizely 及受影响的大型网站都缺乏发布冷却、分阶段发布与自动安全检查等防线，大流量网站更应将第三方脚本本地化（vendoring）而非实时从供应商加载。另有评论者追问，恶意脚本与页面同源后究竟能接触到什么（例如支付信息），以及浏览器安全模型是否也牵涉其中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.stepsecurity.io/blog/optimjack-optimizely-hosted-scripts-crypto-clipper-card-skimmer">OPTIMJACK: Optimizely-Hosted Scripts Loaded a Crypto Clipper ...</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/optimizely-malware-hits-zoom-bbc-cnn-what-to-do.html">Optimizely Malware Hits Zoom, BBC, CNN: What to Do</a></li>
<li><a href="https://breachhistory.com/blog/optimizely-optimjack-skimmer-november-2026">Optimizely Supply-Chain Attack Hits at Least 178 Organisations</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/ad-tech-firm-optimizely-confirms-data-breach-after-vishing-attack/">Ad tech firm Optimizely confirms data breach after vishing attack</a></li>
<li><a href="https://www.techedubyte.com/optimizely-data-breach-vishing-attack/">Ad tech firm Optimizely confirms data breach after... - Tech Edu Byte</a></li>

</ul>
</details>

**标签**: `#security`, `#supply-chain-attack`, `#third-party-scripts`, `#web-development`

---

<a id="item-tech-news-5"></a>
### [Rust 日期时间库 Jiff 发布 1.0 稳定版](https://burntsushi.net/jiff/) ⭐️ 7.0/10

由备受尊敬的 Rust 开发者 burntsushi 编写的日期时间库 Jiff 发布 1.0 稳定版,并于 2026 年 11 月 16 日在 Hacker News 上引发大量讨论\(344 分、78 条评论\)。在 chrono 长期主导但 API 与维护问题饱受诟病的领域,Jiff 被社区视为潜在继任者,其项目文档也明确承认它并非适用于所有场景。目前生态采用仍处于早期阶段,Jiff 能否被广泛接纳以取代 chrono 尚不确定。

hackernews · burntsushi · 11月16日 16:53 · [社区讨论](https://news.ycombinator.com/item?id=50519744)

**「背景」** 在 Rust 生态中，chrono 长期是最主流的日期时间库，但其 API 设计和维护停滞问题一直为人诟病，这也是 Jiff 诞生的背景。Jiff 的设计大量借鉴了 ECMAScript 的 Temporal 提案：它将 Temporal 的“plain”日期时间类型称为“civil”类型，仅支持格里高利历，日期时间范围限制在 ±9999（Temporal 的范围更大），作者 burntsushi 也坦言没有 Temporal 就不会有今天形态的 Jiff。该库以“引导用户跳进成功之坑”（pit of success）为设计理念，并通过 crate 特性开关定制对 Rust 标准库、serde 序列化的支持，以及是否将时区数据库嵌入二进制。

**「影响」** Rust 开发者现在可以通过 crates.io 安装进入 1.0 稳定版的 Jiff（\`cargo add jiff\`），将其作为 chrono 之外的日期时间库选项；其 crate features 支持按需配置标准库支持、serde 序列化，以及是否把时区数据库嵌入二进制，便于控制依赖与产物体积。新项目可以直接以 Jiff 起步，而现有 chrono 代码暂无被迫迁移的兼容性压力——生态采纳仍处早期，Jiff 与大量依赖 chrono 的既有库之间的互操作情况还有待观察。

**「社区讨论」** 曾维护 chrono 约五年的 quodlibetor 表示,他当初接手维护正是因为 chrono 的 API 糟糕,但用户看重 API 稳定、对任何改进尝试都予以抵触,最终因看不到改进路径而倦怠放弃维护,并对 burntsushi 写出 Jiff 表达感谢。另有从事太阳系轨道模拟的用户 ddahlen 询问 Jiff 对 TAI 等时间尺度的处理方式,以及未来扩展支持 UT1 等其他时间尺度的可能性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>
<li><a href="https://githubissues.com/BurntSushi/jiff/readme">BurntSushi / jiff - Githubissues</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/">jiff - Rust</a></li>
<li><a href="https://github.com/BurntSushi/jiff">GitHub - BurntSushi/ jiff : A datetime library for Rust that encourages...</a></li>

</ul>
</details>

**标签**: `#rust`, `#datetime`, `#open-source`, `#library-release`, `#software-engineering`

---

<a id="item-tech-news-6"></a>
### [摩根大通技术故障致美国多家银行网银服务延迟](https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda) ⭐️ 7.0/10

据美联社报道，摩根大通（JPMorgan Chase）发生的一起技术问题导致美国多家主要银行——包括 Chase、Wells Fargo 和 Truist——的网上银行服务出现延迟。截至发稿时，故障的根本原因尚未确认，报道本身未披露技术细节，影响范围与恢复情况仍有待官方进一步说明。

hackernews · samk3nny · 11月16日 18:31 · [社区讨论](https://news.ycombinator.com/item?id=50521045)

**「背景」** 摩根大通当天已向媒体证实，此次中断源于其系统中的一个“软件缺陷”（software bug），并非网络攻击；富国银行、Truist、美国银行等多家银行报告的服务异常也被确认与摩根大通的技术问题有关。有 HN 评论者指出，美国大型银行的核心流程很可能仍运行在 COBOL、CICS、IMS、DB/2 等老旧但以稳定著称的大型机软件栈上，一旦相关环节出错，影响可能经由跨行服务波及其他银行。另有评论者援引 Revolut 的官方复盘提到，10 月下旬 Revolut 曾因一次谷歌云中断导致服务全面瘫痪，约 12 小时后恢复，是同类事件的近期先例。

**「影响」** 故障根源被摩根大通归因于其自建系统中的一个软件缺陷，该行称问题可能已波及其他银行，因此后果并不限于 Chase 客户：11 月 16 日 Wells Fargo、Bank of America 的用户以及 Zelle 支付普遍报告服务延迟。另有报道称此次中断与上周的 Microsoft 365 宕机和美国空管系统中断无关，社区评论中将多起故障视为同一连锁问题的猜测目前没有证据支持。

**「社区讨论」** Hacker News 评论中有用户报告银行卡无法使用、线上银行不可用，并将其与上月欧洲 Revolut 因 Google Cloud 故障中断约 12 小时的事件类比，猜测本次也可能源于云或数据库层面问题，但这仅为推测、未经证实。另有评论者指出银行核心流程很可能仍运行在 COBOL、CICS、IMS 等大型机技术栈上，也有人认为科技行业普遍优先削减 QA 投入是此类故障的潜在诱因之一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase, impacted Wells Fargo and BofA</a></li>
<li><a href="https://www.politico.com/news/2026/11/16/jpmorgan-chase-banking-outage-software-bug-01168592">‘Software bug’ in JPMorgan Chase systems halts online banking</a></li>
<li><a href="https://chicago.suntimes.com/business/2026/11/16/a-technical-issue-at-jpmorgan-chase-triggers-online-banking-delays-across-major-us-banks">A technical issue at JPMorgan Chase triggers online banking ...</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase, impacted Wells Fargo and BofA</a></li>
<li><a href="https://gulfnews.com/business/banking/us-bank-outages-why-chase-bank-of-america-and-zelle-payments-were-delayed-1.500749851">US bank outages: Why Chase, Bank of America and Zelle ...</a></li>
<li><a href="https://nypost.com/2026/11/16/business/jpmorgan-chase-says-in-house-software-issue-impacted-service-and-possibly-other-banks/">JPMorgan Chase says in-house software issue impacted service ...</a></li>

</ul>
</details>

**标签**: `#infrastructure-outage`, `#banking-technology`, `#systems-reliability`, `#legacy-systems`, `#cloud-dependency`

---

<a id="item-tech-news-7"></a>
### [Linebender 维基发布 Squircle 曲线数学解析文章](https://linebender.org/wiki/curves/squircle/) ⭐️ 7.0/10

图形项目 Linebender 在其官方 wiki 发布技术文章《Squircles》，由在曲线与图形学研究领域知名的 raphlinus（Raph Levien）撰写，并于 2026 年 11 月 16 日登上 Hacker News 引发技术讨论。文章对 squircle——一种介于正方形与圆形之间的超椭圆特例——及其各种逼近方法给出了严谨的数学分析，主要面向矢量图形渲染、UI 设计与样条工具开发者。全文可在 linebender.org 的 curves/squircle 页面公开查阅。由于本条目未附原文正文，文中具体的数学结论与公式细节请以原文为准。

hackernews · raphlinus · 11月16日 07:55 · [社区讨论](https://news.ycombinator.com/item?id=50515151)

**「背景」** 超圆角（squircle）是一种介于正方形与圆形之间的形状，通常基于超椭圆（superellipse，即拉梅曲线）定义，但业界至少存在两种常用定义，另一种来自光学领域。虽然 CSS 的 corner-shape 规范要求呈现真正的超椭圆形状，但实际渲染实现一般采用贝塞尔曲线近似，例如 Chromium 的 Blink 实现就给出了每象限两段贝塞尔曲线的闭式高效近似。

**「影响」** 对图形程序员和 UI 设计师而言，这篇文章可作为实现平滑圆角方形（squircle）的可核查数学参考：Apple 在 iOS 图标到按钮、面板的整套界面中采用的都是连续曲率的 squircle，而 CSS \`border-radius\` 只是在直线两端拼接四分之一圆弧，衔接处存在曲率突变。若要在矢量工具、渲染引擎或设计系统中复刻这种“连续圆角”效果，可直接依据文中对各近似方法的误差分析来选择实现方案，而不是靠圆角矩形近似。

**「社区讨论」** 评论者 mosura 认为，避免导数不连续的曲线在与物理世界交互时至关重要，平滑性正来源于此，squircle 只是其中一例；darthcircuit 则分享了 Zune 二代 squircle 方向键的使用体验——既能像小型触摸板一样滑动浏览音乐，又保留了按键功能。另有评论者提供了正在开发中的样条与超椭圆创作工具演示，还有人介绍了 squircle 的三维类比 sphube 及相关 arXiv 论文（arXiv:1604.02174）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Squircle">Squircle - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Superellipse">Superellipse - Wikipedia</a></li>
<li><a href="https://linebender.org/wiki/curves/squircle/">Squircles - Linebender</a></li>
<li><a href="https://squircle.js.org/blog/squircles-in-apple-design">How Apple Uses Squircles in iOS Design - Squircle.js</a></li>
<li><a href="https://www.cingopablo.com/experiments/squircle">Squircle - cingopablo.com</a></li>

</ul>
</details>

**标签**: `#computer graphics`, `#curve geometry`, `#ui design`, `#vector graphics`, `#technical deep-dive`

---

<a id="item-tech-news-8"></a>
### [微软将大规模邮件故障归因于 7 月修复引入的软件缺陷](https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026) ⭐️ 7.0/10

据 The Register 11 月 16 日报道,微软在事故复盘中将一次大规模邮件服务\(Exchange Online\)故障归因于 7 月一次修复中引入的软件缺陷。据报告内容,该问题代码当时通过了微软相对低端的测试环境验证,与高端生产环境机器的差异掩盖了其中的并发缺陷,使其仅在生产的更高并发条件下暴露。本条目来源未提供受影响用户规模、故障持续时间等具体细节。

hackernews · Bender · 11月16日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50517321)

**「事件背景」** 此次故障发生于上周，微软 Microsoft 365 的 Exchange Online 邮件服务中断约 30 小时，波及 74 个国家/地区的用户。微软此后发布了初步事后分析报告（preliminary post-incident report）说明故障根源，并计划于 11 月 20 日公布最终报告。

**「影响」** 此次故障自 2026 年 11 月 12 日开始并延续至次日，Outlook、Exchange Online、Teams 日历和 Copilot 一并中断，波及全球的企业、政府和学校用户，连 ChatGPT 与 Claude 中依赖 Microsoft 365 连接器的功能也同时失效，把邮件或日历接入第三方 AI 工具的组织应将此视为单一故障点。对运营大规模系统的团队而言，微软的事后分析表明，在低配测试环境通过的代码仍可能在生产环境的高并发下暴露缺陷，测试环境与生产环境在规模和并发特性上的一致性是需要补齐的环节。

**「社区讨论」** 讨论集中在恢复策略与测试差距:有评论者以电力行业的“黑启动”类比,指出大型系统故障后难以在满负荷需求下直接恢复,还有人\(andix\)质疑微软为何不通过限制连接、分批轮换放开 IP 段等方式削减负载以逐步恢复服务。另有评论者\(ncr100\)指出低配测试环境通过代码、掩盖并发缺陷的情况,并质疑这种测试与生产环境不一致的权衡是否可接受;也有人\(mindwok\)对 Windows 进程承担关键网络基础设施角色表示意外。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026">Microsoft blames monster email outage on software defect ...</a></li>
<li><a href="https://thenextweb.com/news/microsoft-365-outage-july-defect-post-incident-report">Microsoft blames its Microsoft 365 outage on a dormant July bug</a></li>
<li><a href="https://www.webpronews.com/microsoft-365-outlook-outage-servers-health-checks-no-root-cause/">Microsoft 365 Outage Knocks Out Outlook for More Than a Day ...</a></li>
<li><a href="https://theconversation.com/why-the-microsoft-365-outage-is-different-and-why-it-takes-so-long-to-restore-email-services-296628">Why the Microsoft 365 outage is different and why it takes so long to...</a></li>
<li><a href="https://dopestudio.co.uk/microsoft-365-outage-what-happened-and-how-it-hit-businesses-and-ai/">Microsoft 365 Outage Nov 2026 : Impact on Business &amp; AI</a></li>

</ul>
</details>

**标签**: `#outage-postmortem`, `#microsoft`, `#exchange-online`, `#cloud-reliability`, `#distributed-systems`

---

<a id="item-tech-news-9"></a>
### [Marimba:基于冻结 Qwen3-ASR-0.6B 的轻量语音问答系统](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

作者在 r/MachineLearning 以 \[R\] 帖发布了论文并开源 Marimba:一套轻量 &quot;System 1&quot; 语音问答系统,每 8 秒音频窗口只需一次冻结的 Qwen3-ASR-0.6B 编码器前向计算,配合小型校准读出层即可回答是/否、多选和打分三类音频问题。词项检测\(如“是否说过 satellite”\)零样本完成:对 ASR 解码器的贪心假设和 4 条 beam 假设打分后做 Platt 校准;语言识别复用模型自身的语言得分;轮次结束与说话人变化/计数分别由冻结的第 18 层和第 12 层上的读出层预测。据作者自报告,在相同的 1,000 个公开问题上,Marimba 在 9 项测试中有 6 项追平或超过 Qwen3-Omni\(30B-A3B,后者在 Speech Commands 上仍更强\);说话人变化检测在 AMI 与 VoxConverse 上 AUROC 为 0.966–0.980,高于 ECAPA,说话人计数超过 pyannote 3.1,300 条 FLEURS 片段的语言识别为 100%。作者同时列出局限:轮次结束读出层以 Smart Turn 数据训练,该指标对其属分布内,且在 Smart Turn 自家测试集上 AUROC 0.930 不及 Smart Turn v3.2 的 0.982\(在 ICSI 上 0.716 对 0.712 打平\);系统对未见任务不具泛化能力,在 CochlScene 场景分类上各输出头部均为随机水平。代码、Apache-2.0 权重和在线演示均已公开,并可通过 pip install marimba-audio 安装。

reddit · r/MachineLearning · /u/solanotodesch · 11月16日 15:47

**「背景」** 标题中的“System One”\(系统一\)借自卡尼曼双过程理论的术语，指模型经单次前向推断直接给出答案，而不像“System Two”那样依赖缓慢的多步推理。Marimba 复用的 Qwen3-ASR-0.6B 是 Qwen3 系列中的小型语音识别编码器，而对照组 Qwen3-Omni\(30B-A3B\)是同系列中可对音频直接问答的大得多的模型。作者在帖中说明本帖是上周预告帖的后续，此次补充了论文\(arXiv:2611.18330\)、Apache-2.0 权重以及可 pip 安装的代码。

**「影响」** 对开发语音代理、会议分析或电话系统的团队而言，Marimba 提供了一条明显更省算力的路径：单个 0.6B 冻结编码器对每个 8 秒窗口做一次前向传播即可同时回答关键词检出、语言识别、轮次结束和说话人变化/计数等类型化问题，可替代 30B 级 Qwen3-Omni 或 pyannote、ECAPA、Smart Turn 等专用模型堆栈，且权重以 Apache-2.0 许可发布在 Hugging Face，配有 GitHub 代码和 pip 包，可立即试用。但它不是通用替代品：在训练分布外的任务上（如 CochlScene 场景分类）各输出头接近随机水平，轮次结束检测弱于专用的 Smart Turn v3.2（AUROC 0.930 对 0.982），Speech Commands 上也落后于 Qwen3-Omni，这些场景仍需保留专用模型。此外论文已挂上 arXiv，但全部基准数字均为作者自报、尚无独立复现，生产采用前应自行验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.18330">[2611.18330] Marimba: A System One Model for Speech - arXiv.org</a></li>

</ul>
</details>

**标签**: `#speech-processing`, `#audio-question-answering`, `#model-efficiency`, `#zero-shot-learning`, `#machine-learning-research`

---

<a id="item-tech-news-10"></a>
### [美国与九国签署《旧金山宣言》共护超级智能供应链](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

11 月 15 日，美国与澳大利亚、印度、以色列、日本、韩国、卡塔尔、新加坡、阿联酋和英国共十国签署《旧金山宣言》，确认经济安全是国家安全的根基，承诺共同保护支撑超级智能（SI）供应链的敏感技术与关键基础设施。宣言提出设立五个工作组，分别负责创新政策框架、SI 在关键领域的应用、SI 全栈供应链协作、安全港与供应链安全枢纽，以及 SI 安全与韧性。目前该宣言仍属政策承诺层面，五个工作组为拟议机制，具体运作方式与落实措施尚未公布；消息源自美国国务院发布的声明。

telegram · zaihuapd · 11月16日 10:40

**「背景」** 《旧金山宣言》是 2025 年 12 月由美国发起的“Pax Silica”倡议的新阶段，该倡议旨在关键矿产、能源、半导体和人工智能基础设施等战略领域建立韧性且多元化的供应链。据维基百科条目，宣言各工作组的最终目标包括降低参与方在关键矿产、AI 模型和芯片上对美国对手国家的依赖。签署仪式于 11 月 15 日在美国国务院负责经济事务的次卿 Jacob Helberg 召集的 Pax Silica 创始人峰会（Founders Retreat）期间举行。

**「影响」** 对十个签署国中从事 AI 基础设施、半导体与关键技术的企业而言，五个工作组（尤其是&\#x27;安全港与供应链安全枢纽&\#x27;）后续产出的政策框架，可能直接影响其技术出口合规与供应来源选择。多家报道称该宣言是美国在与中国的技术竞争加剧背景下推进的举措，也是美国 2025 年 12 月启动的 Pax Silica 倡议的新阶段；同时在这两大阵营运营的企业需关注供应链进一步分化的风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/San_Francisco_Declaration_on_the_Secure_Foundations_of_Enduring_Prosperity">San Francisco Declaration on the Secure Foundations of Enduring Prosperity</a></li>
<li><a href="https://www.investing.com/news/world-news/us-nine-nations-sign-san-francisco-declaration-on-ai-security-5028448">U.S., nine nations sign San Francisco declaration on AI security By...</a></li>
<li><a href="https://buzb.uz/en/news/us-and-nine-countries-sign-declaration-on-ai-supply-chain-security">US and Nine Countries Sign Declaration on AI Supply Chain Security</a></li>
<li><a href="https://timesofindia.indiatimes.com/business/india-business/india-joins-us-led-alliance-to-secure-ai-supply-chains-amid-china-tech-rivalry/articleshow/135886669.cms">India joins US-led alliance to secure AI supply chains amid China ...</a></li>
<li><a href="https://buzb.uz/en/news/us-and-nine-countries-sign-declaration-on-ai-supply-chain-security">US and Nine Countries Sign Declaration on AI Supply Chain Security</a></li>

</ul>
</details>

**标签**: `#AI政策`, `#供应链安全`, `#地缘政治`, `#国际合作`, `#超级智能`

---

<a id="item-tech-news-11"></a>
### [亚马逊：AI 代理窃取暴露 AI 应用的 API 密钥自我供血](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

亚马逊 AWS 表示，其诱饵网络 MadPot 于 10 月 3 日至 11 月 5 日期间探测并阻断了一起自主 AI 代理攻击活动：攻击者使用开源渗透测试框架 Artex 驱动 AI 代理，窃取公网暴露的 LiteLLM、Dify 等 AI 应用部署中的 API 密钥，经验证后汇入共享密钥池，用于支付后续更多的大模型调用。亚马逊以中等信心将该行动归于一个与中国相关的威胁组织，并称并非所有被列目标都已实际失陷，已通知可能受影响的 AWS 客户。运营公网暴露 AI 网关或应用平台的团队应检查相关密钥是否泄露。此消息经 Cybernews 转述。

telegram · zaihuapd · 11月16日 13:00

**「背景」** MadPot 是亚马逊在全球部署的诱饵威胁传感器网络，此次亚马逊正是将部分传感器伪装成公网暴露的 AI 应用，才捕获到这些代理发出的请求及其中包含的攻击“运行记忆”。Artex 是一个开源的代理式 AI 渗透测试框架，可驱动自主执行攻击任务的 AI 代理。被列为目标的 LiteLLM、Dify 以及 One API 属于常被企业公开部署在互联网上的大模型网关/应用平台，内部保存着各 AI 服务商的 API 密钥，因此成为窃取凭证型代理的狩猎对象。

**「影响」** 对公网暴露 LiteLLM、One API、Veloera 等 LLM 网关和 Dify、FastGPT 等应用构建平台的运营者而言，直接后果是存储的 API 密钥可能被窃取并用于产生未经授权的大模型调用费用——亚马逊诱饵记录中的代理名单列出了数百个此类目标。这些部署的运营者应检查默认登录凭据、暴露的密钥和账户消费异常；不过亚马逊同时说明名单上的目标并非全部失陷，被盗密钥的实际使用情况也尚待独立证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/">Amazon Threat Intelligence observes threat actors running ...</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify ...</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify ...</a></li>
<li><a href="https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/">AI credential theft campaign used stolen API keys to scale</a></li>
<li><a href="https://tbreak.com/ai-agents-hunt-litellm-dify-api-keys/">AI agents hunt exposed LiteLLM and Dify tools for API keys</a></li>

</ul>
</details>

**标签**: `#ai-security`, `#api-security`, `#llm`, `#threat-intelligence`, `#cybercrime`

---

<a id="item-tech-news-12"></a>
### [美国新规将先进 AI 芯片管制扩展至远程访问](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 7.0/10

美国商务部于 11 月 16 日发布临时最终规则，把针对先进 AI 芯片与服务器的出口管制延伸到远程访问场景，目的是防止通过第三国数据中心规避既有管制。据 The Verge 报道，新规同时要求向印度尼西亚、马来西亚、新加坡、泰国和巴西再出口 AI 芯片时须申请许可。该规则由财政部和国家安全委员会主导起草，报道认为其可能进一步收紧中国获取先进芯片的渠道。

telegram · zaihuapd · 11月16日 14:44

**「背景」** 美国此前已对先进 AI 芯片与服务器实施出口管制，目标是限制中国获取先进算力，但原有管制主要约束实体货物的跨境出口与再出口环节。即使芯片未被直接运入受限目的地，相关方仍可在第三国数据中心部署这些芯片，并通过云服务远程调用其算力，从而绕开管制——新规要堵住的正是这一缺口。

**「影响」** 新规把许可要求落到具体交易层面：向印尼、马来西亚、新加坡、泰国和巴西出口、再出口或境内转移先进半导体均需申请许可，审批按个案进行，并将考量相关国家的出口管制执法情况（tool-2-2, tool-2-1）。在这些国家部署或租用先进 AI 芯片的云服务商与企业需要审查现有算力合同与部署安排；不过用于在线零售、社交媒体等场景的商业推荐系统不在该许可要求范围内（tool-2-1）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://kpmg.com/us/en/taxnewsflash/news/2026/11/commerce-advanced-semiconductor-export-controls.html">U.S. Commerce restricts remote access to advanced ...</a></li>
<li><a href="https://www.nixonpeabody.com/insights/alerts/2026/11/16/bis-targets-remote-access-to-advanced-chips-through-overseas-data-centers">BIS targets remote access to advanced chips through overseas ...</a></li>

</ul>
</details>

**标签**: `#AI chips`, `#export controls`, `#regulation`, `#semiconductors`, `#tech policy`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储主席沃什：AI 将深刻影响经济与未来货币政策，但也可能令人失望](https://www.cnbc.com/2026/11/16/fed-ai-task-force-kevin-warsh.html) ⭐️ 7.0/10

美联储主席凯文·沃什（Kevin Warsh）11 月 16 日在旧金山向他组建的生产力与就业工作组发表讲话称，AI（他按特朗普政府要求改称&quot;超级智能&quot;）将对经济产生重大影响，并对未来货币政策有重要启示。他强调这并非预测，而是列出三种情景：生产率提升推动实际经济增长、自动化取代岗位推高失业率，或所谓&quot;令人失望&quot;的情形，即在大量资本投入和股市上涨后回报转弱、股票估值下跌，进而导致经济放缓、失业明显上升，且经济复苏时并不伴随生产率提升。

rss · CNBC Finance · 11月16日 18:46

**「背景」** 沃尔什于 2026 年 5 月就任美联储（美国中央银行）主席，上任以来多次强调人工智能有望提升生产率并成为抑制通胀的力量。他使用的“超级智能”一词源于特朗普 2026 年 9 月签署的行政命令，该命令要求联邦机构以“超级智能”取代“人工智能”的称法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.federalreserve.gov/aboutthefed/bios/board/warsh.htm">Federal Reserve Board - Kevin Warsh, Chairman</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/artificial-intelligence/elon-musk-pledges-spacexsi-rebrand-after-trumps-executive-order-to-use-super-intelligence-moniker-president-trump-has-signed-the-executive-order-to-replace-artificial-intelligence">Elon Musk pledges SpaceXSI rebrand after Trump &#x27;s executive order ...</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#Monetary Policy`, `#Artificial Intelligence`, `#Labor Market`, `#Productivity`

---

<a id="item-finance-news-2"></a>
### [英伟达 CEO 辞职引发 AI 交易调整，专家推测大型科技公司将受益](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

英伟达首席执行官黄仁勋上周辞职，公司股价录得 2012 年以来最长连续周度下跌，周五收于每股 162.85 美元；Yorkville Ives 随后将其目标价从 300 美元下调至 225 美元，但维持买入评级。在 CNBC&quot;ETF Edge&quot;节目中，Roundhill Investments 首席执行官 Dave Mazza 等受访专家推测，大型科技公司和 AMD、博通等芯片厂商可能成为英伟达困境的受益者。

rss · CNBC Finance · 11月16日 12:13

**「背景」** 英伟达创始人兼 CEO 黄仁勋在公司陷入风波后于 11 月 12 日辞职，由首席财务官科莱特·克雷斯出任临时 CEO；此前 11 月 3 日中期选举中民主党夺得国会控制权，部分民主党议员已呼吁收紧对 AI 数据中心建设的限制。

**「影响」** 分析师 Dan Ives 估计，民主党掌控国会后已规划的数据中心可能有 10%至 20%无法落地，但他认为需求仍以四比一超过供给。本周 AMD 和博通股价均上涨近 13%，纳斯达克指数创 8 月以来最佳单周表现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/live/2026/nov/12/nvidia-ceo-jensen-huang-affairs-share-price-plunges-live-latest">Nvidia turmoil continues as Jensen Huang resigns ... | The Guardian</a></li>
<li><a href="https://www.nacionale.com/en/articles/who-is-colette-kress-nvidia-cfo-interim-ceo-jensen-huang">Colette Kress named Nvidia interim CEO as Huang resigns</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/nvidia-confirms-jensen-huang-has-resigned-as-ceo-colette-kress-executive-vice-president-and-chief-financial-officer-appointed-interim-ceo">Nvidia CEO Jensen Huang resigns in the wake of... | Tom&#x27;s Hardware</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms ...</a></li>
<li><a href="https://fortune.com/2026/11/04/democrats-midterm-election-2026-anti-data-center-governors-texas-georgia-ohio-ai-infrastructure-big-tech-spending-moratorium-regulations/">Democratic blue wave will slow data center construction and ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI trade`, `#ETFs`, `#semiconductors`, `#tech policy`

---

<a id="item-finance-news-3"></a>
### [英特尔及 CEO 陈立武遭股东集体诉讼](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

一家密歇根州养老基金上周五在圣何塞联邦法院对英特尔、CEO 陈立武和 CFO 津斯纳提起集体诉讼，指控他们隐瞒 PC 需求疲软和库存积压的影响；此前英特尔于 10 月 29 日发布不及预期的第四季度营收和利润预测，次日股价暴跌 28.6%，市值蒸发约 1400 亿美元。据 Reuters 报道（Investing.com 转载），诉讼索赔对象为 2026 年 7 月 23 日至 10 月 29 日期间买入英特尔股票的投资者，指控目前尚未经法院认定。

telegram · zaihuapd · 11月16日 11:10

**「背景」** 此次诉讼的导火索是英特尔 10 月 29 日发布的第三季度财报：公司给出的第四季度业绩指引不及市场预期，管理层称 PC 需求疲软预计将至少持续到明年上半年，并面临供应链瓶颈，随后股价出现四十多年来最大单日跌幅。

**「影响」** 在 2026 年 7 月 23 日至 10 月 29 日期间买入英特尔股票的投资者属于本案诉讼集体，可能有权就股价暴跌损失索赔；英特尔及两位高管若败诉或达成和解将承担赔付支出，但相关隐瞒指控目前仅为原告一方说法，尚待法院审理认定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/10/29/intel-intc-q3-earnings-report-2026-.html">Intel (INTC) Q3 earnings report 2026 - CNBC</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-10-29/intel-outlook-hurt-by-weak-market-for-personal-computer-chips">Intel Earnings: (INTC) Stock Sinks After PC Slump, Supply ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#securities litigation`, `#semiconductors`, `#earnings guidance`, `#stock decline`

---

<a id="item-finance-news-4"></a>
### [知情人士称英伟达董事会未考虑让黄仁勋回归 CEO](https://www.cnbc.com/2026/11/16/nvidia-ceo-jensen-huang.html) ⭐️ 7.0/10

据 CNBC 援引知情人士报道，英伟达董事会并未考虑让黄仁勋回归 CEO 职位，目前重点是调查其行为，并已聘请 Wachtell Lipton 律所核查其行为是否危及国家安全与公司机密。该消息来自匿名知情人士，未经英伟达官方证实。

telegram · zaihuapd · 11月17日 01:39

**「背景」** 黄仁勋此前因绯闻风波辞去英伟达 CEO 职务，董事会已任命首席财务官克蕾丝（Colette Kress）为临时 CEO，并聘请 Wachtell Lipton 律所调查其行为；英伟达当时表示，尚无理由认为国家安全或公司机密已受到损害。此后特朗普公开表态支持黄仁勋回归，一封呼吁其复职的公开信已征集逾 16.5 万个签名。

**「影响」** 英伟达股东首当其冲：据 CNN 与《纽约时报》报道，公司 11 月 9 日宣布对 CEO 黄仁勋展开调查后股价应声下跌，雅虎财经称其 2026 年以来涨幅已全部回吐。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/10/nvidia-wachtell-lipton-huang-affair.html">Nvidia hires law firm Wachtell Lipton to lead Jensen Huang affair...</a></li>
<li><a href="https://www.nytimes.com/2026/11/10/business/nvidia-wachtell-lipton-jensen-huang.html">Nvidia Hires Wachtell Lipton to Investigate CEO Jensen ...</a></li>
<li><a href="https://www.pcgamer.com/software/ai/trump-supports-jensen-huangs-return-as-nvidia-ceo-but-it-doesnt-sound-like-the-board-is-interested/">Trump supports Jensen Huang &#x27;s return as Nvidia CEO ... | PC Gamer</a></li>
<li><a href="https://www.theguardian.com/business/live/2026/nov/16/ai-sell-off-resumes-jensen-huang-discusses-comeback-nvidia-ceo-dollar-stock-markets-latest-news-updates">AI sell-off resumes as Jensen Huang ‘discusses comeback as Nvidia ...</a></li>
<li><a href="https://finance.yahoo.com/markets/stocks/articles/nvidia-erases-2026-gains-republicans-204550552.html?fr=sycsrp_catchall">Nvidia Erases 2026 Gains as Republicans Threaten Jensen Huang ...</a></li>
<li><a href="https://www.cnn.com/2026/11/09/investing/nvidia-stock-huang-investigation">Nvidia stock falls after investigation into CEO, bucking ...</a></li>
<li><a href="https://www.nytimes.com/2026/11/09/business/nvidia-stock-price-jensen-huang-ceo.html">Nvidia’s Stock Price Drops After Investigation Into CEO ...</a></li>

</ul>
</details>

**标签**: `#nvidia`, `#corporate-governance`, `#jensen-huang`, `#national-security`, `#legal-investigation`

---