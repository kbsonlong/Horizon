---
layout: default
title: "Horizon Summary: 2026-11-16 (ZH)"
date: 2026-11-16
lang: zh
---

> 从 38 条内容中筛选出 5 条重要资讯。

---

**科技新闻**
1. [美团开源 LongCat-2.5，称全程使用华为升腾训练](#item-tech-news-1) ⭐️ 8.0/10
2. [MacBook Pro 串联 OLED 屏的 PWM 闪烁争议](#item-tech-news-2) ⭐️ 7.0/10
3. [Meta FAIR 与 NYU 训练 200+ 个多模态模型，拆解视觉编码三项设计选择](#item-tech-news-3) ⭐️ 7.0/10
4. [FAA 全国停飞溯源：铜线换光纤升级中新路由器故障](#item-tech-news-4) ⭐️ 7.0/10

**财经新闻**
1. [卢特尼克之子执掌的康托证券大幅减持英伟达，涉华芯片走私争议引发利益冲突质疑](#item-finance-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [美团开源 LongCat-2.5，称全程使用华为升腾训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队在模型正式发布一周后公布了 LongCat-2.5 的权重，该模型总参数量约 1.6 万亿，每 token 激活约 480 亿参数，面向可自主完成多步骤编程等任务的智能体，支持文本、图像和视频输入。美团官方称其训练全程使用华为升腾加速卡，未使用英伟达 GPU，但这一硬件说法与跑分均为厂商自述，尚无独立验证。模型在 Terminal Bench v2.1 上得分为 88.4，略低于 Claude Opus 5 的 89.1。权重以 MIT 许可证发布，可免费商用。

telegram · zaihuapd · 11月15日 11:08

**「背景」** LongCat 是美团旗下的开源大模型系列：上一代 LongCat-2.0 同样是 1.6 万亿参数、面向编程任务的开源模型，曾在 6 月 30 日先以“权重即将发布”的占位形式亮相，随后才将完整权重上传至 Hugging Face，并采用 MIT 许可证发布。此前有报道称，LongCat-2.0 是在约 5 万张国产（升腾）芯片上训练的，并以 MIT 许可证在 GitHub、Hugging Face 和 ModelScope 同步开源。因此 LongCat-2.5“全程使用升腾、未用英伟达 GPU”的说法延续了该团队此前的做法，“先发布模型、约一周后放出权重”的节奏也与上一代类似。

**「影响」** 对开发者与企业而言，LongCat-2.5 以 MIT 许可证开放权重并允许商用，意味着可以自行部署一个官方报告在 Terminal Bench v2.1 上得分 88.4、接近 Claude Opus 5（89.1）的编程智能体模型，从而减少对闭源 API 供应商的依赖；但 1.6 万亿总参数（每 token 激活约 480 亿）的自托管部署仍需可观的显存与算力投入。需要注意，“全程使用华为升腾芯片训练、未用英伟达 GPU”目前仅为美团单方面声明，尚无独立验证，将其作为非英伟达训练路线参考的组织应将其视为待证实的厂商主张。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aicodingweekly.datadriftpress.com/p/61-longcat-edges-out-gpt-5-5">#61 - LongCat edges out GPT-5.5 | AI Coding Weekly</a></li>
<li><a href="https://www.ainchina.com/blog/meituan-longcat-2-trillion-domestic-chips-china-ai-independence-2026/">How Meituan Built a Trillion - Parameter AI Model on 50,000 Domestic...</a></li>

</ul>
</details>

**标签**: `#large language models`, `#open source`, `#AI hardware`, `#agentic AI`, `#China tech industry`

---

<a id="item-tech-news-2"></a>
### [MacBook Pro 串联 OLED 屏的 PWM 闪烁争议](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

11 月 15 日，MacAnorak 发布分析文章（经 HackerNews 讨论扩散），主张搭载串联 OLED（tandem OLED）显示屏的 MacBook Pro 在亮度调光时使用 PWM，其闪烁可能令对闪烁敏感的用户出现眼部疲劳等不适，文章标题即称这是“更好的屏幕反而更难用”。文中引用的测试将 PWM 频率测为约 240Hz，但该数字属于作者一方引用的测量结果，既未经独立验证，也在社区复核中受到直接质疑。受影响的主要是对 PWM 闪烁敏感的一部分用户，而非所有使用者。

hackernews · MacAnorak · 11月15日 13:15 · [社区讨论](https://news.ycombinator.com/item?id=50506719)

**「背景」** PWM\(脉冲宽度调制\)是 OLED 屏幕常见的调光方式：面板通过高速通断来控制亮度，而非持续降低电压，当闪烁频率偏低时，一部分对闪烁敏感的用户可能出现眼疲劳、头痛等不适，这类问题在以往的 OLED 笔记本屏幕上早有讨论。此前 MacBook Pro 一直采用 mini-LED 背光的液晶屏，而文中讨论的机型改用了双层串联\(tandem\)OLED 面板，即两片 OLED 发光层叠加工作，其调光与闪烁行为也因此不同于单层 OLED 和 LCD，这正是本次分析围绕的核心。文中涉及的具体闪烁频率\(240Hz 还是 480/960Hz\)目前仍属作者测量与社区推断，尚无定论。

**「对用户的影响」** 对 PWM 频闪敏感的用户受到直接影响：Notebookcheck 实测 OLED 版 MacBook Pro 的 PWM 频率约为 240 Hz，而前代 mini-LED 机型约为 14,880 Hz，即便新机支持 DC 调光，该频率仍可能让敏感用户出现眼睛疲劳或不适。即使按较高的 480 Hz 估计，也仅处于敏感人群可接受范围的上限，更高才更稳妥。这部分用户在购买前应实际试用设备，或继续选择 mini-LED 机型。

**「社区讨论」** 评论者 legitronics 表示核对原始测量数据后得不出 240Hz 的结论，认为最坏情况约为 480Hz，且两片 OLED 各以 480Hz、相位相差 180 度进行 PWM，在两层同时点亮的大部分可用亮度下有效频率接近 960Hz。achr2 则对苹果采用如此低的 PWM 频率表示惊讶，并援引一篇 Nature 论文称人可感知到频率远高于此的闪烁；另有评论者分享了脑震荡后面对任何屏幕都会不适的经历，并呼吁研究 PWM 敏感人群的实际比例。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.notebookcheck.net/Amazing-OLED-panel-Apple-MacBook-Pro-14-PROLED-XDR-Review.1438048.0.html">Amazing OLED panel - Apple MacBook Pro ... - Notebookcheck Review</a></li>
<li><a href="https://www.youtube.com/watch?v=sGgowKoztzk">Is the PROLED ( OLED ) MacBook Pro a Disaster? Flicker ... - YouTube</a></li>
<li><a href="https://www.macrumors.com/2023/01/10/oled-macbook-kuo/">Kuo: Apple&#x27;s First MacBook With an OLED Display to... - MacRumors</a></li>

</ul>
</details>

**标签**: `#hardware`, `#displays`, `#oled`, `#pwm-flicker`, `#apple`

---

<a id="item-tech-news-3"></a>
### [Meta FAIR 与 NYU 训练 200+ 个多模态模型，拆解视觉编码三项设计选择](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 7.0/10

Meta FAIR 与纽约大学的研究者从零训练了 200 多个多模态 LLM（含 LLM 本体），在完全相同的数据和统一的“生命周期算力”预算下，将视觉编码器中捆绑的三项设计选择拆开逐一检验：编码器单独预训练、仅视觉 token 使用的参数、编码器置于 LLM 之前的位置。主要实验采用 Qwen3-1.7B 和 4B 配置加 0.4B 视觉参数，缩放阶梯覆盖 0.6B 至 6.4B 骨干，评估使用 Cambrian 的 16 个 VQA 基准（448px）和 12 个语言基准。结论是：单独预训练可有可无——四种目标（对比、自监督、两种字幕）预训练的编码器在匹配算力下最多与从零训练持平，将 MetaCLIP 预训练时长增加 6.5 倍虽把 ImageNet 线性探测准确率从 80.4% 提到 84.4%，但 VQA 并未提升；视觉专用参数则不可替代——无编码器模型在 0.6B 到 6.4B 各规模上均落后，约需 3 倍算力才能追平，把参数交给 LLM 只改善文本不改善 VQA；编码器前置也可有可无——在 LLM 前 8 层注入零初始化视觉专用权重（注意力投影与 FFN）的“In-fusion”方案在 1.7B 到 6.4B 上与编码器持平，首 token 延时约低 13%。论文发布于 alphaxiv（abs/2611.17334），博客见 unbundling.github.io。

reddit · r/MachineLearning · /u/trungh98 · 11月15日 17:38

**「背景」** 多模态大模型通常先用一个独立预训练的视觉编码器（以对比学习、自监督或图像描述等为目标训练）把图像转换为 token，再输入语言模型，但这一做法实际上把三个设计选择捆绑在一起：单独预训练、仅视觉 token 使用的参数、以及编码器置于语言模型之前的位置。据帖子所述，各前沿实验室目前对这些取舍并不一致：Gemma 4 12B 取消了编码器，Kimi K3 从零训练自己的编码器，Inkling 2 Small 则重新引入了编码器。由于已发布模型在数据和算力上互不相同，且几乎从不把编码器预训练的开销计入比较，公开模型无法直接裁决这一争论，这正是本研究用 200 多个从零训练、数据和算力对齐的模型做受控消融的动机。

**「影响」** 当前各家前沿实验室在视觉编码上路线分歧明显（发帖者举例：Gemma 4 12B 去掉了编码器，Kimi K3 从零训练编码器，Inkling 2 Small 则恢复了编码器），而已发布模型因数据与算力不同、且很少计入编码器预训练成本，无法直接对比。该研究为多模态模型开发者提供了受控证据：若按生命周期算力记账，投入编码器预训练可能不划算，但省掉视觉专用参数会付出约 3 倍算力代价；采用 In-fusion 式层内注入可在同等 VQA 表现下换取约 13% 的首 token 延时降低，且在预训练 LLM 的中期训练中同样成立。需要说明的是，证据来自作者自述的 Reddit 帖及其链接的论文与博客，具体数字尚待独立验证。

**标签**: `#machine-learning`, `#multimodal-models`, `#vision-encoders`, `#research-paper`, `#empirical-study`

---

<a id="item-tech-news-4"></a>
### [FAA 全国停飞溯源：铜线换光纤升级中新路由器故障](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

据美国交通部长 Sean Duffy 11 月 14 日说明，FAA 周五下令的全国停飞源于一处偏远设施将老旧铜线更换为光纤的例行维护，新装路由器随后出现故障，导致数千架航班停飞。该路由器以每 4 到 5 秒超过一千次连接请求的频率冲击其他路由器，干扰了雷达信号与飞机通信。根因尚未确定，可能是硬件故障、配置错误或承包商 L3Harris 的失误；Duffy 并借此呼吁国会追加空管现代化资金。

telegram · zaihuapd · 11月15日 02:10

**「背景」** 美国联邦航空管理局（FAA）自 1967 年起隶属美国交通部，负责全美空中交通管制，因此此次事故由交通部长 Sean Duffy 出面通报。周五的全国停飞令美国国内出发航班中断逾四个小时，周六早晨仍有数千航班取消或延误，各航空公司还在消化影响。官方表示没有发现网络攻击迹象，调查聚焦阿肯色州与得克萨斯州的路由器，而路由器制造商则称其设备“并未发生故障”。

**「影响」** 直接后果是数千架次航班取消，美国媒体称这是约 25 年来持续时间最长的全国性停飞之一（tool-3-1）。交通部长 Duffy 事后向国会要求 500 亿美元紧急拨款，用于更换引发故障的老旧路由器与交换机并重建空管基础设施（tool-3-2）。《纽约时报》指出，FAA 老化系统近几个月在推进升级时已多次发生中断（tool-3-3）；本次故障又恰恰出现在铜线换光纤的例行维护过程中，说明在现代化完成之前，此类升级施工本身仍可能再次触发大范围停飞。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.m.wikipedia.org/wiki/Federal_Aviation_Administration">Federal Aviation Administration - Wikipedia</a></li>
<li><a href="https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247">FAA lifts ground stop hours after stranding thousands of flights...</a></li>
<li><a href="https://www.yahoo.com/news/us/live/faa-ground-stop-latest-updates-duffy-blames-contractor-l3harris-thousands-more-flights-canceled-saturday-no-sign-of-cyberattack-161329174.html?fr=sycsrp_catchall">FAA ground stop latest updates: Duffy says routers in Arkansas...</a></li>
<li><a href="https://www.foxnews.com/live-news/thousands-of-flights-canceled-after-longest-nationwide-ground-stop-in-25-years-rocks-us-airports">Thousands of flights canceled in wake of FAA ground stop</a></li>
<li><a href="https://www.foxbusiness.com/politics/duffy-sounds-alarm-over-aging-faa-system-after-nationwide-air-travel-shutdown">Sean Duffy demands $50B to rebuild aging air traffic control system</a></li>
<li><a href="https://www.nytimes.com/2026/11/14/us/politics/ground-stop-air-traffic-faa.html">Ground Stop Highlights Chronic Vulnerabilities in Air Traffic System</a></li>

</ul>
</details>

**标签**: `#networking`, `#infrastructure-outage`, `#aviation`, `#hardware`, `#critical-infrastructure`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [卢特尼克之子执掌的康托证券大幅减持英伟达，涉华芯片走私争议引发利益冲突质疑](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

据 CNBC 对证券文件的分析，美国商务部长霍华德·卢特尼克之子执掌的康托·菲茨杰拉德在 2025 年 9 月至 2026 年 3 月间将所持英伟达股票减持近 50%，持仓价值从 6.52 亿美元降至 3.1 亿美元，同期仍继续为英伟达的业务伙伴安排数十亿美元融资。报道指减持期间白宫和情报官员正施压卢特尼克打击涉嫌向中国走私英伟达 AI 芯片的新加坡公司 Megaspeed 而其据 Axios 报道多次抵制，此事在英伟达 CEO 黄仁勋上周四辞职后引发利益冲突质疑；但 CNBC 强调，目前没有证据表明其子提前知晓相关情报警告，或公司利益影响了部长的决策，白宫表示特朗普对卢特尼克&quot;完全有信心&quot;。

rss · CNBC Finance · 11月15日 19:58

**「背景」** 美国商务部长霍华德·卢特尼克此前长期执掌投行坎托·菲茨杰拉德（Cantor Fitzgerald），该行现由其两个儿子布兰登和凯尔领导，而商务部正是负责芯片出口管制、可将企业列入“实体清单”（限制美国公司与特定外国企业往来的官方名单）的部门。英伟达首席执行官黄仁勋已于 11 月 12 日因被指与疑似中国间谍有联系的丑闻辞职，由首席财务官科莱特·克雷斯临时接任。

**「影响」** 受影响最直接的是英伟达及其投资者：财政部长贝森特已公开表示，财政部、国防部、国务院和贸易代表办公室数月来都支持把 Megaspeed 列入“实体清单”（美国政府限制交易的企业名单），而负责执行该清单的商务部是否行动，将直接决定英伟达对华芯片销售受限的程度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theguardian.com/technology/live/2026/nov/12/nvidia-ceo-jensen-huang-affairs-share-price-plunges-live-latest">Nvidia turmoil continues as Jensen Huang resigns ... | The Guardian</a></li>
<li><a href="https://www.npr.org/2026/11/12/nx-s1-6037833/jensen-huang-nvidia-stepped-down">Nvidia CEO Jensen Huang resigns amid spy scandal : NPR</a></li>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.bbc.com/news/articles/cmdx1vpprk9vo">Suspected China spy linked to Nvidia &#x27;s ex-boss left in 2025...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#conflict of interest`, `#export controls`, `#national security`, `#Trump administration`

---