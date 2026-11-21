---
layout: default
title: "Horizon Summary: 2026-11-21 (ZH)"
date: 2026-11-21
lang: zh
---

> 从 39 条内容中筛选出 17 条重要资讯。

---

**科技新闻**
1. [陶哲轩报告无外力纳维-斯托克斯奇性与广义黎曼猜想形式化证明](#item-tech-news-1) ⭐️ 10.0/10
2. [Anthropic 数学家称借 Claude 证明黎曼猜想，尚待验证](#item-tech-news-2) ⭐️ 9.0/10
3. [Thinking Machines 发布开源权重循环 Transformer 模型 Inkling 2 Mini](#item-tech-news-3) ⭐️ 8.0/10
4. [预印本声称证明无外力纳维–斯托克斯方程的有限时间爆破](#item-tech-news-4) ⭐️ 8.0/10
5. [KVM 漏洞 CVE-2026-99312 可让虚拟机读取 AMD 宿主机内存](#item-tech-news-5) ⭐️ 8.0/10
6. [台积电据报暂停中国客户 16nm 及以下制程订单](#item-tech-news-6) ⭐️ 8.0/10
7. [Masullo 仓促公开 940 页广义黎曼猜想证明草稿](#item-tech-news-7) ⭐️ 7.0/10
8. [论文称语言模型可凭自身推理改写自身权重](#item-tech-news-8) ⭐️ 7.0/10
9. [消息人士：美国 SEC 对英伟达的调查正审查潜在会计问题](#item-tech-news-9) ⭐️ 7.0/10
10. [Signal 采取措施阻止移动系统 AI 智能体截取私密聊天](#item-tech-news-10) ⭐️ 7.0/10
11. [Scott Aaronson 质疑「LLM 证明黎曼猜想」的说法](#item-tech-news-11) ⭐️ 7.0/10
12. [苹果被曝研发自主 AI 智能体，最早 2027 年末推出](#item-tech-news-12) ⭐️ 7.0/10
13. [OpenAI 后台模式上线：长任务异步执行，token 最多省 40%](#item-tech-news-13) ⭐️ 7.0/10

**科技博客**
1. [为什么缓存模型输出行不通](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [预测市场：标普 500 年内突破 8000 点概率从 72%骤降至 6%](#item-finance-news-1) ⭐️ 7.0/10
2. [美联储主席沃什拒绝提供利率前瞻指引，官员讲话量反而创 2025 年以来新高](#item-finance-news-2) ⭐️ 7.0/10
3. [美国企业由回购转为净增发股票，供给增加成牛市新阻力](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [陶哲轩报告无外力纳维-斯托克斯奇性与广义黎曼猜想形式化证明](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 10.0/10

陶哲轩于 11 月 20 日发布博客文章，报告了两项数学结果：无外力（unforced）纳维-斯托克斯方程的奇性，以及一个据称已在 Lean 中形式化的广义黎曼猜想证明。评论区引述 Lean Zulip 讨论称，两个相互独立的验证内核均接受了该黎曼证明，据此认为利用内核漏洞的可能性较低；据评论者引述，陶哲轩表示该证明&\#x27;似乎动用了朗兰兹纲领与算术几何现代进展的全部力量&\#x27;。本条目未附带原文正文，上述细节来自帖子分析摘要与社区评论，尚无法独立核实。

hackernews · archon1410 · 11月20日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=50578358)

**「背景」** Navier–Stokes 存在与光滑性问题是克雷数学研究所千禧年大奖难题之一，核心问题是三维不可压缩流体的光滑解是否会在有限时间内产生奇点；广义黎曼猜想（GRH）则是同属千禧年难题的黎曼猜想的推广。2026 年 9 月，OpenAI 内部系统曾发布一份声称解决该问题的证明，称流体动力学可在有限时间内形成奇点，并同步提供 Lean 形式化。Lean 等证明助手的形式化意味着证明可被机器内核逐步校验，而此次报告结果的关键推进在于给出“无外力”（unforced）情形下的爆破证明。

**「影响」** 若声明经核验成立，将同时触及克雷数学研究所七个千禧年大奖问题中的两个：未受迫 Navier–Stokes 奇点针对的正是此前仍无解答的“无外力”情形，也就是百万美元悬赏问题所问的核心情形；而广义黎曼猜想作为黎曼猜想（1859 年提出）的推广，其证明成立即涵盖后者。对数学界最直接的具体后果是验证路径的改变——Lean 形式化使证明可以被机器逐行核验，而无须依赖以年计的传统同行评审来确认正确性；在核验完成之前，社区对博客原文与形式化陈述是否一致仍需逐项检查。

**「社区讨论」** chunky1994 指向 Lean Zulip 讨论称两个独立内核均接受该结果，据此认为证明利用内核漏洞的可能性较低，而 softwaredoug 则质疑在既有抽象之上靠暴力生成加证明验证的路径，能否创造出&\#x27;朗兰兹纲领&\#x27;这样的全新抽象概念。此外，sega\_sai、actusual 等评论者表达了对 AI 超越人类智能的恐惧与自身职业的焦虑，这些属于个人感受而非已确立的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity, unforced Navier-Stokes ...</a></li>
<li><a href="https://www.alphaxiv.org/abs/2609.navier-stokes-solution">On the Navier–Stokes Millennium Prize Problem | alphaXiv</a></li>
<li><a href="https://conyso.com/lawtome/wild/unforced-navier-stokes-blow-up-alpoge-buckmaster/">Has the Navier-Stokes Problem Been Solved Without a Force?</a></li>
<li><a href="https://en.wikipedia.org/wiki/Millennium_Prize_Problems">Millennium Prize Problems - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier–Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://www.claymath.org/millennium-problems/">The Millennium Prize Problems - Clay Mathematics Institute</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#riemann-hypothesis`, `#navier-stokes`, `#formal-verification`, `#ai-research`

---

<a id="item-tech-news-2"></a>
### [Anthropic 数学家称借 Claude 证明黎曼猜想，尚待验证](https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/) ⭐️ 9.0/10

11 月 20 日，Anthropic 的数学家 Levent Alpöge 宣称在与 Claude 合作下证明了黎曼猜想，并表示该方法可直接推广至广义黎曼猜想，稍加时间还可覆盖扩展黎曼猜想。他称论证已用可验证数学正确性的语言 Lean 完成形式化并公开发布，文稿超过 25 万页。黎曼猜想由黎曼于 1859 年提出，涉及素数分布规律，是数学界最著名的未解难题。需要强调的是，这目前仍是一项未经独立验证的宣称，而非已被确认的成果。

telegram · zaihuapd · 11月20日 15:29

**「背景：黎曼猜想与 Lean 形式化验证」** 黎曼猜想由数学家黎曼于 1859 年提出，涉及素数分布的深层规律，160 多年来始终被视为数学界最著名的未解难题之一。此次证明所用的 Lean 是一种证明助手编程语言，能对证明中每一步论证的数学正确性进行机器检验，因此核验工作可由程序逐条完成，而不完全依赖传统的人工同行评审。

**「影响」** 证明已用 Lean 编码发布且作者称不含未证假设，因此数学界的验证工作从人工审读逾 25 万页文稿转为机械运行证明检查器、并核查形式化是否真正&quot;无假设&quot;，社区成员可下载已发布的代码自行复核。若验证通过，作为克雷数学研究所千禧年七大难题之一的黎曼猜想将告解决，且该证明实际针对适用范围更广的广义黎曼猜想，其成立除改进素数计数估计外，还会对许多其他算术函数的增长给出强界。

**「社区讨论」** Hacker News 上 djoldman 实测下载该 Lean 证明压缩包约 1.3GB、近 1500 万行代码；dawdler-purge 引用 MIT 的 Andrew Sutherland 页面（截至 2026-11-20 22:05 UTC，多项形式化检查仍在陆续运行）后认为证明正确性已无悬念，但这属于其个人判断。另有评论指出同日还出现了一份由 Alessandro Masullo 发布的纯人类广义黎曼猜想证明，z7 则引述 Terence Tao 一个月前“现有 AI 仍无法触及黎曼猜想”的说法，与本次宣称形成对照。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-167-year-old-riemann-hypothesis-claude">Claude helped prove 167-year-old Riemann hypothesis , researcher...</a></li>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.scientificamerican.com/article/what-the-riemann-hypothesis-proof-really-means-about-ai-and-the-future/">What the Riemann hypothesis proof really... | Scientific American</a></li>
<li><a href="https://www.claymath.org/millennium-problems/">The Millennium Prize Problems - Clay Mathematics Institute</a></li>

</ul>
</details>

**标签**: `#artificial-intelligence`, `#mathematics`, `#formal-verification`, `#large-language-models`, `#research-news`

---

<a id="item-tech-news-3"></a>
### [Thinking Machines 发布开源权重循环 Transformer 模型 Inkling 2 Mini](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines 发布了开源权重模型 Inkling 2 Mini，采用循环（looped）Transformer 架构，并以 nvfp4 量化端到端完成训练，面向本地运行场景。社区评论称其基准表现达到 Qwen3.8-27B 等更大模型的水平，但这些对比目前只是未经独立验证的第三方报告。据评论转述，团队在 Reddit 表示模型尺寸主要根据本地用户社区的需求确定。

hackernews · jasondavies · 11月20日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=50581260)

**「背景」** 循环变压器\(looped transformer\)是一种让模型中间层反复执行、从而在每个 token 上做更多计算而非写出更多 token 的架构;社区评论称,此前该架构主要出现在 GPT Astra、Sol 等闭源模型的传闻中,公开确认的案例很少。NVFP4 是一种 4 比特低精度浮点量化格式,而 Inkling 2 Mini 的特殊之处在于训练阶段就端到端使用该格式,推理时也依赖逐专家\(per-expert\)的 NVFP4 缩放。该模型为 26.4B 参数的 MoE\(每 token 激活 5.4B\),可在 32GB 内存的 Mac 上本地运行,需要带循环层支持的 llama.cpp 或 Unsloth 构建,并已进入 Ollama 模型库。

**「实际影响」** 对本地推理用户而言，该模型已可在消费级硬件上实际运行：有用户在 Ryzen 395 上通过 llama.cpp 的 Vulkan 后端测得约 27 tokens/s 的解码速度，另有用户在 32GB 内存的 M1 Pro MacBook 上以 q4 xl 量化获得约 10 tokens/s，并同时运行浏览器等其他程序。但最佳性能目前依赖尚未合并的 llama.cpp PR（32694、32657、32429、32704）以及社区提供的小补丁（可带来约 30% 提速），说明本地部署仍有兼容性门槛。

**「社区讨论」** 讨论焦点之一是该模型公开承认循环架构并开放权重的意义：有用户推测多数开源模型将随之转向循环架构，并担心这会带来安全与可解释性方面的新问题，但这属于个人观点而非事实。另有评论提醒基准结果仍需真实场景验证，而初步的本地编码测试反馈总体积极。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://unsloth.ai/docs/models/inkling-2-mini">Inkling 2 Mini - Run Locally Guide | Unsloth Documentation</a></li>
<li><a href="https://ollama.com/library/inkling-2-mini">inkling - 2 - mini</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#llm`, `#open-weights`, `#local-inference`, `#model-release`

---

<a id="item-tech-news-4"></a>
### [预印本声称证明无外力纳维–斯托克斯方程的有限时间爆破](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

11 月 20 日，一份发布在 GitHub 仓库 tristanbuckmaster/navier-stokes 的预印本声称证明了无外力（unforced）纳维–斯托克斯方程存在有限时间爆破的解。若该证明经同行评审与独立核验成立，将对克雷数学研究所千禧年大奖难题中的&quot;解的存在性与光滑性&quot;问题给出否定性答案。需要强调的是，这目前仅是以 GitHub 预印本形式发布的成果，并非已经验证的结论，千禧年问题级别的证明通常需要数年时间的检验。

hackernews · trotro · 11月20日 15:34 · [社区讨论](https://news.ycombinator.com/item?id=50576232)

**「背景」** 纳维–斯托克斯存在性与光滑性问题是克雷数学研究所千禧年大奖难题之一，问的是三维流体在没有外力作用、初始数据光滑的条件下，解是否始终保持光滑。据维基百科“纳维–斯托克斯优先权争议”条目，2026 年 9 月 8 日 OpenAI 曾就引入光滑外力的“受迫”版本提出解答，而 Tristan Buckmaster 在该公告前约 12 小时已代表本人并部分代表 Levent Alpöge 发表声明，由此产生优先权之争。本次由 NYU Courant 研究所教授 Buckmaster 与 Anthropic 数论学家 Alpöge 发布的 79 页论文，声称证明的是无外力情形下的有限时间爆破，即更贴近原始千禧年问题提法的“非受迫”版本，但目前仍属未经独立验证的预印本性质结果。

**「影响」** 若证明经得起核查，克雷数学研究所千禧年问题中“无外力纳维–斯托克斯方程是否存在整体光滑解”将以否定答案收场（解会在有限时间爆破），但该成果目前仅以 GitHub 预印本而非同行评审论文的形式发布，千禧年级别的证明按惯例需要数年核查，偏微分方程与流体力学研究者在正式评审或形式化验证完成前不宜将其当作既定结论引用。同日，Anthropic 数学家 Levent Alpöge 公开表示相信他与 Claude 已证明黎曼猜想并称已通过形式化验证，社区讨论称他也是本篇预印本的作者之一；两项千禧年级别声明同日出现且均待验证，其宣称的形式化验证做法也为本篇证明的核查提供了可参照的路径。

**「社区讨论」** 评论区最有价值的澄清来自 tancop：OpenAI 此前展示的是借助精心设计的外力使方程爆破的例子，而本预印本处理的是无外力版本，因而更贴近克雷原问题的设定。另有评论者 jrflo 认为 OpenAI 的&quot;抢发&quot;让 Buckmaster 与 Alpoge 失去了独立完成这一成果的机会，xianshou 则感叹同日还出现了广义黎曼猜想的声称——这些均属评论者个人观点，相关传言未经证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://officechai.com/ai/tristan-buckmaster-levent-alpoge-claim-proof-of-navier-stokes-millennium-prize-problem-without-forcing/">Tristan Buckmaster, Levent Alpöge Claim Proof Of Navier ...</a></li>
<li><a href="https://magica.com/news/alpoge-buckmaster-navier-stokes-unforced-blowup-claim">Alpöge and Buckmaster’s unverified Navier–Stokes claim | Magica</a></li>
<li>Anthropic mathematician claims AI-assisted proof of the Riemann ...</li>
<li>Anthropic mathematician claims Riemann hypothesis proof with ...</li>

</ul>
</details>

**标签**: `#mathematics`, `#navier-stokes`, `#fluid-dynamics`, `#millennium-prize-problems`, `#research`

---

<a id="item-tech-news-5"></a>
### [KVM 漏洞 CVE-2026-99312 可让虚拟机读取 AMD 宿主机内存](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

据 The Hacker News 报道，Linux 内核 KVM 曝出漏洞 CVE-2026-99312，仅影响启用了嵌套虚拟化的 AMD 主机，可让虚拟机读取宿主机物理内存。研究人员在 DigitalOcean 环境中演示从虚拟机内读取到约 127 GB 宿主内存。上游修复已于 11 月 18 日随稳定内核 7.3.5 等发布，但 Debian、Ubuntu 等发行版内核尚未跟进修补，补丁到位前可通过关闭嵌套虚拟化作为临时缓解。需要说明的是，本条目为 Telegram 转述的安全媒体报道，具体版本号等细节无法从条目本身独立核实。

telegram · zaihuapd · 11月20日 14:23

**「背景」** KVM\(Kernel-based Virtual Machine\)是 Linux 内核内置的管理程序，DigitalOcean 等云服务商普遍用它托管客户虚拟机；嵌套虚拟化则允许在虚拟机内部再运行虚拟机，本漏洞仅在 AMD 处理器且开启该功能的主机上触发。据 Red Hat 的 CVE 记录，漏洞成因是拥有嵌套客户机访问权限的攻击者可在内存分页被禁用时触发处理器复位仿真，使内存管理单元\(MMU\)进入不一致状态，从而越权访问宿主内存；Red Hat 因此将其评为中等\(Moderate\)影响等级。

**「影响与应对」** 该漏洞允许虚拟机内的 root 用户读取乃至写入宿主机内存，宿主机上其他虚拟机的数据与密钥因此面临泄露风险；由于利用前提是攻击者已控制一台启用了嵌套虚拟化的虚拟机，风险主要集中在多租户云环境与提供嵌套虚拟化服务的运营商。披露时各大发行版内核均未修补，所有未升级重启的 AMD KVM 宿主机持续暴露。管理员应立即检查宿主机是否启用嵌套虚拟化，不需要该功能的应在 Debian、Ubuntu 等发行版补丁到位并重启前将其关闭。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html">Linux KVM Flaw CVE-2026-99312 Lets Guest VMs Access Host ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99312">CVE-2026-99312 - Red Hat Customer Portal</a></li>
<li>Linux KVM CVE-2026-99312 Guest Escape: Patching and Hunting</li>
<li>CVE-2026-99312: Linux KVM Hypervisor Escape Exposes Host ...</li>
<li>Check These 4 Settings to See If Your AMD Servers Are Exposed to CVE ...</li>

</ul>
</details>

**标签**: `#virtualization`, `#security vulnerability`, `#Linux kernel`, `#AMD`, `#cloud security`

---

<a id="item-tech-news-6"></a>
### [台积电据报暂停中国客户 16nm 及以下制程订单](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

据 AppleInsider 报道\(经 Telegram 转引\),台积电已通知客户暂停中国企业的 16nm 及以下先进制程芯片订单,并表态将遵守新规。按收紧后的美国半导体出口新规,除非事先取得美国出口许可或豁免,否则不得对中国公司供货。目前已获美方批准的名单包括苹果、AMD 和英伟达,尚无中国公司上榜。由于该消息为二手转述,具体细则\(如制程门槛与许可机制\)尚无法独立核实。

telegram · zaihuapd · 11月21日 02:01

**「背景」** 此前台积电可自行评估客户的芯片设计是否符合美国出口豁免条件并自行决定供货;新规将这一流程改为须由客户提前向美方申请许可或豁免,实质上把豁免判定权从台积电收归美国出口管制当局。这一调整发生在美国持续收紧对华半导体出口管制的背景下。

**「影响」** 受影响的中国芯片设计公司只能退回 28nm、40nm 等成熟制程,并且无法获得 AI 数据中心所需的高带宽内存,先进 AI 硬件的代工与供应渠道因此被切断。仍需使用台积电先进制程的企业须提前向美国申请出口许可或豁免,而截至报道时没有任何中国公司获得批准,短期内获批前景不明。

**标签**: `#semiconductors`, `#export-controls`, `#TSMC`, `#US-China tech tensions`, `#AI hardware`

---

<a id="item-tech-news-7"></a>
### [Masullo 仓促公开 940 页广义黎曼猜想证明草稿](https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/) ⭐️ 7.0/10

11 月 20 日,数学家 Ravi Vakil 在博客上发表题为《仓促宣布》的帖子,称 Alessandro Masullo 提出了广义黎曼猜想\(GRH\)的一个证明并提前公开当前草稿——据 Hacker News 讨论中的描述,该手稿长达 940 页。据 Vakil 所述,Brian Conrad 已密切审阅数月并给出大量正在被吸收的反馈,证明“目前看来不错”,且全部由人工完成、未使用 AI。原计划是让 Masullo 到斯坦福访学一年打磨写作、经足够多人核验后再正式公布,如今因竞争性声明而提前放出草稿:源条目的相关链接指向 Levent Alpöge 声称证明 GRH 的讨论,评论中另提及 Anthropic 的公告。需要注意,这是一份未完成、未经独立核验的草稿——有评论者指出其开篇 1.1.1 节为空白——目前仅是优先权层面的声明,而非已被数学界接受的成果。

hackernews · jasondavies · 11月20日 18:33 · [社区讨论](https://news.ycombinator.com/item?id=50579568)

**「背景」** 广义黎曼猜想（GRH）是黎曼猜想在 L 函数零点与素数分布问题上的著名推广，长期被视为数学界最重要的未解难题之一。就在同一天（2026 年 11 月 20 日），Levent Alpöge 也发布了一份宣称证明 GRH 的工作，据外部报道其中一项声明与 Claude/Lean 形式化相关，这一消息正是促使 Ravi Vakil 决定提前公开 Masullo 草稿的直接诱因。Masullo 本人是 Brian Conrad 门下 2019 届斯坦福博士，且 Conrad 已对该证明审阅数月，这也是社区对其声明相对认真对待的原因。

**「影响」** 对数学界而言，直接后果是广义黎曼猜想的证明归属出现竞争：Masullo 的纯人工证明草稿与 Anthropic 数学家 Alpöge 声称借助 Claude 完成的证明目前均无独立验证，核查与优先权认定必须在两份材料均未完成审阅的情况下并行展开。此外，AI 辅助证明的发布节奏已开始压缩人类数学家传统的打磨与预审周期——Vakil 团队原计划让 Masullo 在斯坦福用一年时间润色文稿、征询足够多同行后再宣布，如今在 Alpöge 公告后改为提前释出尚未完成润色的草稿。

**「社区讨论」** 讨论中最核心的争论在于手稿状态与审阅者信誉的反差:有评论者指出 940 页的草稿开篇 1.1.1 节竟为空白,但同时强调长期审阅该证明的 Brian Conrad 并非“民科”\(该评论者据维基百科称其曾与 Andrew Wiles 就费马大定理有过合作\),并认为在当前环境下把一个 940 页的结果隐藏一年再发布“近乎疯狂”。另有评论者根据手稿中“研究该问题已 12 年”的表述,认为数小时内仓促发布是与 AI 公告争夺优先权、至少“打成平手”的唯一办法,并建议数学家今后定期发布带可验证时间戳的在研工作哈希以保留部分功劳。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://explainx.ai/blog/alessandro-masullo-grh-human-proof-claimed-vs-verified-november-2026">Masullo GRH Draft: What Vakil Announced (Nov 20) | explainx ...</a></li>
<li><a href="https://xenospectrum.com/en/masullo-riemann-proof-draft-release/">Draft Proof of the Generalized Riemann Hypothesis, 12 Years ...</a></li>
<li><a href="https://x.com/i/trending/2123859232806064131">Mathematician Claims Proof of Generalized Riemann Hypothe...</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis ...</a></li>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis ...</a></li>

</ul>
</details>

**标签**: `#mathematics`, `#generalized-riemann-hypothesis`, `#ai-capabilities`, `#proof-verification`, `#research-news`

---

<a id="item-tech-news-8"></a>
### [论文称语言模型可凭自身推理改写自身权重](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

arXiv 论文《Language Models Can Rewrite Their Own Weights》（编号 2611.21885）声称首次做到让语言模型不依赖梯度、不经训练，仅凭自身推理改写自身权重并变得更好：模型在练习题上测试各项权重修改、只保留有效的编辑且每次都在上一次的基础上改进，论文称其准确率在连续八个会话中只升不降。该论文于 2026 年 11 月 20 日被提交到 Hacker News 并引发大量讨论，但多位评论者质疑这种“自我改进”的实质与新颖性——有评论者指出模型真正有效的修改似乎只是缩短推理链以避开 token 上限，也有人认为 Google 的 Sleep 框架等先前工作已展示过相近能力。这目前是一篇论文的声称结果，尚无独立验证。

hackernews · lwhsiao · 11月20日 16:29 · [社区讨论](https://news.ycombinator.com/item?id=50577265)

**「背景」** 按照主流范式，语言模型一经训练完成即被冻结，此后要提升性能只能再进行一次训练，或在推理时借助提示词、外部挂载程序或额外计算——而这些手段随任务结束即告失效，本文正是声称提供了突破这一前提的“第三条路”。相关先行工作已经出现：Google 研究院于 2026 年 10 月发布的“睡眠框架”（Sleep framework）让模型在离线“睡眠”阶段解锁预分配的 MoE 记忆块，并利用自生成的练习样本更新数值权重，在保持核心设计不变的前提下持续吸收新知识；HN 评论者正是以此质疑该论文“首次实现自我改写”的定性。

**「社区讨论」** 围绕“自我改进”的成色存在明显分歧：aesthesia 指出模型唯一的自我改进只是缩短推理链以避开 token 上限，并称这与近期“权重空间编程”一文（发现模型没有明显缺陷可修时便无法被改进）的结论一致；gavinray 则认为 Google 的 Sleep 框架早已展示模型用自生成练习样本更新自身权重，质疑其新颖性。Toutouxc 争论称“在练习题上测试修改、只保留有效项并跨八个会话累积”本质上就是一种训练，与论文“无训练”的说法相悖；LarsDu88 则从 AI 安全角度警告，能自主改写权重的模型未来可能自行定位并抑制与安全对齐相关的激活。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.21885">[2611.21885] Language Models Can Rewrite Their Own Weights</a></li>
<li><a href="https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/">The sleep framework: A new way for LLMs to retain knowledge ...</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#language-models`, `#self-modification`, `#ai-safety`, `#research`

---

<a id="item-tech-news-9"></a>
### [消息人士：美国 SEC 对英伟达的调查正审查潜在会计问题](https://www.marketscreener.com/news/us-sec-s-nvidia-probe-is-examining-potential-accounting-issues-sources-say-ce785ed3dd8ff627) ⭐️ 7.0/10

据 MarketScreener 于 2026 年 11 月 20 日转引匿名消息人士的报道，美国证券交易委员会（SEC）对英伟达（Nvidia）的调查正在审查该公司可能存在的会计问题。该消息完全基于匿名消息人士的说法，目前没有任何调查结论或监管认定公布，属于调查处于审查阶段时的传闻，而非已证实事项。从本条目可见的信息看，调查针对的具体会计问题、时间范围及是否涉及特定交易尚不明确。

hackernews · ftchd · 11月20日 20:22 · [社区讨论](https://news.ycombinator.com/item?id=50581438)

**「背景」** 英伟达正处在领导层过渡期：2026 年 11 月 12 日，黄仁勋辞去总裁兼首席执行官职务，公司任命时任执行副总裁兼首席财务官的 Colette Kress 出任临时 CEO，直至找到正式继任者。由于此次 SEC 调查审查的正是潜在的会计问题，而 Kress 此前正是公司财务工作的主要负责人，临时 CEO 的任命因此与调查形成直接关联。

**「影响」** 最直接可见的后果在市场层面：路透报道传出后，英伟达股价延续创纪录抛售——雅虎财经称此轮下跌已抹去约 2.7 万亿美元市值。由于调查细节目前仅来自匿名消息人士、尚无结论，直接或通过指数基金间接持有英伟达股票的投资者，短期内仍可能随监管消息面剧烈波动；同时，这次会计调查叠加于英伟达已有的多起法律纠纷之上，其财务披露的可信度与合规风险成为投资者需要持续跟踪的问题。

**「社区讨论」** Hacker News 讨论中最集中的两条线索是：有评论者（eyeat）认为调查呼应了英伟达多年来与 neocloud（新兴云服务商）之间&quot;循环融资&quot;的争议，并称若公司按上次财报电话会的思路重新谈判用量协议，可能&quot;搬起石头砸自己的脚&quot;、加剧市场回调。另一条线索聚焦人事问责：多位评论者质疑，若存在会计问题，董事会为何任命 2013 年起担任 CFO 的 Colette Kress 出任临时 CEO，其中 treebeard901 认为财务部门很难对传闻中持续多年的黑市芯片销售入账毫不知情。以上均为评论者的观点与推测，并非已证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/12/nvidias-jensen-huang-resigns-chipmaker-names-cfo-colette-kress-as-interim-ceo/">Nvidia’s Jensen Huang resigns, chipmaker names CFO Colette ...</a></li>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition">NVIDIA Announces CEO Transition | NVIDIA Newsroom</a></li>
<li><a href="https://www.reuters.com/world/us-secs-nvidia-probe-is-examining-potential-accounting-issues-sources-say-2026-11-20/">Nvidia&#x27;s accounting is a focus of US SEC investigation ...</a></li>
<li><a href="https://finance.yahoo.com/markets/article/nvidia-stock-extends-25-trillion-rout-as-sec-probe-reportedly-investigates-its-accounting-194945274.html?fr=sycsrp_catchall">Nvidia stock extends $2.7 trillion rout as SEC probe ...</a></li>

</ul>
</details>

**标签**: `#nvidia`, `#sec`, `#regulation`, `#accounting`, `#ai-hardware`

---

<a id="item-tech-news-10"></a>
### [Signal 采取措施阻止移动系统 AI 智能体截取私密聊天](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal 在官方博客发布《Protecting Your Privacy》一文，说明了其为阻止移动操作系统平台内置 AI 智能体捕获用户 Signal 私聊数据而采取的防护措施。问题根源在于操作系统级 AI 助手可直接读取屏幕内容与设备上的应用数据，而单一应用对系统自带智能体的约束能力有限。上述措施属于 Signal 单方面公布的工程描述，具体技术机制、覆盖平台与兼容性影响以官方原文为准，目前尚无独立验证结果。

hackernews · dotcoma · 11月20日 09:42 · [社区讨论](https://news.ycombinator.com/item?id=50572348)

**「背景」** 随着苹果与谷歌把 Siri、Gemini 等 AI 助手深度集成到 iOS 和 Android 系统中，这些代理能够在设备端读取屏幕上显示的内容，从而与 Signal 这类端到端加密通讯应用所承诺的隐私保证形成直接冲突。Google 自己也已在新的 Gemini 隐私声明中提醒用户不要向 AI 提供个人信息，并披露了其所收集的信息范围，说明这一风险并非 Signal 单方面的担忧。

**「影响」** 对在移动设备上使用内置 AI 代理的用户，Signal 现已限制这些代理捕获或存储其 Signal 数据，端到端加密聊天因此不再默认暴露于设备端 AI 的读取范围。但这一防护属于应用层措施：系统级 AI 代理运行在操作系统层、位于单个应用之上并可跨整个软件栈执行操作，因此此类限制只能缩小而非消除暴露面。Signal 自己也将此举定位为针对代理“潜在捕获与存储”行为的防御性收紧，而非已证实的拦截能力；对隐私要求极高的用户和机构不应把它当作完整的安全边界。

**「社区讨论」** 讨论中最具分量的分歧在于应用层防护是否足够：有评论援引 Signal 总裁 Meredith Whittaker 在 Machine Gods 访谈中的说法称，即便用户自己不安装 AI 应用，联系人设备上的智能体仍可能泄露聊天内容，因此主张用户必须重新掌控操作系统本身（例如改用 GrapheneOS 或 Linux），单靠应用阻止截屏难以长久。另有用户报告新措施带来了副作用——Windows 端 Signal 聊天现在无法截屏；还有评论呼吁 Signal 公开其“取证调查”的结果并以协作文档形式维护，让资源较少的应用开发者也能从中受益。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your screen</a></li>
<li><a href="https://www.zdnet.com/article/dont-tell-your-ai-anything-personal-google-warns-in-new-gemini-privacy-notice/">Don&#x27;t tell your AI anything personal, Google warns in new... - ZDNET</a></li>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>
<li><a href="https://durapid.com/blog/how-os-level-ai-agents-will-fundamentally-change-enterprise-app-behaviour/">OS - Level AI Agents : How They&#x27;re Changing Enterprise Apps</a></li>

</ul>
</details>

**标签**: `#privacy`, `#security`, `#AI agents`, `#mobile operating systems`, `#encrypted messaging`

---

<a id="item-tech-news-11"></a>
### [Scott Aaronson 质疑「LLM 证明黎曼猜想」的说法](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

2026 年 11 月 20 日，计算复杂性学者 Scott Aaronson 在其博客发文，检视「一个 LLM 已经证明黎曼猜想」的说法；文章标题以「随机鹦鹉显然证明了黎曼猜想」的反讽口吻显示出质疑立场。原文具体内容无法从本条目直接核实，但 Hacker News 上的讨论表明，争议焦点包括该证明是否源于训练数据泄漏、如何验证机器生成的数学证明，以及人类能否理解这类证明。目前没有任何证据表明黎曼猜想已被真正证明，该文的价值在于对 AI 推理与验证局限的专家分析。

hackernews · stratos123 · 11月20日 20:03 · [社区讨论](https://news.ycombinator.com/item?id=50581084)

**「背景」** 黎曼猜想由数学家伯恩哈德·黎曼于 1859 年提出，断言素数在数轴上看似随机的分布实际上由一种精巧而有意义的秩序决定，长期被视为数学中最著名的未解难题之一 \[tool-1-1, tool-1-3\]。这一声明并非 AI 在该方向上的首次进展：据 Quanta 报道，2026 年 10 月已有 AI 证明了较弱的“拟黎曼猜想” \[tool-1-2\]；而本次引发讨论的，是 Anthropic 的 AI 数学家声称证明了完整的黎曼猜想 \[tool-1-1, tool-1-3\]，Scott Aaronson 的博客文章正是针对这一说法的检验。

**「对数学界的影响」** 对数学研究者而言，直接后果是骤增的验证与消化负担：据维基百科条目记载，OpenAI 已于 2026 年 10 月 6 日在 GitHub 一次性发布 722 份声称攻克多个重大未解难题的手稿，其中“准黎曼假设”（黎曼假设的较弱版本）的证明被斯坦福大学的 Jared Duker Lichtman 称为“迄今最重要的 AI 数学成果”。在此基础上，据 Scientific American 报道，独立数学家如今已“几乎确信”一份由 AI 生成的完整黎曼假设证明是真实的。数学家接下来需要以独立核查而非对模型输出的信任为准，逐份确认并吸收这批机器生成的结果——Quanta 在 10 月 19 日已以《接下来会怎样？》为题讨论数学界将如何应对这一局面。

**「社区讨论」** 评论者 janalsncm 以 Stockfish 象棋引擎作类比，认为 AI 给出的「解释」只是大量计算的聚合，难以满足人类对「为什么」的追问；jstummbillig 则担忧人类在科学与工程领域将日益无法理解机器产出并失去实质贡献能力。另有评论者引用文中「我们仍应修复泄漏」的说法（alterom），认为这一结论适用于数据泄漏之外更广泛的场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/">AI Proved the Quasi- Riemann Hypothesis . | Quanta Magazine</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenAI_bulk_release_of_mathematical_papers">OpenAI bulk release of mathematical papers - Wikipedia</a></li>
<li><a href="https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/">AI Proved the Quasi-Riemann Hypothesis. What Happens Now?</a></li>
<li><a href="https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/">The AI Riemann hypothesis proof is almost certainly true ...</a></li>

</ul>
</details>

**标签**: `#artificial intelligence`, `#llm-reasoning`, `#mathematics`, `#riemann-hypothesis`, `#interpretability`

---

<a id="item-tech-news-12"></a>
### [苹果被曝研发自主 AI 智能体，最早 2027 年末推出](https://www.bloomberg.com/news/articles/2026-11-19/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding) ⭐️ 7.0/10

据彭博（Bloomberg）从苹果本周新增招聘信息中获得的报道，苹果正在招募高级工程经理，主导开发一款可代用户编写代码、浏览网页和操控应用的「主动式 AI 智能体」，最早 2027 年末推出，但项目仍处于早期阶段，目前属于计划而非已发布能力。与此同时，一个已经落地的变化是：苹果在 macOS 27.3 中加入警告页，第三方智能体获取 Mac 控制权限的步骤由 4 步增至 14 步，显著提高了竞争对手智能体的使用摩擦。报道称 Meta 的 Muse 和 OpenAI 等公司已推出同类智能体，苹果在此领域处于追赶位置。

telegram · zaihuapd · 11月20日 08:59

**「背景」** 「AI 智能体」指能代表用户自主完成写代码、浏览网页、操控应用等任务的软件，Meta 的 Muse、OpenAI 等公司已率先推出同类产品。苹果此前一直没有可自主执行此类任务的智能体，据报道此番研发正是为了在快速扩张的 AI 助手市场竞争。AppleInsider 等媒体评论指出，外界其实早已普遍预期苹果会推出智能体方案，此次曝光的招聘信息让这一预期首次有了较具体的轮廓。

**「影响」** 对面向 Mac 的第三方智能体开发者而言，macOS 27.3 是当下最实际的冲击：第三方智能体获取 Mac 控制权限的步骤由 4 步增至 14 步，TechCrunch 也证实新警告页会劝阻用户向第三方智能体授予完全访问权限，新用户的启用摩擦显著上升，相关产品需要重新设计权限引导流程。苹果自研智能体最早 2027 年末才推出，而 Meta Muse、OpenAI、Claude 等竞品已先行上市；在自家产品落地之前先收紧第三方权限通道，使这些竞品在苹果平台上面临实际的分发与兼容阻力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tech.yahoo.com/ai/apple-intelligence/articles/apple-develops-ai-agent-control-160700103.html">Apple develops AI agent to control apps, browse web and write ...</a></li>
<li><a href="https://appleinsider.com/articles/26/11/19/apple-ai-agents-are-coming-to-help-you-code-browse-perform-tasks">Apple AI agents are coming to help you code, browse ...</a></li>
<li><a href="https://techcrunch.com/2026/11/19/apple-may-be-developing-its-own-ai-agent-that-runs-your-mac/">Apple may be developing its own AI agent that runs your... | TechCrunch</a></li>

</ul>
</details>

**标签**: `#apple`, `#ai-agents`, `#macos`, `#coding-agents`, `#tech-industry`

---

<a id="item-tech-news-13"></a>
### [OpenAI 后台模式上线：长任务异步执行，token 最多省 40%](https://developers.openai.com/api/docs/guides/background) ⭐️ 7.0/10

据 OpenAI 开发者文档（经 Telegram 转述，尚无法独立核实），OpenAI 推出后台模式，将长耗时请求改为异步执行：开发者在请求中设置 background: true，并通过 background\_options.completion\_window 指定 2h 或 8h 的完成时限，对应 Token 费率分别比标准价低 30% 和 40%；不设置时默认使用无折扣的 soonest。该折扣目前在 GPT-6.2 Astra、GPT-6.2 Sol、GPT-6.1 Terra 和 GPT-6.1 Luna 上公开测试。需要注意，后台模式会临时存储响应数据，即使 store 设为 false 或启用了零数据保留也不受豁免。

telegram · zaihuapd · 11月20日 11:15

**「背景」** 后台模式是 OpenAI Responses API 中的异步执行机制：完成时限自 API 接受初始请求时起算，复用同一完成窗口、continuation ID、模型与项目的后续请求可获得更高队列优先级，折扣也适用于每条符合条件的请求（含追问）。第三方报道称这两个折扣窗口于 2026 年 11 月 17 日上线，后台模式与 OpenAI 既有的 Batch API 共享速率限制，但使用相互独立的提示缓存。

**「影响」** 对延迟不敏感的批量工作负载（如离线摘要、代码库分析、数据清洗），开发者只需设置 background: true 并选择 2h 或 8h 完成时限，即可将 token 成本降低 30%–40%，适合重新评估预算分配。但存在一个明确的兼容性顾虑：即使 store 设为 false 或已启用零数据保留，后台模式的响应数据仍会被临时存储，有严格数据合规要求（如医疗、金融场景）的团队在迁移前需要评估这一例外是否可接受。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.openai.com/api/docs/guides/background">Background mode | OpenAI API</a></li>
<li><a href="https://www.datastudios.org/post/openai-responses-api-background-2-hour-8-hour-windows-30-40-percent-off">OpenAI Responses API background mode: 30% off for 2-hour, 40% ...</a></li>

</ul>
</details>

**标签**: `#openai`, `#api`, `#async-processing`, `#cost-optimization`, `#llm`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [为什么缓存模型输出行不通](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月21日 00:00

**「背景」** LLM 推理经济学依赖缓存输入（KV 缓存）来避免每条消息都重算整个对话历史，这让人自然想到是否也该缓存或去重输出。智能体的可见输出确实充满重复——复述代码片段、引用调查文档、重复示例输出——而输出 token 因需逐个串行生成，比输入 token 贵得多，浪费看似比输入端更严重。

**「方案」** 技术上可行：微调或提示模型只输出引用（如 &quot;src/script.py:12-15&quot;）而非重述内容，再由 harness 展开引用。但作者指出这只优化了可见输出。根据他自己的智能体历史，可见输出仅占输出 token 的约 6%，其余 50% 是推理 token、44% 是工具调用。由此撞上 Amdahl 定律：即使省下可见输出的三分之二（他自认是极度乐观的估计），也只省总输出 token 的约 4%。其前提假设是思维链很少自我重复——作者对此仅中等信心，因为前沿模型的思维链不可读，且他承认工具调用内部（思维链中构思的内容再在工具里重写一遍）可能存在重复，并公开征集答案。真正省 token 的办法是压缩那 94% 的不可见输出，而这主要取决于模型智能：更聪明的模型用更少的推理 token 和工具调用就能抵达正确答案，因此单价贵 5 倍的模型若总 token 少用 6 倍，整体成本反而更低。

**「启示」** 优化可见输出的重复受 Amdahl 定律硬性约束，收益上限只有几个百分点；降低智能体成本的根本杠杆是模型智能带来的不可见 token（推理与工具调用）缩减。这解释了作者观察到的反直觉现象：按 token 计价更贵的模型，用起来反而可能更便宜。

**标签**: `#llm-inference-economics`, `#caching`, `#ai-agents`, `#token-costs`, `#amdahls-law`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [预测市场：标普 500 年内突破 8000 点概率从 72%骤降至 6%](https://www.cnbc.com/2026/11/20/sp-500-8000-kalshi-odds-ai-selloff.html) ⭐️ 7.0/10

在人工智能相关股票遭抛售之际，预测市场平台 Kalshi 上的交易员目前仅给出标普 500 指数 2026 年内突破 8000 点 6%的概率，远低于 10 月 13 日的 72%。标普 500 指数年内涨幅已收窄至略高于 2%。

rss · CNBC Finance · 11月20日 19:59

**「背景」** 卡尔希（Kalshi）是一家受监管的预测市场平台，交易者可在其中就标普 500 指数能否突破某一点位等现实事件的结果买卖合约；而所谓股指进入&quot;回调区间&quot;，指道指和标普 500 已较各自近期高点下跌超过 10%。

**「影响」** 本轮抛售已使道琼斯指数和标普 500 指数进入回调区间（即较近期高点回落 10%以上）、纳斯达克指数年内转为下跌，持有 AI 建设相关科技股的投资者首当其冲；《Stock Trader&\#x27;s Almanac》认为市场低点更可能出现在 12 月中下旬，且不排除进一步下行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://kalshi.com/">Kalshi - Prediction Market for Trading the Future</a></li>
<li><a href="https://edition.cnn.com/2026/11/20/investing/us-stocks-anthropic-ai">Nasdaq wipes out gains for the year as Anthropic IPO fails to quell AI ...</a></li>

</ul>
</details>

**标签**: `#prediction markets`, `#S&amp;P 500`, `#market correction`, `#AI stocks`, `#Federal Reserve`

---

<a id="item-finance-news-2"></a>
### [美联储主席沃什拒绝提供利率前瞻指引，官员讲话量反而创 2025 年以来新高](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

美联储主席凯文·沃什上任六个月来拒绝就利率走向提供&quot;前瞻指引&quot;（即预先告知市场政策计划），CNBC 援引美国银行的分析称，过去两周联储官员公开讲话密度为 2025 年初以来同期最高。由于通胀率仍在 3%以上、高于美联储 2%的目标，CME FedWatch 数据显示交易员预计 12 月至少加息 0.25 个百分点的概率为 100%，其中理事沃勒曾提出加息 0.5 个百分点的可能性。

rss · CNBC Finance · 11月20日 21:10

**「背景」** 沃什于 2026 年 5 月经美国参议院以 54 比 45 票确认，接替鲍威尔出任第 17 任美联储主席。他上任后即从货币政策声明中删除了“前瞻指引”——即央行预先透露未来利率走向的做法，理由是这会在真正决策之前束缚政策制定者的手脚。

**「影响」** 10 月会议纪要显示几乎所有官员都预计 12 月加息，据芝商所 FedWatch 数据，交易员已 100%定价 12 月至少加息 25 个基点（并有较小概率加息 50 个基点）；美银经济学家警告，官员密集且相互矛盾的发声正在本已动荡的时期加剧利率市场波动，直接影响债券投资者。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/business/2026/may/13/kevin-warsh-federal-reserve-chair">US Senate confirms Kevin Warsh as Federal Reserve chair ...</a></li>
<li><a href="https://www.financialexpress.com/market/global-market-pulse/why-fed-chair-warsh-scrapped-forward-guidance-in-a-132-word-pivot/4272071/">Why Fed Chair Warsh scrapped forward guidance in a 132-word ...</a></li>
<li><a href="https://www.standardtopic.com/story/19348/fed-october-minutes-signal-possible-december-hike">Fed minutes show nearly all officials expect December rate hike</a></li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#forward guidance`, `#inflation`

---

<a id="item-finance-news-3"></a>
### [美国企业由回购转为净增发股票，供给增加成牛市新阻力](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

据 CNBC 报道，美国企业过去两年已从净回购股票转为净增发，Acadian 资产管理分析显示，截至上周后期净新增发行量约占总市值的 3.1%，仍低于互联网泡沫和新冠泡沫时期的峰值。近期大规模发行包括 Alphabet 宣布的 848 亿美元增发、SpaceX IPO 募资 857 亿美元，以及 Anthropic 以每股 83 美元定价、募资 810 亿美元的 IPO；分析师认为股票供给增加，叠加回购时代结束，构成已持续四年牛市的潜在阻力。

rss · CNBC Finance · 11月20日 14:15

**「背景」** 过去多年美国上市公司以回购自家股票为主，流通股数量因此不断减少，这在推高每股收益的同时也支撑了股价；而 Baker 与 Wurgler 在 2000 年发表的研究发现，企业偏向发股而非发债的时期过后，股市回报往往偏低，即管理层倾向于在股价高估时卖股。

**「影响」** 对全体美股投资者而言，过去企业回购缩减流通股、从而推高股价和每股收益的支撑机制正在逆转：据 Acadian 资产管理分析，净增发带来的股票供给增加，正成为这轮持续四年的牛市的潜在阻力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.jstor.org/stable/222488">The Equity Share in New Issues and Aggregate Stock Returns</a></li>
<li><a href="https://www.hbs.edu/faculty/Pages/item.aspx?num=9176">The Equity Share in New Issues and Aggregate Stock Returns</a></li>

</ul>
</details>

**标签**: `#equity issuance`, `#share buybacks`, `#bull market`, `#IPO market`, `#AI investment`

---