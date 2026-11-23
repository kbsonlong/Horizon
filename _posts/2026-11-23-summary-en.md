---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 29 items, 7 important content pieces were selected

---

**Technology News**
1. [OpenAI Essay Argues Perplexity Tracks Model Intelligence](#item-tech-news-1) ⭐️ 7.0/10
2. [Lean Formalization of Masullo&\#x27;s Claimed Riemann Hypothesis Proof Invites AI Agents](#item-tech-news-2) ⭐️ 7.0/10
3. [Tim O&\#x27;Reilly: Realign Silicon Valley&\#x27;s Incentives Toward Human Flourishing](#item-tech-news-3) ⭐️ 7.0/10

**Technology Blog**
1. [Flailing Under Uncertainty: Try Many Things, Drop Failures Fast](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [US Tech Stocks Plunge; Asian Markets Roll Out Stabilization Measures](#item-finance-news-1) ⭐️ 9.0/10
2. [China Demands US Revoke Restrictions on Phone Number Access](#item-finance-news-2) ⭐️ 7.0/10
3. [Record Super El Niño Threatens to Deepen Global Hunger as Aid Funding Falls](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Essay Argues Perplexity Tracks Model Intelligence](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI published an essay arguing that a language model&\#x27;s perplexity, its held-out prediction error on a common evaluation set, corresponds to intelligence, with the accompanying discussion indicating it presents a cross-entropy trend that remains clear even for RL-trained reasoning-era models and positions perplexity as a simpler alternative to increasingly convoluted benchmarks. The article text itself is not supplied here, so its specific claims cannot be independently confirmed from this item. A commenter reported, citing a Mustafa Suleyman tweet, that Microsoft has now committed to sharing its pre-training progress on OpenAI&\#x27;s common held-out evaluation set, with MAI-2 Base posting a log-perplexity of 0.819, described as being in the same ballpark as OpenAI&\#x27;s GPT-5.6 Sol base model.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Perplexity and the compression–intelligence idea」** Perplexity — the exponentiated cross-entropy loss a language model incurs when predicting the next token, where 1 means perfect prediction and the vocabulary size means a random guess — has been the standard quality measure for language models since well before the current LLM era. The claim that prediction and compression are intertwined with intelligence is a long-standing idea in machine-learning research, but frontier-lab evaluation practice had shifted toward increasingly task-specific capability benchmarks, and the spread of RL-trained reasoning models led many practitioners to treat pretraining cross-entropy loss on a fixed held-out set as no longer a decisive signal.

**「Impact」** The essay&\#x27;s metric may be hardening into a de facto cross-lab benchmark: a Hacker News commenter reports that Microsoft AI — led by CEO Mustafa Suleyman — has committed to reporting pre-training perplexity on OpenAI&\#x27;s common held-out evaluation set, with MAI-2 Base posting a log-perplexity of 0.819, reportedly in the same ballpark as OpenAI&\#x27;s GPT-5.6 Sol base model. If that commitment holds, researchers and developers gain a single, simple next-token-prediction figure for comparing base models across labs, though the numbers cited so far are vendor-reported via social media rather than independently measured.

**「Community discussion」** The most substantive thread concerned whether prediction and compression genuinely equal intelligence: d\_burfoot argued the correspondence &quot;could not work any other way&quot; because prediction rate on raw data is exactly the metric capturing extraction of world models, citing his own 2008 paper, while jrflo expressed surprise that the cross-entropy trend stays so clear despite the shift to RL-trained reasoning models. hazrmard noted the article never defines perplexity and supplied the definition for other readers, ranging from 1 for a perfect next-token predictor up to the vocabulary size for a random one.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence - OpenAI</a></li>
<li><a href="https://www.explainx.ai/blog/openai-pachocki-perplexity-intelligence-pacing-safety-november-2026">OpenAI Perplexity Metric: GPT Log-Loss Curve (Nov 2026 ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Mustafa_Suleyman">Mustafa Suleyman - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#language-models`, `#evaluation-metrics`, `#research-analysis`, `#compression`

---

<a id="item-tech-news-2"></a>
### [Lean Formalization of Masullo&\#x27;s Claimed Riemann Hypothesis Proof Invites AI Agents](https://claude.ai/artifact/CtQyX8qfYAF822bgHJHHE3) ⭐️ 7.0/10

A progress map for the community-run Lean formalization of Alessandro Masullo&\#x27;s claimed proof of the Riemann hypothesis surfaced on Hacker News on November 22, tracking work in the riemann-masullo GitHub repository against the manuscript. A mathematician contributing to the repo reports that hundreds of errata issues, some minor and some not, have been logged, with many already fixed, and that it is &quot;way too early to tell&quot; whether the core argument contains a fatal gap; the project&\#x27;s contribution guide explicitly invites volunteers to point AI coding agents at the effort. Outside skepticism is serious: commenters report that Ravi Vakil, who originally announced the claim on Masullo&\#x27;s behalf, now says he has not even read the document, and that Brian Conrad — described as the only academic vouching for the work and Masullo&\#x27;s thesis advisor — told Scientific American the manuscript needs &quot;major revision.&quot; Masullo has no other publications besides the claimed proof and his thesis, the argument&\#x27;s correctness remains unverified, and the formalization progress bar is not evidence that it is sound.

hackernews · Qision · Nov 22, 23:12 · [Discussion](https://news.ycombinator.com/item?id=50605045)

**「Background」** The Riemann hypothesis, one of the most important open conjectures in mathematics, concerns the zeros of the Riemann zeta function. On November 20, Ravi Vakil, president of the American Mathematical Society and a Stanford mathematician, publicly posted Alessandro Masullo&\#x27;s draft proof of the generalized Riemann hypothesis on Masullo&\#x27;s behalf, then added an update about eight hours later saying several people had already reported problems in the proposed proof, some found with the help of different AI models.

**「Impact」** The progress map should not be read as evidence that the proof is holding up: the riemann-masullo repo describes itself as still &quot;formalizing the prerequisites&quot; of the 940-page draft, and problems reported in the manuscript could still force major revision of its core argument. Because the project explicitly invites AI-agent-assisted contributions, outside effort — human or agentic — may be spent formalizing groundwork that a single irreparable gap in the core would invalidate.

**「Community Discussion」** The central disagreement is over how much signal the effort carries: repo contributor kopje\_koffie argues it is &quot;way too early to tell&quot; whether the hundreds of errata entries conceal a fatal hole in the core idea, while commenter ion\_trapper counters with expert context — Vakil&\#x27;s statement that he never read the manuscript, Conrad&\#x27;s &quot;major revision&quot; verdict, and Masullo&\#x27;s absent publication record. hodgehog11 adds a structural caution that the progress bar cannot indicate correctness because &quot;it takes only one hole for the entire thing to come crashing down,&quot; arguing the machinery involved feels like less of a leap than the asymptotic-order theta lifting in Alpoge&\#x27;s competing claimed proof.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">Generalized Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.nacionale.com/en/articles/what-happens-next-alessandro-masullo-riemann-proof-revision-credit-clay-prize">Vakil : problems reported in Masullo &#x27;s GRH draft</a></li>
<li><a href="https://www.scientificamerican.com/article/dueling-claims-of-riemann-hypothesis-proofs-emerge/">Dueling claims of Riemann hypothesis proofs ... | Scientific American</a></li>
<li><a href="https://www.nacionale.com/en/articles/what-happens-next-alessandro-masullo-riemann-proof-revision-credit-clay-prize">Vakil: problems reported in Masullo &#x27;s GRH draft</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#Lean`, `#theorem proving`, `#Riemann hypothesis`, `#community-driven mathematics`

---

<a id="item-tech-news-3"></a>
### [Tim O&\#x27;Reilly: Realign Silicon Valley&\#x27;s Incentives Toward Human Flourishing](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O&\#x27;Reilly has published a long-form essay on O&\#x27;Reilly Radar, &quot;What Happened to Silicon Valley?&quot;, arguing that the industry&\#x27;s dysfunction is a problem of misaligned incentives: capitalism is treated as an optimization engine whose current objective function is shareholder value rather than broader value creation. The proposed remedy is mechanism design, framed in the essay as &quot;reverse game theory&quot; — asking not what the rules of the current game are but &quot;What game ought we to be playing?&quot; — with the author&\#x27;s answer being &quot;the game of human flourishing.&quot; The essay cites a remark from Hal Varian, formerly Google&\#x27;s chief economist, that only about 6% of Google search result pages carry any advertising. This is an argument rather than a shipped policy or capability, but it drew substantial Hacker News engagement \(482 points, 277 comments\), much of it debating whether the incentive-design framing or the cheap-money era better explains the industry&\#x27;s current state.

hackernews · greenyouse · Nov 22, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50602947)

**「Background」** Mechanism design, the framework at the essay&\#x27;s core, is a branch of economics often described as &quot;reverse game theory&quot;: rather than deducing what players will do under existing rules, it asks what rules and incentives would lead self-interested participants toward a chosen outcome. The piece ran on O&\#x27;Reilly Radar, tech publisher O&\#x27;Reilly&\#x27;s long-running commentary channel, framed as a lecture tracing Silicon Valley&\#x27;s shift from customer-centered innovation toward extraction driven by shareholder capitalism, monopoly ambitions, and hype, and it ties that trajectory to the economics of the current AI boom.

**「Impact」** The essay&\#x27;s argument about misaligned incentives has a measurable test case running now: hyperscalers including Amazon, Alphabet, and Microsoft are projected to spend a combined $803–828 billion on AI infrastructure in 2026, and investor fears over that outlay have already helped erase roughly $1 trillion in market value. For the developers and organizations being asked to redirect effort toward AI, the question O&\#x27;Reilly raises about what the industry is optimizing for is being settled in current capital allocations and market reactions, not merely in commentary.

**「Community discussion」** Several commenters endorsed the essay&\#x27;s core move: michalsustr flagged the buried mechanism-design passage as the most important idea, and Animats argued the market is a machine people built and whose designers should be held accountable rather than treated as natural phenomena. Others disputed the diagnosis — CoolestBeans contended the proximate cause was the zero-interest-rate era, which let companies grow to &quot;grotesque proportions&quot; and now fuels AI spending that cannibalizes core competencies, while jansport123 blamed an influx of 1980s Wall Street transplants and self-serving &quot;VC influencers&quot; for thinning the culture.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/what-happened-to-silicon-valley/">What Happened to Silicon Valley? – O’Reilly</a></li>
<li><a href="https://www.businessinsider.com/amazon-alphabet-meta-microsoft-spacex-capex-ai-spending-total-2026-10">AI Hyperscalers Expected to Spend up to a Whopping $828B in 2026</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/fears-over-828-billion-ai-104400351.html">Fears over $828 billion AI capex spending spree help erase $1 trillion...</a></li>

</ul>
</details>

**Tags**: `#tech industry`, `#silicon valley`, `#mechanism design`, `#industry analysis`, `#AI economy`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Flailing Under Uncertainty: Try Many Things, Drop Failures Fast](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** Engineers routinely face situations with no clear guidance — features without product-market fit, tangled or oversized systems, team dysfunction nobody can articulate — where waiting for better understanding seems safer. The author argues it usually isn&\#x27;t, while candidly admitting this is dangerous advice: flailing badly can damage your reputation, and his case rests largely on one first-hand anecdote plus his own judgment.

**「Solution」** His method has three parts: try many different things, watch feedback extremely closely, and ruthlessly drop whatever isn&\#x27;t working. Volume enables all three — it maximizes contact with reality \(&\#x27;hit all the buttons and see what happens&\#x27;\), compensates for most plans being bad \(try ten and one may be good\), and prevents over-investment in any single plan. He maps this onto three arenas. Product flailing: his GitHub Models work produced many failed features, but AI inference from a GitHub Actions token proved sticky and seeded &\#x27;Continuous AI&\#x27;. Engineering flailing: exhaustively studying large modern systems before acting strikes him as foolish — make speculative changes, drop them immediately if not better, and dig in if they are; AI agents help by generating several candidate refactors to skim. Organizational flailing, the senior/staff case, means automating manual work, volunteering for tasks, and proposing long-term plans — most won&\#x27;t help, but visible effort counts, and feedback sensitivity matters most here, since dropping a failing plan builds trust while pressing on attracts blame. He closes on psychology: the approach feels like repeated failure from the inside even when it reads as proactive experimentation from outside, and that feeling should be treated as a positive signal.

**「Takeaway」** The author&\#x27;s core thesis is that under uncertainty, broad and cheap experimentation with fast feedback and ruthless pruning beats cautious deliberation. It is a familiar explore-exploit idea made memorable by honesty about its psychological cost — though he never seriously addresses when flailing is the wrong strategy, such as irreversible actions or high-blast-radius decisions.

**Tags**: `#engineering career advice`, `#decision-making under uncertainty`, `#explore-exploit`, `#organizational dynamics`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US Tech Stocks Plunge; Asian Markets Roll Out Stabilization Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

US AI-related tech stocks suffered a heavy selloff on Friday, with the Nasdaq falling 5.28% in a single day and the Philadelphia Semiconductor Index dropping nearly 11%, according to Xinhua, Yonhap, and CNA reports. In response, mainland China cut the minimum margin requirement for leveraged stock trading to 80%, South Korea will ease daily share buyback order limits for listed companies for three months starting November 24, and Taiwan will ban short-selling below the previous day&\#x27;s close from November 23 while raising the margin deposit for short sales from 130% to 150%.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** The tech-led rout left the Nasdaq 100 down 10.4% for the week, its worst weekly performance in more than six years. Mainland Chinese markets had already fallen on the Friday session, with semiconductor stocks among the biggest decliners, before regulators across Asia announced their stabilization measures.

**「Who is affected」** Asian chipmakers and tech-sector investors are directly exposed — TSMC, Samsung Electronics and SK Hynix had already closed down 4.7%, 7% and 5.9% in an earlier wave of the AI-related sell-off — while the new measures immediately change the trading rules for leveraged investors and short sellers in mainland China, Korea and Taiwan.

<details><summary>References</summary>
<ul>
<li><a href="https://www.guancha.cn/GuoJi%C2%B7ZhanLue/2026_11_21_909399.shtml">AI 恐慌爆发，华尔街震荡，美国 科 技 股 跌 入熊市</a></li>
<li><a href="https://github.com/1992513/djy/blob/master/gb/26/11/20/n14892347.md">djy/gb/26/ 11 / 20 /n14892347.md at master · 1992513/djy · GitHub</a></li>
<li><a href="https://www.theguardian.com/business/live/2026/nov/20/asia-stocks-worst-anthropic-ipo-ai-stock-market-latest-updates-news">Anthropic shares slide as AI sell - off hits global markets - as it happened</a></li>

</ul>
</details>

**Tags**: `#美股科技股抛售`, `#纳斯达克大跌`, `#卖空限制`, `#亚洲市场政策应对`, `#半导体指数`

---

<a id="item-finance-news-2"></a>
### [China Demands US Revoke Restrictions on Phone Number Access](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 7.0/10

China&\#x27;s Commerce Ministry on November 22 demanded that the US revoke new Federal Communications Commission \(FCC\) rules that bar China Mobile, China Telecom, and China Unicom from directly accessing US phone numbers. The FCC&\#x27;s November 19 vote tightened security requirements for internet voice providers seeking direct access to US numbers, citing entities on its Covered List; China called the national security justification factually unsupported and warned the moves are pushing both countries toward decoupling in telecoms, communications, and testing certification, adding it will take necessary measures to protect its interests.

telegram · zaihuapd · Nov 22, 06:44

**「Background」** The FCC is the top US telecom regulator, and its &\#x27;Covered List&\#x27; names foreign equipment and services it judges to be national-security risks and bars from US networks. All three carriers involved are Chinese state-owned firms, and US regulators have previously denied or revoked US operating authorizations for Chinese telecom operators such as China Telecom and China Unicom on security grounds.

**「Impact」** China Mobile, China Telecom and China Unicom lose direct access to US phone-number resources — a curb the FCC framed as part of efforts against robocalls — while MOFCOM&\#x27;s threatened countermeasures, if carried out, could affect US telecom and testing-certification businesses in China.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/China_Unicom">China Unicom - Wikipedia</a></li>
<li><a href="https://www.foxnews.com/politics/1m-day-china-tech-crackdown-proposed-amid-cascade-us-cyber-disruptions">GOP bill would bar Chinese carriers from operating in US... | Fox News</a></li>
<li><a href="https://www.jpost.com/international/article-915665">China slams US FCC ban on direct phone number access for...</a></li>
<li><a href="https://www.foxbusiness.com/politics/fcc-bans-chinese-firms-direct-access-us-phone-numbers-bid-curb-robocalls">FCC regulators bar Chinese telecom giants from direct number access</a></li>

</ul>
</details>

**Tags**: `#US-China relations`, `#telecom regulation`, `#FCC`, `#trade tensions`, `#national security`

---

<a id="item-finance-news-3"></a>
### [Record Super El Niño Threatens to Deepen Global Hunger as Aid Funding Falls](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

Central tropical Pacific sea-surface warming, a measure of El Niño strength, reached a record 3.5°C as of October, breaking the prior record of about 2.75°C, and is projected by Berkeley Earth climate scientist Zeke Hausfather to peak near 4°C in early winter. The World Food Programme warned in August that this El Niño could push an additional 49 million people into acute food insecurity by end-2027, bringing the total to 274 million, while global aid funding in 2025 has fallen 30% from its 2022 peak.

telegram · zaihuapd · Nov 22, 14:09

**「Background」** El Niño is a recurring natural climate pattern in which surface waters across the central and eastern tropical Pacific become unusually warm; scientists gauge its strength by temperature readings in the central Pacific&\#x27;s Niño 3.4 zone. The resulting shifts in global rainfall, including droughts like the one Somalia faced, disrupt harvests, which is why the UN&\#x27;s World Food Programme monitors the event.

**「Impact」** Rice farmers and rice-dependent consumers face the biggest crop risk, as global rice yields have historically run about 1.0 to 1.5 percent below trend during past El Niño events, while soybean yields have tended to rise.

<details><summary>References</summary>
<ul>
<li><a href="https://science.nasa.gov/earth/explore/el-nino/">El Niño - NASA Science</a></li>
<li><a href="https://wattsupwiththat.com/2016/04/04/quicky-early-april-2016-enso-update-nino3-4-sea-surface-temperature-anomalies-still-at-the-threshold-of-a-strong-el-nino/">Quicky Early April 2016 ENSO Update: NINO 3 . 4 Sea Surface ...</a></li>
<li><a href="https://reliefweb.int/report/world/crop-monitor-special-report-el-nino-2026-2027-anticipated-climate-and-agricultural-yield-impacts-june-16-2026">Crop Monitor Special Report: El Niño 2026-2027: Anticipated ...</a></li>

</ul>
</details>

**Tags**: `#climate`, `#el-nino`, `#food-security`, `#humanitarian-aid`, `#agriculture`

---