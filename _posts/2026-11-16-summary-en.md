---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 38 items, 5 important content pieces were selected

---

**Technology News**
1. [Meituan Open-Sources LongCat-2.5, Claims Training Used Only Huawei Ascend Chips](#item-tech-news-1) ⭐️ 8.0/10
2. [MacBook Pro Tandem OLED&\#x27;s PWM Flicker Sparks Eye-Strain and Measurement Debate](#item-tech-news-2) ⭐️ 7.0/10
3. [Meta FAIR and NYU Train 200+ MLLMs: Encoder Pretraining Optional, Vision Parameters Essential](#item-tech-news-3) ⭐️ 7.0/10
4. [FAA nationwide ground stop traced to faulty router during copper-to-fiber upgrade](#item-tech-news-4) ⭐️ 7.0/10

**Financial News**
1. [Lutnick family firm nearly halved Nvidia stake amid chip-smuggling scrutiny](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Meituan Open-Sources LongCat-2.5, Claims Training Used Only Huawei Ascend Chips](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team has released the weights of LongCat-2.5, a 1.6-trillion-parameter model with roughly 48 billion parameters activated per token, one week after the model&\#x27;s official release. The weights are published under the permissive MIT license, permitting commercial use, and the model accepts text, image, and video input. Meituan states that training ran entirely on Huawei Ascend accelerators without using any NVIDIA GPUs, though this hardware claim is self-reported and not independently verified. The company reports a Terminal Bench v2.1 score of 88.4, slightly below Claude Opus 5&\#x27;s 89.1, positioning the model for agents that autonomously complete long, multi-step tasks, particularly coding work.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5 succeeds LongCat-2.0, Meituan&\#x27;s earlier open-weights coding model of the same 1.6-trillion-parameter scale, whose weights were uploaded to Hugging Face under an MIT license after a June 30 &quot;weights coming soon&quot; placeholder — the same announce-first, release-weights-later pattern seen with the current model. Reporting on that release said LongCat-2.0 was trained on roughly 50,000 domestic Chinese accelerators, establishing the no-NVIDIA training approach that Meituan says LongCat-2.5 continues. Both models use a Mixture-of-Experts design — 1.6 trillion total parameters with about 48 billion activated per token, as listed on the model&\#x27;s Hugging Face page — meaning only a fraction of the network fires for each token.

**「Impact」** Developers and enterprises can now download, fine-tune, and commercially deploy a near-frontier agentic model under the permissive MIT license instead of relying on closed APIs — though serving the full 1.6-trillion-parameter mixture-of-experts model \(roughly 48 billion parameters active per token\) still requires substantial accelerator memory, and the reported Terminal Bench v2.1 score of 88.4 versus Claude Opus 5&\#x27;s 89.1 is vendor-reported. If Meituan&\#x27;s claim that training ran entirely on Huawei Ascend accelerators holds up, it provides a concrete data point that large-scale, frontier-adjacent model training is achievable without NVIDIA GPUs — relevant to organizations facing US chip export restrictions — but this hardware claim has not been independently verified.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/meituan-longcat/LongCat-2.5">meituan - longcat / LongCat - 2 . 5 · Hugging Face</a></li>
<li><a href="https://aicodingweekly.datadriftpress.com/p/61-longcat-edges-out-gpt-5-5">#61 - LongCat edges out GPT-5.5 | AI Coding Weekly</a></li>
<li><a href="https://www.ainchina.com/blog/meituan-longcat-2-trillion-domestic-chips-china-ai-independence-2026/">How Meituan Built a Trillion - Parameter AI Model on 50,000 Domestic...</a></li>

</ul>
</details>

**Tags**: `#large language models`, `#open source`, `#AI hardware`, `#agentic AI`, `#China tech industry`

---

<a id="item-tech-news-2"></a>
### [MacBook Pro Tandem OLED&\#x27;s PWM Flicker Sparks Eye-Strain and Measurement Debate](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

A MacAnorak analysis argues that the tandem OLED display in Apple&\#x27;s MacBook Pro uses low-frequency PWM dimming, which the article puts at around 240Hz, and that the resulting flicker can cause eye strain and headaches for sensitive users, making a technically superior panel worse to use for that group. PWM \(pulse-width modulation\) dims a screen by rapidly switching it on and off rather than reducing power, and the article reportedly also documents DC dimming behavior at certain brightness levels. The headline 240Hz figure is contested rather than settled: commenters who re-examined the underlying oscilloscope data argue the two stacked OLED panels each run at 480Hz, 180 degrees out of phase, yielding an effective 960Hz at most usable brightness levels. No independent measurements in the discussion corroborate either figure, and the share of users affected by PWM sensitivity is not well quantified.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「Background」** Pulse-width modulation \(PWM\) controls screen brightness by rapidly switching a display on and off rather than lowering the drive current \(DC dimming\), and although the resulting flicker is invisible to most people, low PWM frequencies have long been a suspected cause of headaches and eye strain in a minority of sensitive users, especially on OLED phones. The MacBook Pro display at issue uses tandem OLED, meaning two stacked light-emitting layers driven together to reach higher brightness, which makes the effective flicker frequency depend on how the two layers&\#x27; pulses overlap in phase. This overlap behavior is precisely what is contested in the article&\#x27;s measurement debate, with commenters disputing whether the panel truly runs at 240 Hz or effectively at 480/960 Hz when both layers are active.

**「Impact on flicker-sensitive users」** For flicker-sensitive users, upgrading from a mini-LED or LCD MacBook Pro could be a usability regression: Notebookcheck measured about 240 Hz PWM on the OLED model, versus roughly 14,880 Hz on the previous mini-LED panels, and its review explicitly flags the 240 Hz flicker as a potential problem for sensitive users despite the panel&\#x27;s DC dimming. Because sensitivity varies from person to person, affected buyers should test the display in person before purchasing or keep their high-frequency-dimming model.

**「Community discussion」** The sharpest disagreement is over the frequency itself: commenter legitronics re-read the article&\#x27;s raw scope data and argues it shows 480Hz per panel with the two tandem OLED layers 180 degrees out of phase, for an effective 960Hz, rather than the claimed 240Hz. Others add reported experience and external context, with achr2 citing a Nature Scientific Reports paper as showing humans can perceive flicker at more than twice the display&\#x27;s rate, and explosion-s, who describes post-concussion screen sensitivity, noting symptoms triggered by screens generally rather than bright OLEDs specifically.

<details><summary>References</summary>
<ul>
<li><a href="https://www.notebookcheck.net/Amazing-OLED-panel-Apple-MacBook-Pro-14-PROLED-XDR-Review.1438048.0.html">Amazing OLED panel - Apple MacBook Pro ... - Notebookcheck Review</a></li>
<li><a href="https://www.youtube.com/watch?v=sGgowKoztzk">Is the PROLED ( OLED ) MacBook Pro a Disaster? Flicker ... - YouTube</a></li>
<li><a href="https://www.macrumors.com/2023/01/10/oled-macbook-kuo/">Kuo: Apple&#x27;s First MacBook With an OLED Display to... - MacRumors</a></li>

</ul>
</details>

**Tags**: `#hardware`, `#displays`, `#oled`, `#pwm-flicker`, `#apple`

---

<a id="item-tech-news-3"></a>
### [Meta FAIR and NYU Train 200+ MLLMs: Encoder Pretraining Optional, Vision Parameters Essential](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 7.0/10

A Meta FAIR and NYU study \(paper 2611.17334, shared on Reddit by a co-author\) reports training 200+ multimodal LLMs from scratch — LLM included — on identical data, with encoder pretraining counted against the same lifetime-compute budget, to separately test three bundled vision-encoder design choices; main comparisons use Qwen3-1.7B and 4B configurations with 0.4B parameters of vision capacity, a 0.6B–6.4B scaling ladder, 16 Cambrian VQA benchmarks at 448 px, and 12 language benchmarks. The authors find separate encoder pretraining optional: encoders pretrained with four objectives \(contrastive, self-supervised, two captioning variants\) at best tie an encoder trained from scratch alongside the LLM at matched compute, and pretraining MetaCLIP 6.5× longer raised ImageNet linear-probe accuracy from 80.4% to 84.4% without improving VQA. Vision-only parameters, by contrast, were required: encoder-free models trailed at every size from 0.6B to 6.4B and needed roughly 3× the compute to catch up, and giving the encoder&\#x27;s parameters to the LLM instead improved text benchmarks but not VQA. Placement before the LLM was also optional: an &\#x27;in-fusion&\#x27; variant adding zero-initialized vision-only attention projections and FFNs to the LLM&\#x27;s first 8 layers matched a standard encoder from 1.7B to 6.4B with about 13% lower time to first token \(45.0 vs. 44.4 VQA at 1.7B, vs. 42.3 when text shares those weights and 35.1 when placed in the last 8 layers\), and the result held when vision was added to a pretrained 1.7B LLM during midtraining.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Background」** Most multimodal LLMs send images through a vision encoder that is pretrained separately — typically with contrastive or captioning objectives — and then feed the resulting visual tokens into the language model, a design that bundles three distinct decisions: separate encoder pretraining, parameters used only by vision tokens, and encoder placement ahead of the LLM. According to the post, frontier labs currently disagree on these choices, with Gemma 4 12B dropping the encoder entirely, Kimi K3 training its encoder from scratch, and Inkling 2 Small bringing an encoder back. Published models cannot settle the debate because they differ in training data, compute, and whether encoder pretraining costs are counted at all.

**「Implications for MLLM design」** For teams designing multimodal models, the reported evidence argues that compute spent pretraining a separate vision encoder can be redirected to joint training, and that &\#x27;in-fusion&\#x27; placement offers encoder-level VQA at about 13% lower time to first token — relevant to a live split the post describes, in which Gemma 4 12B dropped its encoder, Kimi K3 trains one from scratch, and Inkling 2 Small restored one. The main caution for encoder-free architectures is cost: at the tested scales they needed roughly 3× the compute for parity. These results are author-reported via Reddit and the linked paper and have not been independently verified here.

**Tags**: `#machine-learning`, `#multimodal-models`, `#vision-encoders`, `#research-paper`, `#empirical-study`

---

<a id="item-tech-news-4"></a>
### [FAA nationwide ground stop traced to faulty router during copper-to-fiber upgrade](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

US Transportation Secretary Sean Duffy said on November 14 that the FAA&\#x27;s nationwide ground stop on Friday, which halted thousands of flights, began during routine maintenance at a remote facility that was replacing aging copper wiring with fiber. According to Duffy, a newly installed router then malfunctioned and flooded other routers with more than 1,000 connection requests every 4 to 5 seconds, disrupting radar signals and communications with aircraft. He said the root cause remains undetermined — possibilities include a hardware failure, a configuration error, or a mistake by contractor L3Harris — and urged Congress to approve additional funding for air traffic control modernization. These details are the Secretary&\#x27;s account of the incident, not an independent technical finding.

telegram · zaihuapd · Nov 15, 02:10

**「Background」** The cause disclosure follows the FAA&\#x27;s nationwide ground stop ordered on Friday, which halted U.S. departures for more than four hours and left thousands of flights canceled or delayed, with airlines still recovering on Saturday \(tool-2-2\). In follow-up remarks, Transportation Secretary Sean Duffy said routers at facilities in Arkansas and Texas are under investigation, while the router manufacturer stated the devices &quot;did not fail&quot; and officials reported no sign of a cyberattack — leaving the root-cause question contested between the government and the vendor \(tool-2-3\).

**「Impact」** The disruption hit travelers at national scale: it was the longest nationwide ground stop in roughly 25 years, with thousands of flights canceled in its wake. Transportation Secretary Sean Duffy is now pressing Congress to approve $50 billion in emergency funding to replace outdated routers and switches across the air traffic control system. The risk is also ongoing rather than a one-off — the FAA&\#x27;s aging infrastructure has suffered several disruptive failures in recent months, including during upgrade work such as the copper-to-fiber conversion that triggered this outage, so similar maintenance on the legacy network can plausibly cause repeat incidents.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247">FAA lifts ground stop hours after stranding thousands of flights...</a></li>
<li><a href="https://www.yahoo.com/news/us/live/faa-ground-stop-latest-updates-duffy-blames-contractor-l3harris-thousands-more-flights-canceled-saturday-no-sign-of-cyberattack-161329174.html?fr=sycsrp_catchall">FAA ground stop latest updates: Duffy says routers in Arkansas...</a></li>
<li><a href="https://www.foxnews.com/live-news/thousands-of-flights-canceled-after-longest-nationwide-ground-stop-in-25-years-rocks-us-airports">Thousands of flights canceled in wake of FAA ground stop</a></li>
<li><a href="https://www.foxbusiness.com/politics/duffy-sounds-alarm-over-aging-faa-system-after-nationwide-air-travel-shutdown">Sean Duffy demands $50B to rebuild aging air traffic control system</a></li>
<li><a href="https://www.nytimes.com/2026/11/14/us/politics/ground-stop-air-traffic-faa.html">Ground Stop Highlights Chronic Vulnerabilities in Air Traffic System</a></li>

</ul>
</details>

**Tags**: `#networking`, `#infrastructure-outage`, `#aviation`, `#hardware`, `#critical-infrastructure`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Lutnick family firm nearly halved Nvidia stake amid chip-smuggling scrutiny](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 8.0/10

CNBC reported that Cantor Fitzgerald, the Wall Street firm led by Commerce Secretary Howard Lutnick&\#x27;s sons, cut its reported Nvidia holding by 49% — from $652 million in September 2025 to $310 million by March 2026 — during a period when, according to Axios, Lutnick resisted White House and intelligence officials&\#x27; pressure to crack down on Megaspeed, a Singapore-based firm suspected of funneling Nvidia AI chips to China. CNBC stressed there is no evidence the share changes were tied to any intelligence warnings or that the firm&\#x27;s interests influenced Lutnick&\#x27;s decisions, and Cantor said the holdings stemmed from routine client swap transactions.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Nvidia CEO Jensen Huang resigned on Nov. 12 amid a scandal over his alleged ties to a suspected Chinese spy, with CFO Colette Kress named interim chief. Howard Lutnick ran Cantor Fitzgerald before becoming commerce secretary in February 2025, a post that oversees U.S. export controls, including the &quot;entity list&quot; of foreign companies barred from buying American technology; his sons Brandon and Kyle now lead the firm.

**「Impact」** Whether Singapore-based Megaspeed is added to the U.S. entity list — the government&\#x27;s register of firms barred from buying American exports — now rests with Lutnick&\#x27;s Commerce Department, and a listing would cut off a suspected channel for Nvidia&\#x27;s AI chips into China; Treasury, Defense, State and the USTR said they had favored the move for months.

<details><summary>References</summary>
<ul>
<li><a href="https://www.npr.org/2026/11/12/nx-s1-6037833/jensen-huang-nvidia-stepped-down">Nvidia CEO Jensen Huang resigns amid spy scandal : NPR</a></li>
<li><a href="https://www.bbc.com/news/articles/cmdx1vpprk9vo">Suspected China spy linked to Nvidia &#x27;s ex-boss left in 2025...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#conflict of interest`, `#export controls`, `#national security`, `#Trump administration`

---