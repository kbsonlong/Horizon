---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 29 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [OpenAI 发文探讨困惑度与语言模型智能的对应关系](#item-tech-news-1) ⭐️ 7.0/10
2. [Masullo 黎曼猜想“证明”的 Lean 形式化进度图](#item-tech-news-2) ⭐️ 7.0/10
3. [O&\#x27;Reilly 发文追问“硅谷怎么了”：以机制设计转向人类繁盛](#item-tech-news-3) ⭐️ 7.0/10

**科技博客**
1. [不确定时，乱试一气：工程师的试错之道](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [美股科技股暴跌，亚洲多地推出稳定措施](#item-finance-news-1) ⭐️ 9.0/10
2. [中国商务部要求美国撤销对三大运营商的电话号码接入限制](#item-finance-news-2) ⭐️ 7.0/10
3. [超级厄尔尼诺海温破纪录，或新增 4900 万人陷入急性粮食不安全](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 发文探讨困惑度与语言模型智能的对应关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 在官网发表文章《Perplexity and Intelligence》,探讨语言模型的困惑度与智能之间的对应关系;该文于 2026 年 11 月 22 日在 Hacker News 引发 514 分、355 条评论的技术性讨论。文章正文未随条目提供,据条目分析,其论述围绕预测、压缩与模型评估展开。从社区评论来看,文中似乎基于一个留出评估集呈现各基础模型的交叉熵/困惑度趋势,且该趋势在 RL 训练的推理模型时代依然保持清晰。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景」** 困惑度（perplexity）衡量语言模型预测下一个词元时的“意外程度”，本质上是交叉熵损失的指数形式：完美预测时为 1，随机猜测时上限为词表大小，数值越低代表模型压缩（预测）数据的能力越强。将预测与压缩能力对应于智能是机器学习领域长期存在的论点，有研究者在社区讨论中称其早在 2008 年的论文中就论证过：对原始数据流的预测压缩率正是从数据中提取世界模型的核心指标。近年来业界转向 RL 训练的推理模型与日益复杂的评测基准，不少从业者一度认为交叉熵损失这类简单的预训练指标已不再是衡量能力的关键信号，这也是文中趋势令部分读者感到意外的原因。

**「影响」** 对模型评测者和开发者而言，困惑度可能正在成为跨厂商可直接比较的预训练指标：社区评论转述微软 AI CEO Mustafa Suleyman 的推文称，微软已承诺在 OpenAI 的同一保留评估集上报告其预训练进展，MAI-2 Base 的对数困惑度为 0.819，与 GPT-5.6 Sol 基础模型处于同一水平。若该承诺落实，各家基础模型的预训练质量将可在这一简单指标上直接横向对比，有评论者认为这比日益繁杂的评测套件更可取；但上述动向目前仅见于社区转述的推文，除 Suleyman 的微软 AI CEO 身份已获证实外，推文内容尚无独立来源确认。

**「社区讨论」** 评论者 jrflo 表示,原以为 RL 兴起后交叉熵损失已不再重要,文中趋势之清晰令其意外,并认为这种简单基准胜过日益繁复的各类评测;d\_burfoot 则主张“预测即压缩”恰好度量了智能从原始数据中提取世界模型的能力,并援引其 2008 年的论文作为佐证。另有评论引述微软 Mustafa Suleyman 的推文,称 MAI-2 Base 在 OpenAI 留出评估集上的 log-perplexity 为 0.819、与 GPT-5.6 Sol 基础模型相当\(此为评论转述,未经验证\);hazrmard 则指出文章未定义困惑度,并补充其取值介于 1\(完全确定\)与词表大小\(随机预测\)之间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence - OpenAI</a></li>
<li><a href="https://www.explainx.ai/blog/openai-pachocki-perplexity-intelligence-pacing-safety-november-2026">OpenAI Perplexity Metric: GPT Log-Loss Curve (Nov 2026 ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Mustafa_Suleyman">Mustafa Suleyman - Wikipedia</a></li>

</ul>
</details>

**标签**: `#machine-learning`, `#language-models`, `#evaluation-metrics`, `#research-analysis`, `#compression`

---

<a id="item-tech-news-2"></a>
### [Masullo 黎曼猜想“证明”的 Lean 形式化进度图](https://claude.ai/artifact/CtQyX8qfYAF822bgHJHHE3) ⭐️ 7.0/10

一个追踪 Alessandro Masullo 所称黎曼猜想证明手稿 Lean 形式化进度的进度图于 11 月 22 日在 Hacker News 引发大量讨论,对应社区驱动的 GitHub 仓库 mccorvie/riemann-masullo。自称为该仓库贡献者的数学家在评论中邀请外界将 AI 编程代理指向此项目以协助形式化,并说明勘误表中数百条问题有轻有重、许多已被修复,目前尚无法判断核心思路是否存在重大漏洞。与此同时,另一评论者引述称:最初代 Masullo 发布声明的 Ravi Vakil 现表示自己甚至没有读过该文稿,唯一似乎为其背书的 Brian Conrad 向《科学美国人》表示手稿需要“重大修改”,且 Masullo 除与 Conrad 合作完成的博士论文外没有其他发表记录。因此该进度图只反映形式化的覆盖范围,并不构成对该证明正确性的证据。

hackernews · Qision · 11月22日 23:12 · [社区讨论](https://news.ycombinator.com/item?id=50605045)

**「背景」** 黎曼猜想是关于黎曼 zeta 函数零点分布的最重要数学猜想之一，其推广版本广义黎曼猜想（GRH）至今未被证明。11 月 20 日，斯坦福大学教授、美国数学学会主席 Ravi Vakil 公布了同校年轻数学家 Alessandro Masullo 声称证明广义黎曼猜想的草稿，约八小时后便更新称已有多人借助不同 AI 模型报告其中存在的问题；同期还出现了另一项相互竞争的证明声称。本次讨论的 Lean 形式化进度图，正是社区为逐条核验 Masullo 这份手稿而启动的项目。

**「影响」** 该仓库的贡献者已在 Hacker News 评论中公开邀请有余力者将 AI 代理指向该项目\(仓库附有贡献指南\),为持有 LLM 代理的开发者与数学研究者提供了一条低门槛的参与路径。但读者不应把进度图当作证明大体正确的信号:数百条勘误中部分已修复、部分仍悬而未决,核心思路是否存在重大漏洞为时尚早;仓库截至 11 月 21 日也仍处于“形式化前置知识”的早期阶段。叠加 Brian Conrad 称原稿需要“重大修改”、Vakil 表示未曾阅读该文档等专家保留意见,当前的形式化进度不能作为 Masullo 证明正确性的佐证。

**「社区讨论」** 讨论的主要分歧在于形式化进度能否说明证明质量:贡献者 kopje\_koffie 认为勘误轻重不一、多数已修复且下结论为时尚早,而 hodgehog11 提醒只要一个漏洞就足以让整个证明崩塌,并表示据其理解证明中很可能存在重大漏洞,相比之下 Alpoge 证明中的 theta 提升才更像真正的进展。另有评论者\(ohyes\)对 Agentic AI 可能抢在人类数学家之前抵达终点表示沮丧,这属于个人情绪表达而非事实判断。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">Generalized Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.nacionale.com/en/articles/what-happens-next-alessandro-masullo-riemann-proof-revision-credit-clay-prize">Vakil : problems reported in Masullo &#x27;s GRH draft</a></li>
<li><a href="https://www.scientificamerican.com/article/dueling-claims-of-riemann-hypothesis-proofs-emerge/">Dueling claims of Riemann hypothesis proofs ... | Scientific American</a></li>
<li><a href="https://www.nacionale.com/en/articles/what-happens-next-alessandro-masullo-riemann-proof-revision-credit-clay-prize">Vakil: problems reported in Masullo &#x27;s GRH draft</a></li>

</ul>
</details>

**标签**: `#formal verification`, `#Lean`, `#theorem proving`, `#Riemann hypothesis`, `#community-driven mathematics`

---

<a id="item-tech-news-3"></a>
### [O&\#x27;Reilly 发文追问“硅谷怎么了”：以机制设计转向人类繁盛](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

11 月 22 日，O&\#x27;Reilly Radar 刊发长文《What Happened to Silicon Valley?》，这是一篇行业观点评论而非技术发布。文章将资本主义描述为一台“优化机器”，认为硅谷当前的困境源于它被设定去优化股东价值而非更有价值的目标，并主张引入经济学的“机制设计”——作者称之为“反向博弈论”——先追问“我们究竟应当玩一场什么样的游戏”，其给出的答案是“人类繁盛之戏”。文中还引用谷歌前首席经济学家 Hal Varian 的说法作为例证：只有约 6% 的谷歌搜索结果页带有广告。该文在 Hacker News 上获得 482 分、277 条评论的讨论。

hackernews · greenyouse · 11月22日 19:20 · [社区讨论](https://news.ycombinator.com/item?id=50602947)

**「背景」** “机制设计”（mechanism design）是经济学中被称为“反向博弈论”的分支：普通博弈论分析既定规则下的策略行为，机制设计则先确定想要的结果，再反推应当设计怎样的规则与激励，作者将这一框架作为全文的核心论据。该文以演讲形式发表于奥莱利（O&\#x27;Reilly）旗下的 Radar 评论栏目，并从文中提及的玛格丽特（Margaret）关于“合作”的论述出发，把既有合作体系开始失灵视为硅谷当前面临的根本问题。

**「现实影响」** 文章对“激励错配”的批评有可量化的现实注脚：据估算，亚马逊、Alphabet、微软等大型科技公司 2026 年的 AI 资本开支合计将达 8030 亿至 8280 亿美元，2027 年预计突破 1 万亿美元；据报市场对这轮支出的担忧已造成约 1 万亿美元的市值蒸发。这些数据为读者评估作者“以机制设计重设优化目标”的主张提供了具体依据，但该主张目前仍属规范性倡议，尚无任何政策或公司治理层面的实际变化与之挂钩。

**「社区讨论」** 评论普遍认同文章的诊断，但对成因各有侧重：michalsustr 认为全文核心正是用机制设计追问“我们应当玩什么游戏”，并赞同以“人类繁盛”为集体优化目标；CoolestBeans 则主张更直接的近因是 ZIRP（零利率）时代让科技巨头畸形膨胀、鼓励初创公司豪赌，如今利率回归后企业又在 AI 上侵蚀自身核心能力。另有评论（jansport123）批评从华尔街涌入硅谷的“VC 网红”文化，称硅谷的操守比以往任何时候都更稀薄。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/what-happened-to-silicon-valley/">What Happened to Silicon Valley? – O’Reilly</a></li>
<li><a href="https://oreillyradar.substack.com/p/what-happened-to-silicon-valley">What Happened to Silicon Valley? - oreillyradar.substack.com</a></li>
<li><a href="https://www.cnbc.com/2026/04/30/ai-boom-big-tech-capital-expenditures-now-seen-topping-1-trillion-in-2027-.html">AI boom: Big Tech capital expenditures now seen topping $1 trillion...</a></li>
<li><a href="https://www.businessinsider.com/amazon-alphabet-meta-microsoft-spacex-capex-ai-spending-total-2026-10">AI Hyperscalers Expected to Spend up to a Whopping $828B in 2026</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/fears-over-828-billion-ai-104400351.html">Fears over $828 billion AI capex spending spree help erase $1 trillion...</a></li>

</ul>
</details>

**标签**: `#tech industry`, `#silicon valley`, `#mechanism design`, `#industry analysis`, `#AI economy`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [不确定时，乱试一气：工程师的试错之道](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 工程师常处于没有明确指引、不知道什么才会有效的境地，直觉做法是谨慎等待、先加深理解。作者 Sean Goedecke 却主张此时最优策略往往是&quot;乱试一气&quot;（flail about）——尽管乱试得很糟确实会损害你在科技公司的声誉。

**「方案」** 作者给出三条要领：尝试大量不同做法、极其仔细地关注反馈、果断放弃没有正反馈的尝试。多试既是为了直接触碰现实（如同原始人乱按 iPhone 按钮看反应），也因为多数计划注定糟糕——试十件才可能有一件好，既然无法预判好坏，就必须对反馈高度敏感；持有多个计划还能避免对单一方案过度投入，从而敢于砍掉失败项。他将场景分为三类：产品乱试，即产品尚未找到 product-market fit 时在核心思路边缘试探——他在 GitHub Models（现已退役）上做的功能大多失败，但&quot;用 GitHub Actions token 运行 AI 推理&quot;意外站稳，成为 Continuous AI 的种子；工程乱试，面对庞大纠缠或已高度优化的系统，与其先完整梳理再提建议（作者认为现代系统太大且变化太快，此举愚蠢），不如做一批投机性改动看效果，AI 代理还能批量生成候选重构供比较，不行就立即丢弃；组织乱试，最关乎资深/staff 工程师——问题常非技术性（团队互不沟通、士气低迷且原因不明），主动接手任务、提出长期方案即使大多无用，也至少表明你在努力，但此处最需对反馈敏感：及时止损能建立信任，忽视反馈硬推则会招致对方的愤怒。

**「启示」** 作者的核心论点是：在产品、工程与组织的不确定性中，大量低成本实验加上对反馈的敏锐感知和快速止损，是获得理解、变得有用的最快途径；而从内部感受到的&quot;像在反复出丑&quot;的乱试感，是正常且应当被当作积极信号的心理障碍。

**标签**: `#engineering career advice`, `#decision-making under uncertainty`, `#explore-exploit`, `#organizational dynamics`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股暴跌，亚洲多地推出稳定措施](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

美国 AI 科技股周五遭大幅抛售，纳斯达克指数单日实际下跌 5.28%，费城半导体指数跌近 11%；随后中国内地下调融资保证金最低比例至 80%，韩国自 11 月 24 日起放宽上市公司每日回购订单限制，中国台湾地区自 11 月 23 日起禁止平盘以下卖空并将融券保证金比例由 130%提高至 150%。上述数字与政策来自新华社、韩联社和中央社的报道。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 这轮抛售由市场对 AI 板块的恐慌引发，以科技股为主的纳斯达克 100 指数全周累计下跌 10.4%，为六年多来最差单周表现；中国内地股市上周五已同步下挫，深证成指和创业板指均跌逾 3%，半导体股领跌、多只个股连续跌停。

**「影响」** 亚洲芯片巨头首当其冲，三星电子、SK 海力士、台积电已随美股抛售大跌（外媒报道三星一度跌近 10%、SK 海力士跌超 11%），而中国台湾禁止平盘下卖空并上调融券保证金、韩国收紧卖空监控等措施，将直接抬高做空和杠杆交易者的成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.guancha.cn/GuoJi%C2%B7ZhanLue/2026_11_21_909399.shtml">AI 恐慌爆发，华尔街震荡，美国 科 技 股 跌 入熊市</a></li>
<li><a href="https://github.com/1992513/djy/blob/master/gb/26/11/20/n14892347.md">djy/gb/26/ 11 / 20 /n14892347.md at master · 1992513/djy · GitHub</a></li>
<li><a href="https://www.cnbc.com/2026/11/06/tech-stocks-sk-hynix-samsung-softbank.html">Tech stocks sell - off : SK Hynix, Samsung , SoftBank</a></li>
<li><a href="https://www.dw.com/en/european-shares-join-a-global-sell-off-as-ai-spending-fears-rattle-wall-street-and-asian-markets/a-79871504">European and Asian stocks fall as AI fears mount</a></li>
<li><a href="https://www.theguardian.com/business/live/2026/nov/20/asia-stocks-worst-anthropic-ipo-ai-stock-market-latest-updates-news">Anthropic shares slide as AI sell - off hits global markets - as it happened</a></li>

</ul>
</details>

**标签**: `#美股科技股抛售`, `#纳斯达克大跌`, `#卖空限制`, `#亚洲市场政策应对`, `#半导体指数`

---

<a id="item-finance-news-2"></a>
### [中国商务部要求美国撤销对三大运营商的电话号码接入限制](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 7.0/10

中国商务部 11 月 22 日要求美国撤销联邦通信委员会（FCC）的新措施，即禁止中国移动、中国电信、中国联通三家最大运营商直接获取美国电话号码，并称这正推动两国在电信、通信及检测认证领域走向脱钩，中方将采取必要措施维护自身利益。FCC 于 11 月 19 日投票收紧互联网语音服务商直接接入美国号码的安全要求，新增国家安全认证，以阻止其&\#x27;覆盖清单&\#x27;（Covered List）上的实体、设备和服务接入美国网络；商务部称美方在没有事实依据的情况下援引国家安全风险，违反非歧视与公平竞争原则。

telegram · zaihuapd · 11月22日 06:44

**「背景」** FCC（美国联邦通信委员会，美国的电信监管机构）近年已多次以国家安全为由收紧对中国国有电信运营商的限制，中国电信、中国联通等公司此前均因安全原因未能获得在美运营授权，此次号码接入禁令是美国遏制骚扰电话与间谍风险行动的最新一步。

**「影响」** 禁令将使中国移动、中国电信、中国联通无法直接接入美国电话号码资源，涉及赴美话务须改经美国第三方服务商中转；中国商务部除预告将采取必要反制措施外，还表示美方举措有违两国领导人此前达成的共识。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.foxbusiness.com/politics/fcc-bans-chinese-firms-direct-access-us-phone-numbers-bid-curb-robocalls">FCC regulators bar Chinese telecom giants from direct number access</a></li>
<li><a href="https://www.foxnews.com/politics/1m-day-china-tech-crackdown-proposed-amid-cascade-us-cyber-disruptions">GOP bill would bar Chinese carriers from operating in US... | Fox News</a></li>
<li><a href="https://www.jpost.com/international/article-915665">China slams US FCC ban on direct phone number access for...</a></li>
<li><a href="https://www.foxbusiness.com/politics/fcc-bans-chinese-firms-direct-access-us-phone-numbers-bid-curb-robocalls">FCC regulators bar Chinese telecom giants from direct number access</a></li>

</ul>
</details>

**标签**: `#US-China relations`, `#telecom regulation`, `#FCC`, `#trade tensions`, `#national security`

---

<a id="item-finance-news-3"></a>
### [超级厄尔尼诺海温破纪录，或新增 4900 万人陷入急性粮食不安全](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

据伯克利地球气候学家 Zeke Hausfather，截至 10 月中热带太平洋海温升温已达 3.5℃，打破此前约 2.75℃的纪录，并预计初冬升至约 4℃峰值。世界粮食计划署 8 月警告，本轮厄尔尼诺可能在 2027 年底前额外将 4900 万人推入急性粮食不安全，使总数达 2.74 亿，而全球援助资金 2025 年已较 2022 年峰值下降 30%。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 厄尔尼诺是赤道太平洋海表温度异常偏暖的自然气候现象，会改变全球降雨格局、引发干旱与洪涝，直接冲击农业收成。科学界通常以中太平洋尼诺 3.4 区海温相对常年的偏高幅度来衡量其强度。

**「影响」** 世界粮食计划署预计相关国家的急性粮食不安全人口将从约 2.25 亿增至 2.74 亿（升约 22%）；另据 Crop Monitor 对以往厄尔尼诺事件的分析，全球稻米单产通常比趋势水平低 1.0%–1.5%，是受冲击最大的作物，稻米主产区农户收成承压最重。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://science.nasa.gov/earth/explore/el-nino/">El Niño - NASA Science</a></li>
<li><a href="https://www.yahoo.com/news/us/article/el-nino-is-being-supersized-before-our-eyes-un-warns-what-that-means-for-the-weather-where-you-live-this-fall-and-winter-115712832.html">El Niño is being &#x27;supersized before our eyes,&#x27; U.N. warns.</a></li>
<li><a href="https://www.wfp.org/news/world-food-programme-ramps-preparedness-and-response-plans-el-nino-threatens-push-tens">World Food Programme ramps up preparedness and response plans ...</a></li>
<li><a href="https://reliefweb.int/report/world/crop-monitor-special-report-el-nino-2026-2027-anticipated-climate-and-agricultural-yield-impacts-june-16-2026">Crop Monitor Special Report: El Niño 2026-2027: Anticipated ...</a></li>

</ul>
</details>

**标签**: `#climate`, `#el-nino`, `#food-security`, `#humanitarian-aid`, `#agriculture`

---