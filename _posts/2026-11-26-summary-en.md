---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 36 items, 4 important content pieces were selected

---

**Technology News**
1. [Scott Aaronson: AI Opens a &\#x27;New Continent&\#x27; of Mathematical Truth](#item-tech-news-1) ⭐️ 9.0/10
2. [OpenAI Bets Cybersecurity Will Outgrow Coding, Backed by GPT-6 Cyber and Daybreak](#item-tech-news-2) ⭐️ 7.0/10
3. [Asian Data Centers Resell Surplus AI Compute to US Buyers After Export Crackdown](#item-tech-news-3) ⭐️ 7.0/10
4. [OpenAI Testing &\#x27;Private Inference&\#x27; With Zero Data Retention for Select Customers](#item-tech-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Scott Aaronson: AI Opens a &\#x27;New Continent&\#x27; of Mathematical Truth](https://scottaaronson.blog/?p=10379) ⭐️ 9.0/10

Theoretical computer scientist Scott Aaronson published an essay, surfaced via Hacker News on November 25, 2026, arguing that AI-driven discovery has changed in kind rather than degree: instead of one-off solutions to individual complexity questions, he now expects &quot;a whole new continent of mathematical truth,&quot; comparing the gain in resolution to Galileo first pointing a telescope at the stars or van Leeuwenhoek first aiming a microscope at pond water. The post is tied to a claimed result, circulating as a PDF and debated on Hacker News under the title &quot;The matrix multiplication exponent is nine fourths,&quot; that the matrix multiplication exponent ω equals 9/4 — implying O\(n^2.25\) matrix multiplication — a longstanding open problem in algorithms with direct relevance to ML compute. Both the exponent claim and Aaronson&\#x27;s broader assessment are unverified: the linked discussion reports the ω = 9/4 proof as pending verification, and the essay itself is an argument about significance rather than a published result.

hackernews · Kotlopou · Nov 25, 19:11 · [Discussion](https://news.ycombinator.com/item?id=50646108)

**「Background」** The matrix multiplication exponent ω describes how the cost of multiplying two square n×n matrices grows with n, and determining its exact value has been a 57-year open problem in theoretical computer science \[tool-2-3\]. Aaronson&\#x27;s post reacts to a November 24, 2026 OpenAI preprint in which an unnamed internal model argues that ω is exactly 9/4 over every field, a claim accompanied by a Lean formalization that outside reviewers have started checking against the paper&\#x27;s LaTeX source \[tool-2-1, tool-2-2\].

**「Impact」** For developers of linear-algebra libraries and ML compute stacks, the claimed result requires no immediate action: the exponent ω = 9/4 is an asymptotic complexity bound that, per current reporting, does not speed up existing hardware or shipped kernels, which already operate well above the theoretical floor. The concrete consequence, if the proof survives verification, falls on complexity theory and algorithm research — the claim of 2.25 over every field is attributed to an OpenAI preprint that remains pending peer review — rather than on any deployed system.

**「Community discussion」** The most useful disagreement in the Hacker News thread concerns what follows from AI progress in mathematics: nickysielicki argues, against the grain, that there is no present evidence AI labs have cracked real cryptosystems — an organization of that size, he reasons, could not keep such a secret without whistleblowers or leaks — while jsLavaGoat holds that proficiency in axiomatic mathematics does not entail that AI will &quot;solve&quot; other fields or pose existential risk. Taking the opposite stance, Nevermark argues humans are biologically incapable of reacting at anything near the scale the change deserves, and sunir offers a historical analogy via Bruno Latour&\#x27;s &quot;centers of calculation,&quot; noting that Tycho Brahe&\#x27;s systematic compilation of astronomical data was what enabled Kepler&\#x27;s laws.

<details><summary>References</summary>
<ul>
<li><a href="https://aiweekly.co/alerts/openai-preprint-claims-matrix-multiplication-exponent-is-94">OpenAI preprint claims matrix multiplication exponent is 9/4</a></li>
<li><a href="https://lilting.ch/en/articles/matrix-multiplication-exponent-nine-fourths-openai">Checking OpenAI&#x27;s 9/4 Matrix Multiplication Exponent Paper ...</a></li>
<li><a href="https://geekblog.net/ai-software/openai-matrix-multiplication-exponent-9-4-proof-explained/">OpenAI&#x27;s 9/4 Matrix Multiplication Proof, Explained</a></li>
<li>OpenAI preprint claims the matrix multiplication exponent is exactly 9/4</li>
<li>OpenAI pins the matrix multiplication exponent at 2.25</li>

</ul>
</details>

**Tags**: `#theoretical-computer-science`, `#matrix-multiplication`, `#artificial-intelligence`, `#algorithms`, `#mathematics`

---

<a id="item-tech-news-2"></a>
### [OpenAI Bets Cybersecurity Will Outgrow Coding, Backed by GPT-6 Cyber and Daybreak](https://www.theinformation.com/newsletters/ai-agenda/openais-roadmap-making-cyber-bigger-coding-remains-blurry) ⭐️ 7.0/10

A report from The Information, relayed via a Chinese-language summary, says OpenAI&\#x27;s leadership is betting on cybersecurity as its next growth engine, with President Greg Brockman stating that cybersecurity will become a bigger business segment for OpenAI than coding and the CFO arguing that external estimates of a cybersecurity market exceeding $300 billion still significantly understate its size. Behind that positioning, the company has launched GPT-6 Cyber for security research and is expanding its Daybreak trusted-access program, which as of September covered thousands of verified defenders and roughly 2,000 approved organizations and workspaces, supporting vulnerability discovery, codebase analysis, and binary reverse engineering. The claims and figures come from a secondhand summary of a paywalled newsletter and are not independently verified, and the report itself notes that OpenAI&\#x27;s competition with Anthropic and Google and the prospects for commercializing cybersecurity at scale remain unclear.

telegram · zaihuapd · Nov 25, 04:51

**「Background」** The comparison rests on OpenAI&\#x27;s coding business, which the report frames as a current core segment and the benchmark that cybersecurity would need to surpass. The bet builds on infrastructure OpenAI already has in place: the GPT-6 Cyber model aimed at security research and the Daybreak trusted-access program, which verifies individual defenders and approves organizations and workspaces before granting access to capabilities for vulnerability discovery, code analysis, and binary reverse engineering.

**「What this changes for security teams」** For security practitioners, part of this is already shipped rather than purely strategic: GPT-6 Cyber launched on November 5 and has been credited with surfacing 81 Firefox vulnerabilities, and Daybreak offers live tooling including the Defense Factory for connected repositories, Red Team for authorized security testing, and the Codex Security CLI and SDK. For the roughly 2000 organizations approved as of September, this puts AI-assisted vulnerability discovery, codebase analysis, and binary reverse engineering within reach today, while other teams face a concrete gating action: access requires being a verified defender or an organization approved through the Daybreak trusted-access program. Security buyers should treat the tooling as the concrete deliverable, since the projection that cybersecurity will outgrow OpenAI&\#x27;s coding business — and the CFO&\#x27;s claim that the $300 billion-plus market estimate is understated — are executive positions, with the report itself noting unclear commercialization prospects against Anthropic and Google.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=uz3LF-YBjoE">GPT - 6 Cyber : OpenAI &#x27;s New AI Found 81 Hidden Firefox... - YouTube</a></li>
<li><a href="https://openai.com/daybreak/">Daybreak | OpenAI for cybersecurity | OpenAI</a></li>
<li><a href="https://thehackernews.com/2026/11/openai-launches-gpt-6-cyber-after-ai.html">OpenAI Launches GPT - 6 Cyber After AI Helps Find 81 Firefox Flaws...</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#cybersecurity`, `#AI industry strategy`, `#LLM applications`, `#vulnerability research`

---

<a id="item-tech-news-3"></a>
### [Asian Data Centers Resell Surplus AI Compute to US Buyers After Export Crackdown](https://www.bloomberg.com/news/articles/2026-11-25/asia-data-centers-sound-out-us-clients-to-replace-china-demand) ⭐️ 7.0/10

The US government has tightened a loophole that allowed Chinese companies to obtain Nvidia&\#x27;s most advanced AI chips, and data center operators across multiple Asian markets are now racing to resell surplus compute capacity to US customers, according to Bloomberg. Ronit Jain, CEO of Liquid Compute, said the new rules on exporting advanced AI accelerators to the region are hitting providers that had planned to rent compute to Chinese clients. The item relays a paywalled Bloomberg report published November 25 and provides no figures on the volume of capacity being redirected or which markets are most affected, so the scale of the shift remains unverified.

telegram · zaihuapd · Nov 25, 11:35

**「The loophole and its closure」** Chinese AI companies had been working around US export controls by tapping advanced Nvidia computing power hosted in third countries such as Singapore, a gap US lawmakers were weighing how to close as of August 2026. The Commerce Department shut that remote-access loophole with an interim final rule in mid-November 2026, and the new rules also require data centers in Southeast Asia to seek US approval before buying advanced AI chips, threatening a regional build-out that had been fueled heavily by Chinese demand.

**「Impact on regional operators」** Data center operators in Singapore, Malaysia and the wider region now need a US license to buy advanced AI chips from manufacturers such as Nvidia, and because the new rules specifically target the region&\#x27;s role in supplying compute to Chinese companies, providers that sized capacity for Chinese demand must land US customers to avoid idle compute. The effect is already visible in markets: Reuters reported that shares of Southeast Asian data centre and chip supply chain companies tumbled after the curbs were announced, threatening the region&\#x27;s $100 billion-plus AI industry.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/08/19/china-ai-nvidia-chips-us-export-controls.html">China AI firms tap Nvidia power overseas as U.S ... - CNBC</a></li>
<li><a href="https://www.forbes.com/sites/zacharyfolk/2026/11/16/us-closes-loophole-that-allowed-china-to-remotely-access-nvidia-chips/">US Closes Loophole That Allowed China To Remotely Access ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U.S. chip curbs put Southeast Asia&#x27;s data center ... - CNBC</a></li>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U.S. chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/asia-s-data-center-hotbed-hit-by-us-chip-curbs-as-trump-visits">Asia’s Data Center Hotbed Hit by US Chip Curbs as Trump ...</a></li>
<li><a href="https://www.reuters.com/world/asia-pacific/us-ai-chip-curbs-threaten-southeast-asia-data-centre-boom-shares-tumble-2026-11-17/">US AI chip curbs threaten Southeast Asia data centre boom ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#data centers`, `#compute market`, `#tech industry`

---

<a id="item-tech-news-4"></a>
### [OpenAI Testing &\#x27;Private Inference&\#x27; With Zero Data Retention for Select Customers](https://x.com/sama/status/2125638790593274259) ⭐️ 7.0/10

Sam Altman announced on X that OpenAI is testing a Private Inference service with a small number of customers, the latest offering in its OpenAI Private Intelligence lineup. According to the post, enabling Private Safety Processing within the zero data retention \(ZDR\) scheme lets safety reviews complete automatically, with OpenAI staff unable to access the underlying content. Altman framed stronger privacy protections as a way to make frontier AI usable in more work scenarios and called enterprise data privacy important to a healthy industry ecosystem. The announcement is a brief CEO post describing a limited test, with no technical detail on how the privacy or automated safety mechanisms work, rather than a generally available or independently verified capability.

telegram · zaihuapd · Nov 26, 01:44

**「Background」** OpenAI already offers Zero Data Retention \(ZDR\), under which it does not retain eligible API customers&\#x27; prompts or responses on its frontier models, and its August 19, 2026 announcement previewed Private Safety Processing \(PSP\) as a way to run advanced safety review without compromising data privacy. OpenAI&\#x27;s developer documentation describes ZDR with PSP as enabling offline, automated safety review without retaining customer prompts or responses, and outlines operating responsibilities that remain with the customer. The newly announced Private Inference test is positioned as the latest addition to OpenAI&\#x27;s Private Intelligence line, which packages these privacy controls for enterprise use of frontier models.

**「Impact」** By letting safety review run automatically without OpenAI staff accessing underlying customer content, the test targets a specific adoption blocker for privacy-sensitive and regulated organizations that have so far kept confidential workloads off frontier models. Interested enterprises should first confirm Zero Data Retention eligibility, since OpenAI limits ZDR to eligible API customers and supported endpoints subject to applicable controls and exceptions. External reporting describes Private Safety Processing as extending ZDR safety monitoring across multi-turn interactions without exposing customer content, with a technical white paper planned, so how well abuse detection actually works without content access — the core open question in outside coverage — is not yet independently verifiable.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/offering-zero-data-retention-for-frontier-models/">Offering Zero Data Retention for frontier models - OpenAI</a></li>
<li><a href="https://openai.com/business/private-intelligence/">Private Intelligence | Frontier intelligence. Private by ...</a></li>
<li><a href="https://developers.openai.com/api/docs/guides/private-safety-processing">ZDR with Private Safety Processing | OpenAI API</a></li>
<li><a href="https://www.linkedin.com/posts/paritosh-dagar-a5bb7119_offering-zero-data-retention-for-frontier-activity-7496138682236846082-KbVM">OpenAI Zero Data Retention for Enterprise AI Models | LinkedIn</a></li>
<li><a href="https://www.brocker.org/openai-previews-private-safety-processing-zero-data-retention">OpenAI Previews Private Safety Processing for ZDR Enterprise ...</a></li>
<li><a href="https://www.contentgrip.com/openai-zero-data-retention/">Can zero - retention AI still catch harmful use?</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#AI privacy`, `#enterprise AI`, `#zero data retention`, `#inference services`

---