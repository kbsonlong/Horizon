---
layout: default
title: "Horizon Summary: 2026-11-22 (ZH)"
date: 2026-11-22
lang: zh
---

> 从 24 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [黎曼猜想的 Lean 形式化证明获社区联合认证](#item-tech-news-1) ⭐️ 10.0/10
2. [GPGME 2.3.0 前版本双重释放漏洞波及 GitLab、Samba 等软件](#item-tech-news-2) ⭐️ 8.0/10
3. [浙江大学在「天目 2 号」超导芯片上首次实现 QRAM 真机运行](#item-tech-news-3) ⭐️ 8.0/10
4. [微软发布 RDMA over USB4 预览，多台 PC 可合跑本地大模型](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenRouter 警告 MiniMax 提示词疑遭第三方读取，建议轮换凭证](#item-tech-news-5) ⭐️ 7.0/10
6. [特斯拉海外推送 FSD v15,新增 Reality View 可视化](#item-tech-news-6) ⭐️ 7.0/10

**科技博客**
1. [写好代码的秘诀:避免灾难性失误](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [特朗普、习近平、普京在深圳 APEC 期间首次面对面三边会晤](#item-finance-news-1) ⭐️ 7.0/10
2. [特朗普称拟对在海外建 AI 数据中心的美企征收&quot;巨额税款&quot;](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [黎曼猜想的 Lean 形式化证明获社区联合认证](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 10.0/10

2026 年 11 月 20 日，Levent Alpöge 发布黎曼猜想的 Lean 形式化证明，代码库约 1700 万行，证明由 Claude 驱动编写，Alpöge 以人类专家身份在环把关。11 月 21 日，Lean FRO 与 Mathlib Initiative 联合声明认证该命题与证明均正确：命题与 Mathlib 中已有的 RiemannHypothesis 表述一致，代码库可无错误编译，且经多个独立证明检查器验证有效。黎曼猜想是千禧年大奖难题之一，据报道 Claude 在此过程中形式化了相当大一部分现代数学；需要说明的是，目前的认证来自 Lean 社区机构自身，其结论的可靠性也取决于所用检查器本身。

hackernews · g-b-r · 11月21日 14:36 · [社区讨论](https://news.ycombinator.com/item?id=50589618)

**「背景」** 黎曼猜想是克雷数学研究所七大“千禧年大奖难题”之一，此前从未有过通过机器形式化验证的完整证明。Lean 是一种交互式定理证明器，其社区维护的数学库 Mathlib 中早已存在 RiemannHypothesis 命题的形式化表述，本次工作的关键在于首次给出并通过验证的完整证明。在 Lean 内核之外，社区还依赖多个不同语言独立实现的证明检查器对编译产物进行交叉验证，这是判定证明有效性的常规手段。

**「影响」** 对数学界而言，黎曼猜想这一千禧年大奖难题如今有了经机器验证的证明，且命题与 Mathlib 中 RiemannHypothesis 定义一致、约 1700 万行代码库可无错编译，后续研究可以直接在这份形式化资产上引用和扩展，而不必重新形式化相关陈述。由于主导者 Levent Alpöge 是任职于 Anthropic 的数论学家，Claude 承担了大量形式化工作，该结果也成为“人类专家 + AI”协作迄今最高难度的公开可复核案例。对结论持保留态度的研究者，可按社区建议用 con-leche、con-ron 等自带自洽性证明的独立检查器重新复核证明，以排除 Lean 内核缺陷的影响。

**「社区讨论」** 讨论的主要分歧在于验证可靠性：rcr-anti 认为如今存在多个不同语言实现、自带一致性证明的独立内核（如 con-leche 与 con-ron），证明利用内核漏洞的概率已微乎其微；而 thejokeisonme 反驳称过去曾有一个 Collatz 猜想的虚假反驳通过了某个所谓独立检查器，检查器的独立性可能被夸大，且联合声明的四个认证要点均未依赖人类专家的参与。此外，killerstorm 认为该结果的意义不仅在于黎曼猜想本身，对数学基础与形式化同样重大，trio8453 则强调 Levent Alpöge 善于驱动模型的能力是取得这一成果的关键。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Levent_Alp%C3%B6ge">Levent Alpöge - Wikipedia</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Riemann hypothesis proof verified in Lean</a></li>

</ul>
</details>

**标签**: `#formal-verification`, `#theorem-proving`, `#ai-assisted-mathematics`, `#lean`, `#riemann-hypothesis`

---

<a id="item-tech-news-2"></a>
### [GPGME 2.3.0 前版本双重释放漏洞波及 GitLab、Samba 等软件](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

GnuPG 官方公告披露，GPGME 2.3.0 之前的所有版本存在一个双重释放（double-free）漏洞，且无论以共享库、DLL 还是静态链接方式使用该库的软件均受影响。公告列举的受影响软件包括 Gpg4win、GnuPG Desktop、GnuPG VS-Desktop、多数邮件客户端、许多 XMPP 客户端、Samba 和 Flatpak，其中 GitLab 因支持签名提交而被认为在该路径上风险尤为突出，GitLab Omnibus 已提供相应补丁。该漏洞由 Johan Carlsson 发现，GitLab 于 2026 年 11 月 12 日上报；原定 11 月 25 日协调披露，但因 Ruby2Shell 漏洞迫使 GitLab 提前更新，公告提前至 11 月 20 日发布。需要注意，公告描述的是“潜在代码执行”，这一严重性定性在社区中存在争议。

hackernews · gdgghhhhh · 11月21日 08:32 · [社区讨论](https://news.ycombinator.com/item?id=50587208)

**「背景」** GPGME（GnuPG Made Easy）是 GnuPG 项目提供的编程接口库，让邮件客户端、Samba、Flatpak、Gpg4win 以及 GitLab 的提交签名等功能可以调用 OpenPGP 的加密与验证能力，因此它以共享库、Windows DLL 或静态链接的形式被大量软件内嵌。该漏洞被跟踪为 CVE-2026-129975，由 Johan Carlsson 发现，GitLab 于 2026 年 11 月 12 日向 GnuPG 项目通报；由于修复版本 2.3.0 从未公开发布，此前所有公开发布的 GPGME 版本均在受影响范围内，官方随公告为旧版本附上了补丁。

**「影响范围与修复措施」** 所有以共享库、DLL 或静态链接方式使用 2.3.0 之前版本 GPGME 的软件都受影响，波及大多数邮件客户端、多数 XMPP 客户端、Samba 和 Flatpak 等广泛部署的组件。系统管理员应把 GPGME 共享库升级到 2.3.1，Windows 用户可安装捆绑修复版库的 Gpg4win 5.1.2；而静态链接的二进制程序仅升级共享库无效，必须针对 GPGME 2.3.1 重新构建。

**「社区讨论」** 主要争议在于严重性定性：mik1998 认为“这只是双重释放漏洞，并非完整的 RCE 利用链”，并质疑漏洞报告是否被有意夸大。uptrails 则援引 Red Hat 的软件包仓库指出，该漏洞据称 5 年前就已被 Red Hat 在下游修复，但当时未被上游采纳；另有用户讨论 apt 等不依赖 GPGME 的工具是否受影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[ Announce ] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://www.openwall.com/lists/oss-security/2026/11/20/13">oss-security - Fwd: GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[Announce] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://www.phoronix.com/news/GnuPG-GPGME-Critical">GnuPG&#x27;s GPGME Affected By Critical Security Bug In Turn... - Phoronix</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>

</ul>
</details>

**标签**: `#security`, `#vulnerability`, `#cryptography`, `#open-source`, `#memory-safety`

---

<a id="item-tech-news-3"></a>
### [浙江大学在「天目 2 号」超导芯片上首次实现 QRAM 真机运行](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

据新浪财经报道，浙江大学团队在自主制备的超导量子芯片「天目 2 号」上实现了 QRAM（量子随机存储器）的真机运行，报道称之为全球首次，成果发表于《自然·物理》。团队在芯片上运行了可调取 4 位和 8 位数据的原型，检索准确率分别为 80.9% 和 60.4%，线路深度较未优化方案降低 30% 以上，并首次验证该架构具备局部抗噪特性。团队下一步将推进 QRAM 的规模化研究。需要说明的是，该消息为财经媒体转述，具体数据以论文原文为准。

telegram · zaihuapd · 11月21日 08:31

**「背景」** 量子随机存取存储器（QRAM）此前大多停留在理论方案层面：它设想让量子处理器以量子方式高效读取经典数据，被普遍视为量子搜索和量子机器学习等算法实用化时面临的数据访问瓶颈，真实硬件上的演示长期缺失。据英国量子行业媒体 ukquantum.org 报道，浙江大学团队此次确实在超导量子处理器上对这一架构进行了实验演示。

**「影响」** QRAM 长期停留在理论层面，是量子搜索、量子机器学习等算法设想中的关键部件，此次在超导真机上验证其可运行且具备局部抗噪性，为该架构在硬件上继续扩展提供了实验依据。但当前原型规模仅为 4 位和 8 位，8 位检索准确率 60.4% 仍明显偏低，距实用化还有相当距离，短期内不会改变现有量子计算机的能力边界。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ukquantum.org/chinese-scientists-demonstrate-quantum-random-access-memory-architecture-aimed-at-solving-data-bottleneck/">Chinese Scientists Demonstrate Quantum Random Access Memory ...</a></li>

</ul>
</details>

**标签**: `#quantum computing`, `#quantum hardware`, `#QRAM`, `#superconducting qubits`, `#research`

---

<a id="item-tech-news-4"></a>
### [微软发布 RDMA over USB4 预览，多台 PC 可合跑本地大模型](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

微软面向 Windows 推出 RDMA over USB4 开发者预览，使多台 PC 能通过普通 USB4 线缆互联，共享内存与 GPU 算力，在无需专用网卡或交换机的情况下共同运行同一个本地 AI 大模型。在演示中，三台 AMD Ryzen AI Max+ 395 机器以 4-bit 量化运行 Qwen3-235B-A22B，吞吐约 18.5 token/s。该功能目前仅为开发者预览，将通过 Windows Insider 计划推送，尚未进入稳定版 Windows。

telegram · zaihuapd · 11月21日 06:13

**「背景」** RDMA\(远程直接内存访问\)允许一台机器绕过操作系统直接读写另一台机器的内存,以往主要依赖 InfiniBand 或专用网卡与交换机,部署成本高;微软此次将其引入 USB4,使消费级 PC 用普通线缆即可组建类似集群。演示所用的 Ryzen AI Max+ 395 本就是单机运行本地大模型的常见硬件——一台 128GB 机型单独运行 Qwen3 27B\(Q4 量化\)约 11.89 token/s,此次三机合跑 235B 模型则依赖跨机内存聚合。

**「影响」** 对拥有多台大内存 Windows PC 的用户，这项功能提供了一条不依赖多 GPU 工作站或专用网卡、就能本地运行单机内存放不下的超大模型的路径：演示中三台 Ryzen AI Max+ 395 合并内存后，以约 18.5 token/s 运行 4-bit 量化的 Qwen3-235B-A22B。但该能力目前为开发者预览，需通过 Windows Insider 渠道获取，且推理框架必须适配 Windows 数据中心 RDMA 所用的同一套 NetworkDirect API 才能跨机协同，短期内主要面向开发者而非普通用户。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=MGS4ZnL8fwg">External GPU vs Desktop Tower For Local AI - YouTube</a></li>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftusbblog/introducing-rdma-over-usb4%C2%AE-on-windows-run-larger-local-ai-models-across-pcs/4574602">Introducing RDMA over USB 4 ® on Windows : run larger local AI...</a></li>

</ul>
</details>

**标签**: `#distributed inference`, `#RDMA`, `#USB4`, `#local LLM`, `#Microsoft Windows`

---

<a id="item-tech-news-5"></a>
### [OpenRouter 警告 MiniMax 提示词疑遭第三方读取，建议轮换凭证](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter 通过邮件通知用户，发往 MiniMax 模型的请求内容可能已被第三方读取，并已撤下相关端点的「零数据保留」标签。其依据是安全研究者在 2026 年 7 至 10 月间向 MiniMax 模型发送包含测试 URL 的提示词，第三方在 40 至 130 小时后访问了这些 URL。OpenRouter 将问题归因于 MiniMax 及其转发方 AtlasCloud、Novita、StreamLake，并建议曾在提示词中写入敏感凭证的用户更换 API Key 和密码。目前该消息仅通过邮件传达，OpenRouter 官网暂未发布相关公告，事件细节仍待进一步确认。

telegram · zaihuapd · 11月21日 06:53

**「背景」** OpenRouter 是一个多供应商的大模型 API 路由服务，用户请求会经其转发给上游提供商，因此上游方仍能看到提示词原文；其平台此前为部分端点标注「零数据保留」（Zero Data Retention），用以表示该端点承诺不存储请求数据。本次事件的判定依据是「金丝雀 URL」手法：研究者在提示词中嵌入唯一的测试链接，一旦该链接在事后被第三方访问，即证明提示词内容已被读取。

**「实际影响」** 在 2026 年 7 至 10 月间通过 OpenRouter 调用过 MiniMax 模型、且提示词中包含 API Key 或密码等敏感凭证的用户，应按 OpenRouter 的建议轮换相关凭证——金丝雀 URL 在发送后 40 至 130 小时被第三方访问，说明存在实际的数据外泄而非理论风险。相关端点已被撤下「零数据保留」标签，此前依赖该标签做出合规或数据处理承诺的用户需要重新评估这些端点。此外，OpenRouter 页面显示 MiniMax M3 目前仍由包括被点名 StreamLake 在内的 7 家供应方提供，由于请求会跨供应方路由，希望避开受影响转发方的用户需在请求中显式固定 provider。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openrouter.ai/">OpenRouter</a></li>
<li><a href="https://cdn.venice.ai/blog/venice-vs-openrouter">Venice.ai vs OpenRouter : API Comparison (2026)</a></li>
<li><a href="https://openrouter.ai/minimax/minimax-m3">MiniMax M3 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**标签**: `#llm-security`, `#data-privacy`, `#openrouter`, `#minimax`, `#api-data-retention`

---

<a id="item-tech-news-6"></a>
### [特斯拉海外推送 FSD v15,新增 Reality View 可视化](https://x.com/Tesla/status/2124222447855743019) ⭐️ 7.0/10

特斯拉已于 11 月 22 日开始在海外市场向车主推送 FSD v15,这是其自动驾驶系统的一次大版本更新。特斯拉宣称新版本对安全关键场景的处理能力提升至原来的 25 倍,但该数字来自厂商官方发布,尚无独立测试结果佐证。本次更新新增“Tesla Reality View”可视化界面,可在车机屏幕上将摄像头画面与 FSD 行驶规划叠加显示,支持全屏、地图、分屏视图及安静模式。此外,导航可将转弯等信息叠加显示,转向灯提示音更轻柔并逐渐减弱,坑洼、碎片等路况下的行驶体验以及学校区域和恶劣天气中的速度控制也得到优化。

telegram · zaihuapd · 11月22日 00:03

**「背景」** 特斯拉 FSD（Full Self-Driving）是一套基于端到端神经网络的驾驶辅助系统。此前有报道称，特斯拉预告 v15 将把模型参数量提升 10 倍，使系统能处理更多驾驶细节。而本次更新重点改进的坑洼避让、学校区域限速等场景，正是 FSD 长期被外界指出的薄弱环节。

**「影响」** 对海外已订阅 FSD 的车主，v15 带来 Reality View 可视化界面以及对坑洼、碎片、学校区域和恶劣天气等场景的驾驶行为优化，属于实际可感知的更新；但“安全关键场景处理能力提升至 25 倍”是特斯拉单方面宣称，尚无第三方实测或监管数据佐证，不应被解读为已获独立验证的安全性提升。此外推送为分阶段进行，马斯克此前表示 v15 将随假日更新进入大范围发布，暂未收到推送的车主可能还需等待后续批次。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=eNBqkc7V1nU">Introducing Tesla Self-Driving V 15 - YouTube</a></li>
<li><a href="https://www.notateslaapp.com/news/5057/tesla-fsd-v15-coming-next-month-with-holiday-update-musk">Tesla FSD V 15 Arriving Next Month: Home Garage... - Not a Tesla App</a></li>
<li><a href="https://electrek.co/">Electrek | EV and Tesla News, Green Energy, Ebikes, and more</a></li>
<li><a href="https://www.notateslaapp.com/news/5057/tesla-fsd-v15-coming-next-month-with-holiday-update-musk">Tesla FSD V 15 Arriving Next Month: Home Garage... - Not a Tesla App</a></li>

</ul>
</details>

**标签**: `#autonomous-driving`, `#tesla`, `#artificial-intelligence`, `#machine-learning`, `#software-update`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [写好代码的秘诀:避免灾难性失误](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月22日 00:00

**「背景」** 许多工程师把写好代码想象成产生绝妙洞见、发现优雅的新抽象,作者认为这是误解:真正的秘诀是避免灾难性失误。他用国际象棋作比——只要不送子就能赢下几乎所有业余对手\(作者估计约相当于 1600-1700 分棋力\);而编程不像篮球那样拥有&quot;持久领先优势&quot;,一次失误就可能让优雅的代码库变得破烂。

**「方案」** 作者指出两大重罪是不一致与引入不必要的需求:不一致破坏信任,工程师不能再假定代码按合理方式运作,而要处处提防意外;不必要的需求既&quot;黏&quot;——实现者有上下文判断其必要性,后来者只能假定它必要而使其长期留存——又彼此交织,每个新功能都得考虑与已有特性的交互,这种组合爆炸正是大型代码库难办的原因。他列举的典型失误包括:为同一任务引入平行系统、为关键数据引入第二个事实来源、把安全的同步操作变成微妙的异步操作、增加隐蔽故障点、弄复杂关键接口。因此写代码时应全力做两件事——找到任务在现有代码库中最自然的落点,并把需求裁剪到最小;一旦琢磨起&quot;可以用这个巧妙的模式&quot;,那往往是偏离重点、即将犯错的警报。作者在脚注中限定这套经验主要针对大型商业代码库的团队协作,且无论手写代码还是驱动 AI 智能体都适用——后者在一致性上与人类相当,却在避免不必要需求上差得多。

**「启示」** 作者的核心论点是:做出优秀的编程工作不需要聪明,聪明有时反而是劣势;真正需要的是对细节的关注,以及对保持一致、砍掉不必要需求的专注——不失误,你就能赢。

**标签**: `#software-engineering`, `#code-quality`, `#engineering-judgment`, `#opinion-essay`, `#complexity-management`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [特朗普、习近平、普京在深圳 APEC 期间首次面对面三边会晤](https://www.cnbc.com/2026/11/21/china-xi-trump-putin-global-diplomacy-shenzhen.html) ⭐️ 7.0/10

在深圳举行的亚太经合组织（APEC）领导人会议期间，美国总统特朗普、中国国家主席习近平与俄罗斯总统普京首次举行面对面三边会晤，讨论了削减核武器以及乌克兰、中东和朝鲜半岛问题。习近平在会上宣布中国将向亚太地区提供 2000 万美元支持。

rss · CNBC Finance · 11月21日 06:00

**「背景」** 亚太经济领导人会议（APEC）是亚太经济体的年度峰会，本届由中国深圳主办；此前 2025 年 9 月，习近平曾在天津的上海合作组织（以欧亚国家为主的政府间组织）年会期间，将普京与印度总理莫迪聚在一起会面，这是中国连续第二年以东道主身份促成此类大国互动。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.euronews.com/2026/11/18/trump-arrives-in-china-for-unprecedented-trilateral-encounter-with-xi-and-putin">Trump and Putin shake hands ahead of historic trilateral summit</a></li>
<li><a href="https://www.dw.com/en/apec-summit-xi-trump-and-putin-to-hold-first-ever-trilateral-in-china/live-79964719">Xi , Trump and Putin set for historic trilateral in China</a></li>

</ul>
</details>

**标签**: `#geopolitics`, `#diplomacy`, `#US-China relations`, `#APEC`, `#Russia`

---

<a id="item-finance-news-2"></a>
### [特朗普称拟对在海外建 AI 数据中心的美企征收&quot;巨额税款&quot;](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

美国总统特朗普 11 月 20 日在白宫记者会上表示，拟对在海外建设 AI 数据中心的美国科技公司征收&quot;巨额税款&quot;，目的是将数据中心留在美国、保持对中国的 AI 竞争优势。据美联社和路透社报道，这一计划目前仅是口头意图，特朗普称尚未向政府内部官员透露，也未公布税率、立法途径或时间表；他还敦促美国各地社区接纳数据中心项目，建议社区与开发商谈判争取付款，而全美多地社区因担忧用电需求和噪音正反对新建项目。

telegram · zaihuapd · 11月21日 03:26

**「背景」** AI 数据中心是集中部署大量计算机、用于训练和运行人工智能的设施，美国科技公司近年来在国内外大力扩建；由于耗电量大且噪音扰民，全美多地社区反对新建项目，而特朗普认为这类建设对美国经济有利。

**「潜在影响」** 在美国科技公司正大举投入海外多吉瓦级数据中心建设（如马来西亚）之际，若这项目前仅有表态、尚无税率与立法安排的征税计划落地，相关公司的海外 AI 基建成本将直接上升，而更多项目留在美国也可能加剧当地社区对用电和噪音的担忧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.yahoo.com/news/politics/articles/trump-says-plans-penalize-us-174503646.html">Trump seeks to penalize US companies that build AI data centers ...</a></li>
<li><a href="https://tech.yahoo.com/general/article/trump-threatens-us-companies-that-build-data-centers-in-other-countries-as-americans-increasingly-oppose-the-facilities-in-their-communities-202048230.html">Trump threatens U . S . companies that build data centers in other...</a></li>
<li><a href="https://www.technologyreview.com/2025/05/20/1116327/ai-energy-usage-climate-footprint-big-tech/">We did the math on AI ’s energy footprint. | MIT Technology Review</a></li>

</ul>
</details>

**标签**: `#US policy`, `#AI data centers`, `#corporate taxation`, `#US-China AI competition`, `#tech investment`

---