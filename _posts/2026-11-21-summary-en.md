---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 39 items, 17 important content pieces were selected

---

**Technology News**
1. [Tao Reports Unforced Navier–Stokes Singularity and Claimed Lean Proof of GRH](#item-tech-news-1) ⭐️ 10.0/10
2. [Anthropic Mathematician Claims Claude-Assisted Lean Proof of Riemann Hypothesis](#item-tech-news-2) ⭐️ 9.0/10
3. [Thinking Machines Releases Open-Weights Looped Transformer Inkling 2 Mini](#item-tech-news-3) ⭐️ 8.0/10
4. [Buckmaster Preprint Claims Finite-Time Blow-Up for Unforced Navier–Stokes](#item-tech-news-4) ⭐️ 8.0/10
5. [KVM Flaw CVE-2026-99312 Exposes AMD Host Memory to Guest VMs](#item-tech-news-5) ⭐️ 8.0/10
6. [TSMC reportedly suspends Chinese orders for 16nm-and-below chips](#item-tech-news-6) ⭐️ 8.0/10
7. [Hurried Release of Masullo&\#x27;s Claimed 940-Page GRH Proof Draft](#item-tech-news-7) ⭐️ 7.0/10
8. [Paper Claims LLM Can Rewrite Its Own Weights Without Gradient Training](#item-tech-news-8) ⭐️ 7.0/10
9. [SEC&\#x27;s Nvidia Probe Examining Potential Accounting Issues, Sources Say](#item-tech-news-9) ⭐️ 7.0/10
10. [Signal Publishes Measures to Block OS AI Agents From Reading Private Chats](#item-tech-news-10) ⭐️ 7.0/10
11. [Scott Aaronson skeptically examines claim an LLM proved the Riemann Hypothesis](#item-tech-news-11) ⭐️ 7.0/10
12. [Apple Reportedly Building AI Agent for Coding, Browsing, and App Control](#item-tech-news-12) ⭐️ 7.0/10
13. [OpenAI launches background mode: 8-hour async tasks at up to 40% off tokens](#item-tech-news-13) ⭐️ 7.0/10

**Technology Blog**
1. [Why Output Caching Doesn&\#x27;t Work for LLM Agents](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Prediction-Market Odds of S&amp;P 500 Hitting 8,000 in 2026 Slump Amid AI Sell-Off](#item-finance-news-1) ⭐️ 7.0/10
2. [Fed officials talk more, not less, as Chair Warsh withholds rate guidance](#item-finance-news-2) ⭐️ 7.0/10
3. [U.S. Companies Turn From Buying Back Shares to Selling Them](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Tao Reports Unforced Navier–Stokes Singularity and Claimed Lean Proof of GRH](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 10.0/10

Terence Tao&\#x27;s November 20, 2026 blog post reports two results on Clay Millennium-class problems: a singularity for the unforced Navier–Stokes equations \(no external forcing, the setting of the Clay existence-and-smoothness problem\) and an apparent proof of the Generalized Riemann Hypothesis, the extension of the Riemann Hypothesis to Dirichlet L-functions; the post&\#x27;s title also lists an unforced Euler singularity. According to the Hacker News thread, the Riemann argument is formalized in the Lean proof assistant, with Tao quoted as saying it &quot;appears to use the full power of modern developments on the Langlands program and arithmetic geometry.&quot; One commenter linking the Lean Zulip discussion reports that two independent verification kernels accepted the result, which would make exploitation of a kernel bug unlikely. The underlying post was not available to this digest, so these extraordinary claims — including the degree of AI involvement that commenters assume — could not be independently verified here.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** The Navier–Stokes existence and smoothness problem — whether solutions of the three-dimensional incompressible equations can develop a singularity in finite time — is one of the Clay Millennium Prize Problems, and the Riemann hypothesis that the Generalized Riemann Hypothesis extends is another. The announcement follows an earlier claim posted to alphaXiv on September 8, 2026, in which an internal OpenAI system released a writeup and a Lean formalization arguing that Navier–Stokes dynamics blow up in finite time. Tao&\#x27;s new post concerns the unforced equations, meaning no external forcing term is applied, and the results again come with Lean formalizations — the machine-checkable proof format also used in the September release.

**「Impact」** Both results sit squarely within the Clay Mathematics Institute&\#x27;s Millennium Prize Problems, each carrying a $1 million award, and Tao&\#x27;s unforced Navier–Stokes result addresses the formulation that was still listed as open: OpenAI&\#x27;s earlier solution covered only the forced case and OpenAI stated it would not claim the prize, while the no-external-force case remained unsolved \(tool-3-1, tool-3-2\). If the Generalized Riemann Hypothesis proof is confirmed, the review burden for mathematicians shifts from checking the argument itself to checking that the formalized statement faithfully encodes the hypothesis, since a commenter citing the Lean Zulip thread reports that two independent Lean kernels already accept the proof — a community report rather than an audited finding.

**「Community discussion」** The clearest technical point came from chunky1994, who linked the Lean Zulip thread and argued that acceptance by two independent kernels makes a kernel-bug exploitation of the proof unlikely; softwaredoug raised the opposite concern, asking how genuinely new abstractions comparable to the Langlands program itself could ever emerge from brute-force proof generation and verification over existing concepts. Several commenters, including sega\_sai and actusual, described feeling frightened that AI has surpassed human researchers — a personal reaction rather than an established fact about how the results were produced.

<details><summary>References</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Euler singularity, unforced Navier-Stokes ...</a></li>
<li><a href="https://www.alphaxiv.org/abs/2609.navier-stokes-solution">On the Navier–Stokes Millennium Prize Problem | alphaXiv</a></li>
<li><a href="https://conyso.com/lawtome/wild/unforced-navier-stokes-blow-up-alpoge-buckmaster/">Has the Navier-Stokes Problem Been Solved Without a Force?</a></li>
<li><a href="https://en.wikipedia.org/wiki/Millennium_Prize_Problems">Millennium Prize Problems - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier–Stokes existence and smoothness - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#riemann-hypothesis`, `#navier-stokes`, `#formal-verification`, `#ai-research`

---

<a id="item-tech-news-2"></a>
### [Anthropic Mathematician Claims Claude-Assisted Lean Proof of Riemann Hypothesis](https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/) ⭐️ 9.0/10

Anthropic mathematician Levent Alpöge announced on November 20 that, working with Claude, he has discovered a proof of the Riemann Hypothesis — the 1859 problem concerning the distribution of primes — and that the method extends to the Generalized Riemann Hypothesis, with the Extended Riemann Hypothesis expected to follow. The argument has been formalized in the Lean proof language &\#x27;without assumptions,&\#x27; with a write-up Alpöge describes as exceeding 250,000 pages; community inspection of the download puts it at roughly 1.3 GB across 14 parts. The claim is still an unverified announcement rather than an accepted result: MIT&\#x27;s Andrew Sutherland has begun independent formal-verification checks \(run with Claude Code, last updated November 20\), but completion and acceptance by the mathematics community were pending at publication time.

telegram · zaihuapd · Nov 20, 15:29

**「Background」** Posed by Bernhard Riemann in 1859, the Riemann Hypothesis concerns the distribution of prime numbers and has remained unproven for 167 years, making it one of the most celebrated open problems in mathematics. The claimed proof was released in Lean, a programming language and proof assistant that mechanically verifies the mathematical correctness of each argument, which in principle allows the result to be checked without relying on traditional human peer review.

**「Impact」** If the Lean-formalized argument passes independent verification, it would settle the Riemann hypothesis, one of the seven Clay Millennium Prize Problems. Because Alpöge&\#x27;s proof establishes the generalized Riemann hypothesis \(GRH\), confirmation would turn the strong bounds that hypothesis implies for the distribution of primes and related arithmetic functions, such as the Möbius function, into unconditional results, letting number theorists replace &quot;assuming GRH&quot; conditions in existing work with proved theorems. Until the roughly 15-million-line Lean codebase is fully checked, results conditional on GRH should still be treated as provisional.

**「Community Discussion」** Verification was the central argument in the comments: dawdler-purge contended that Andrew Sutherland&\#x27;s ongoing formal checks leave &\#x27;no doubt&\#x27; the proof is correct, while Jaxan noted a separate, purely human &\#x27;hurried announcement&\#x27; of a Generalized Riemann Hypothesis proof posted the same day, and z7 quoted Terence Tao saying a month earlier that current AI &\#x27;couldn&\#x27;t touch&\#x27; the Riemann Hypothesis. djoldman supplied practical evidence of the scale, reporting the Lean formalization at about 1.3 GB and roughly 15 million lines of code across 14 downloadable parts.

<details><summary>References</summary>
<ul>
<li><a href="https://interestingengineering.com/ai-robotics/anthropic-167-year-old-riemann-hypothesis-claude">Claude helped prove 167-year-old Riemann hypothesis , researcher...</a></li>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.scientificamerican.com/article/what-the-riemann-hypothesis-proof-really-means-about-ai-and-the-future/">What the Riemann hypothesis proof really... | Scientific American</a></li>
<li><a href="https://www.claymath.org/millennium-problems/">The Millennium Prize Problems - Clay Mathematics Institute</a></li>

</ul>
</details>

**Tags**: `#artificial-intelligence`, `#mathematics`, `#formal-verification`, `#large-language-models`, `#research-news`

---

<a id="item-tech-news-3"></a>
### [Thinking Machines Releases Open-Weights Looped Transformer Inkling 2 Mini](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 8.0/10

Thinking Machines has released Inkling 2 Mini, an open-weights model that openly embraces a looped transformer architecture and was trained end-to-end in nvfp4, a 4-bit floating-point format, per a team note quoted in the release discussion. Commenters report benchmark results comparable to the much larger Qwen3.8-27B, though these are third-party claims that have not been independently verified. The model is already running locally: one user measured 27 tokens/s decode on a Ryzen 395 via llama.cpp&\#x27;s Vulkan backend, and another reported about 10 tokens/s with a q4 quantization on a 32GB M1 Pro MacBook.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Background」** A looped transformer re-runs its middle layers multiple times, spending more computation on each token instead of stacking more layers, and Thinking Machines presents this design as more monitorable as well as more efficient. NVFP4 is a 4-bit floating-point quantization format, and Inkling 2 Mini was trained end-to-end in NVFP4 rather than quantized after training, which is why local runtimes need explicit looped-layer and per-expert NVFP4 support. The model itself is a 26.4B-parameter mixture-of-experts with 5.4B parameters active per token, sized so that only the active portion drives inference cost on consumer hardware.

**「Impact」** Local inference is immediately practical but partially dependent on unreleased tooling: the faster llama.cpp setups rely on several unmerged pull requests plus a small patch that one user says yields roughly a 30% speed boost, so users on mainstream builds will see lower performance until those changes land.

**「Community Discussion」** Much of the discussion centered on the openly acknowledged looped architecture: lilytweed contrasted it with GPT Astra 6+ and Sol 6.1+, which are only heavily rumored to be looped, predicted that most open models will follow suit, and raised unresolved questions about safety and interpretability at this level of availability. Enthusiasm remained conditional — montroser called the results &quot;bonkers good&quot; only if the benchmarks hold up in real-world scenarios.

<details><summary>References</summary>
<ul>
<li><a href="https://thinkingmachines.ai/news/inkling-2-mini/">Introducing Inkling 2 Mini - Thinking Machines Lab</a></li>
<li><a href="https://unsloth.ai/docs/models/inkling-2-mini">Inkling 2 Mini - Run Locally Guide | Unsloth Documentation</a></li>
<li><a href="https://ollama.com/library/inkling-2-mini">inkling - 2 - mini</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#llm`, `#open-weights`, `#local-inference`, `#model-release`

---

<a id="item-tech-news-4"></a>
### [Buckmaster Preprint Claims Finite-Time Blow-Up for Unforced Navier–Stokes](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A preprint released on Tristan Buckmaster&\#x27;s GitHub repository \(tristanbuckmaster/navier-stokes\) claims a finite-time blow-up solution for the unforced Navier–Stokes equations, which — if verified — would negatively resolve the Clay Millennium Prize problem on Navier–Stokes existence and smoothness. As of the Hacker News discussion on November 20, 2026, the work exists only as a GitHub-released manuscript with no peer review or independent verification reported. Commenters credit Buckmaster and Alpoge as the authors, and distinguish the claim from a recent OpenAI result that, according to those comments, achieved blow-up only for the forced equations using a carefully designed external force.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Background」** The Navier–Stokes existence and smoothness problem, one of the seven Clay Millennium Prize Problems, asks whether solutions of the equations governing viscous fluid flow can develop singularities in finite time from smooth initial data. On 8 September 2026, OpenAI announced a blow-up construction for the forced version of the equations, in which a smooth external force drives the singularity; roughly twelve hours earlier, Tristan Buckmaster had issued a statement on behalf of himself and partly Levent Alpöge, setting off a priority controversy over who had the result first. The present paper targets the harder unforced case, claiming blow-up with no external force acting on the fluid.

**「Impact」** For PDE and fluid-dynamics researchers, a verified proof would resolve the Clay existence-and-smoothness Millennium Problem in the negative—smooth solutions of the unforced equations genuinely blow up in finite time—which would end the decades-long search for a global-regularity proof and redirect effort toward classifying blow-up behavior. The concrete near-term action is expert scrutiny: the argument is circulating as a GitHub-released preprint rather than a peer-reviewed paper, and Millennium-scale claims typically take years to check. It also lands on the same day as a separate, unverified claim by Anthropic mathematician Levent Alpöge to have proved the Riemann hypothesis with Claude, giving the mathematical community two landmark proofs to vet simultaneously.

**「Community discussion」** Commenters mostly contextualize rather than celebrate: tancop argues OpenAI&\#x27;s earlier example needed a designed external force, making the unforced claim &quot;more realistic&quot;, while ninkendo and Ericson2314 ask whether a real-time simulation or physical demonstration of the blow-up will be feasible. jrflo contends that OpenAI&\#x27;s earlier announcement scooped Buckmaster and Alpoge, and xianshou treats a same-day, unverified generalized Riemann Hypothesis claim as making this &quot;only the second-biggest result of the day&quot;.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://officechai.com/ai/tristan-buckmaster-levent-alpoge-claim-proof-of-navier-stokes-millennium-prize-problem-without-forcing/">Tristan Buckmaster, Levent Alpöge Claim Proof Of Navier ...</a></li>
<li>Anthropic mathematician claims AI-assisted proof of the Riemann ...</li>
<li>Anthropic mathematician claims Riemann hypothesis proof with ...</li>

</ul>
</details>

**Tags**: `#mathematics`, `#navier-stokes`, `#fluid-dynamics`, `#millennium-prize-problems`, `#research`

---

<a id="item-tech-news-5"></a>
### [KVM Flaw CVE-2026-99312 Exposes AMD Host Memory to Guest VMs](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

A Linux KVM vulnerability, CVE-2026-99312, allows virtual machines running on AMD hosts with nested virtualization enabled to read host memory; according to the report, researchers read roughly 127 GB of host memory from inside a VM on DigitalOcean. The upstream fix shipped on November 18 with stable kernel 7.3.5 and related releases, but Debian and Ubuntu distribution kernels have not yet been patched. Until distributions pick up the fix, disabling nested virtualization serves as a workaround.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** KVM \(Kernel-based Virtual Machine\) is the hypervisor built into the Linux kernel and is widely used by cloud providers, where keeping guest virtual machines isolated from host memory is the core security boundary of shared servers. Nested virtualization — an optional feature that lets a guest VM itself host further virtual machines — is the precondition here: Red Hat&\#x27;s advisory on this CVE explains that exploitation requires nested virtualization on AMD-based KVM hosts, where a malicious actor with access to a nested guest can trigger processor reset emulation while memory paging is disabled, leaving the memory management unit in an inconsistent state.

**「Impact」** For operators of AMD KVM hosts with nested virtualization enabled, especially public or multi-tenant clouds, a root user inside an untrusted guest can reportedly read and write host memory, so an unpatched host risks full compromise rather than mere information disclosure. Because the fix remained unpatched across all major Linux distributions as of disclosure, the practical action is to disable nested virtualization on AMD hosts until a patched kernel \(7.3.5 or later\) is deployed and the host rebooted.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html">Linux KVM Flaw CVE-2026-99312 Lets Guest VMs Access Host ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99312">CVE-2026-99312 - Red Hat Customer Portal</a></li>
<li>Linux KVM CVE-2026-99312 Guest Escape: Patching and Hunting</li>
<li>CVE-2026-99312: Linux KVM Hypervisor Escape Exposes Host ...</li>

</ul>
</details>

**Tags**: `#virtualization`, `#security vulnerability`, `#Linux kernel`, `#AMD`, `#cloud security`

---

<a id="item-tech-news-6"></a>
### [TSMC reportedly suspends Chinese orders for 16nm-and-below chips](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

TSMC has notified customers that it is suspending orders for 16nm-and-below process chips from Chinese companies, according to an AppleInsider report relayed via Telegram. Under the tightened US semiconductor export rules, supply now requires a prior US export license or exemption, and Apple, AMD, and Nvidia are reportedly on the US-approved list while no Chinese company is. Chinese customers are consequently said to be limited to older nodes such as 28nm and 40nm and cut off from the high-bandwidth memory needed for AI data centers. TSMC stated it will comply with the new rules; because the item is a secondhand summary, details such as the node threshold could not be independently verified.

telegram · zaihuapd · Nov 21, 02:01

**「Background」** TSMC&\#x27;s advanced-process business with China has been governed by US semiconductor export rules, which set the conditions under which it may supply Chinese customers. Previously, TSMC could itself evaluate whether a customer&\#x27;s chip design qualified for an exemption; the tightened rules shift this to a pre-application process in which customers must seek US approval in advance, which is the change that reportedly triggered the suspension.

**「Impact」** For Chinese AI hardware developers, the suspension removes foundry access to 16nm-and-below processes, the nodes advanced logic requires, leaving 28nm/40nm-class legacy processes and no reported path to AI-datacenter-grade high-bandwidth memory unless they obtain a US license or exemption — something no Chinese company has reportedly received so far.

**Tags**: `#semiconductors`, `#export-controls`, `#TSMC`, `#US-China tech tensions`, `#AI hardware`

---

<a id="item-tech-news-7"></a>
### [Hurried Release of Masullo&\#x27;s Claimed 940-Page GRH Proof Draft](https://math216.wordpress.com/2026/11/20/hurried-announcement-alessandro-masullo-grh/) ⭐️ 7.0/10

On November 20, 2026, Ravi Vakil announced on the math216 blog that Alessandro Masullo has a proposed proof of the Generalized Riemann Hypothesis \(GRH\), releasing the roughly 940-page draft immediately instead of after the originally planned year at Stanford to polish the writing and run it past more mathematicians. Vakil writes that Brian Conrad has been examining the proof closely for months, that his extensive feedback is still being incorporated, that it is &quot;so far looking good,&quot; and that the work is entirely human with no AI involvement. The hurried release came amid competing GRH claims — the post links to Levent Alpöge&\#x27;s separately announced proof — and the draft itself remains unpolished and unverified, with readers noting that its opening subsections are empty.

hackernews · jasondavies · Nov 20, 18:33 · [Discussion](https://news.ycombinator.com/item?id=50579568)

**「Background」** The Generalized Riemann Hypothesis extends the classic Riemann Hypothesis on the distribution of prime numbers to a broader class of L-functions and remains one of mathematics&\#x27; most consequential open problems. Masullo, a 2019 Stanford PhD who studied under Brian Conrad, spent roughly 12 years on the 940-page draft, &quot;The Music of the Primes,&quot; which Conrad had been reviewing closely for months before the release. Vakil published the draft ahead of schedule because a competing GRH proof claim surfaced the same day — Levent Alpöge&\#x27;s, reported as a Lean-formalized artifact built with Claude — which commenters described as an Anthropic announcement.

**「Impact」** The timing itself is the concrete consequence: Vakil states the draft was pulled forward from a planned year of polishing at Stanford, apparently in response to Levent Alpöge&\#x27;s same-day claim at Anthropic of a Claude-assisted proof of the Riemann hypothesis, so number theorists now face two large unverified manuscripts to check instead of one. Verifying Masullo&\#x27;s claim is harder because the hurried draft is unfinished — readers report 940 pages with an empty opening subsection — and Vakil notes that Brian Conrad&\#x27;s feedback is still being incorporated, so neither proof currently has independent verification. Among commenters, one proposed response is for mathematicians to publish timestamped hashes of in-progress work to preserve priority against AI-assisted discoveries, though that remains a suggestion rather than an established practice.

**「Community Discussion」** Commenters focused on the race for priority: Aurornis argued that publishing the draft within hours was the only way for Masullo — whose manuscript, per the comment, says he worked on the problem for 12 years — to claim a share of the discovery, while Kotlopou flagged that the draft&\#x27;s very first subsection is empty, though Brian Conrad&\#x27;s involvement \(described as having worked with Andrew Wiles on Fermat&\#x27;s Last Theorem\) lends it credibility. prometheus1992 speculated without evidence that portions of the manuscript might have reached Anthropic through uploads, and rlt proposed that mathematicians routinely publish timestamped hashes of in-progress work to secure partial credit if an AI system solves their problem first.

<details><summary>References</summary>
<ul>
<li><a href="https://explainx.ai/blog/alessandro-masullo-grh-human-proof-claimed-vs-verified-november-2026">Masullo GRH Draft: What Vakil Announced (Nov 20) | explainx ...</a></li>
<li><a href="https://xenospectrum.com/en/masullo-riemann-proof-draft-release/">Draft Proof of the Generalized Riemann Hypothesis, 12 Years ...</a></li>
<li><a href="https://x.com/i/trending/2123859232806064131">Mathematician Claims Proof of Generalized Riemann Hypothe...</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis ...</a></li>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis ...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#generalized-riemann-hypothesis`, `#ai-capabilities`, `#proof-verification`, `#research-news`

---

<a id="item-tech-news-8"></a>
### [Paper Claims LLM Can Rewrite Its Own Weights Without Gradient Training](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

An arXiv preprint \(2611.21885\) claims that, for the first time, a language model rewrote its own weights through its own reasoning and became better, with no gradients and no conventional training. According to the authors, the model proposes candidate weight edits, tests them on practice problems, submits only the edits that help, and its accuracy rose across eight consecutive self-editing sessions. These are author-reported preprint results, not peer-reviewed or independently replicated findings.

hackernews · lwhsiao · Nov 20, 16:29 · [Discussion](https://news.ycombinator.com/item?id=50577265)

**「Background」** Under the standard paradigm the paper positions itself against, a language model is trained once and then frozen: further improvement requires either another gradient-based training run or inference-time aids like prompts and harnesses, whose gains disappear once the task ends. A related capability had already been demonstrated by Google&\#x27;s &quot;sleep&quot; framework, described on October 27, 2026, in which a deployed model periodically unlocks pre-allocated Mixture-of-Experts memory blocks and updates its numerical weights using self-generated practice examples to absorb new facts without a full retraining pipeline — a point raised by commenters as prior work.

**「Community discussion」** Hacker News commenters questioned both the substance and the novelty of the claim: one argued that the model&\#x27;s only successful self-improvement was shortening its reasoning traces to avoid hitting a token limit, and another noted that Google&\#x27;s Sleep framework had already updated model weights using self-generated practice examples. Others contended that &\#x27;submitting only what works&\#x27; on practice problems is functionally a selection-based training loop despite the paper&\#x27;s framing, while one commenter argued the capability is safety-relevant because an autonomous model could similarly locate and suppress safety-related activations in its own weights.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.21885">[2611.21885] Language Models Can Rewrite Their Own Weights</a></li>
<li><a href="https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/">The sleep framework: A new way for LLMs to retain knowledge ...</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#language-models`, `#self-modification`, `#ai-safety`, `#research`

---

<a id="item-tech-news-9"></a>
### [SEC&\#x27;s Nvidia Probe Examining Potential Accounting Issues, Sources Say](https://www.marketscreener.com/news/us-sec-s-nvidia-probe-is-examining-potential-accounting-issues-sources-say-ce785ed3dd8ff627) ⭐️ 7.0/10

A report dated November 20, 2026 and attributed to unnamed sources says the U.S. Securities and Exchange Commission&\#x27;s probe of Nvidia is examining potential accounting issues at the AI-chip company. For Nvidia and its investors, the claim carries a major limitation: it is anonymously sourced, the available material contains only the headline rather than article text, and no findings, charges, or statements from the SEC or Nvidia are cited. Commenters in the linked Hacker News thread state that longtime CFO Colette Kress is currently serving as Nvidia&\#x27;s interim CEO, a detail the supplied material does not independently verify.

hackernews · ftchd · Nov 20, 20:22 · [Discussion](https://news.ycombinator.com/item?id=50581438)

**「Days after Nvidia&\#x27;s abrupt CEO transition」** On November 12, 2026, Nvidia announced that Jensen Huang had resigned as president and CEO, and that executive vice president and CFO Colette Kress was appointed interim CEO until a permanent successor is found. The reported SEC examination of potential accounting issues emerges roughly a week after that leadership change, placing the company&\#x27;s finance function — previously led by the new interim CEO — at the center of both the probe and the succession.

**「Impact」** The immediate consequence has fallen on shareholders: Nvidia shares extended a record sell-off that has erased roughly $2.7 trillion in market value after Reuters reported that SEC investigators are examining the company&\#x27;s accounting. The probe also adds to the legal problems already facing the chipmaker, and because the scrutiny targets how revenue is booked rather than a single product line, its eventual outcome bears directly on the reliability of the reported financials that institutional investors and index funds depend on.

**「Community discussion」** Commenters converge on two arguments: eyeat contends that Nvidia&\#x27;s arrangements with neocloud customers amount to &\#x27;circular financing&\#x27; that has &\#x27;plagued&\#x27; the company for five years and that renegotiating those usage deals could backfire, while ralph84 and treebeard901 question why the board elevated CFO Colette Kress \(CFO since 2013\) to interim CEO if accounting problems are suspected, with treebeard901 arguing the finance department would necessarily have booked any undisclosed &\#x27;blackmarket&\#x27; chip-sales revenue. These are commenter opinions and speculation; no SEC findings or confirmed subjects of investigation appear in the discussion.

<details><summary>References</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/12/nvidias-jensen-huang-resigns-chipmaker-names-cfo-colette-kress-as-interim-ceo/">Nvidia’s Jensen Huang resigns, chipmaker names CFO Colette ...</a></li>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition">NVIDIA Announces CEO Transition | NVIDIA Newsroom</a></li>
<li><a href="https://www.reuters.com/world/us-secs-nvidia-probe-is-examining-potential-accounting-issues-sources-say-2026-11-20/">Nvidia&#x27;s accounting is a focus of US SEC investigation ...</a></li>
<li><a href="https://finance.yahoo.com/markets/article/nvidia-stock-extends-25-trillion-rout-as-sec-probe-reportedly-investigates-its-accounting-194945274.html?fr=sycsrp_catchall">Nvidia stock extends $2.7 trillion rout as SEC probe ...</a></li>

</ul>
</details>

**Tags**: `#nvidia`, `#sec`, `#regulation`, `#accounting`, `#ai-hardware`

---

<a id="item-tech-news-10"></a>
### [Signal Publishes Measures to Block OS AI Agents From Reading Private Chats](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal has published a blog post describing engineering measures intended to prevent AI agents built into mobile operating systems from capturing users&\#x27; private Signal chats. The announcement addresses the tension between OS-level, on-device AI integration and app-level privacy guarantees, since platform-controlled agents operate above the level where an app can fully enforce protections. The full technical details of the measures were not included in the supplied source material, so the specific mechanisms and their measured effectiveness remain unverified here.

hackernews · dotcoma · Nov 20, 09:42 · [Discussion](https://news.ycombinator.com/item?id=50572348)

**「Background」** Recent mobile platforms ship with built-in AI assistants — Apple&\#x27;s Siri on iOS 27 and Google&\#x27;s Gemini and other AI assistants on Android — that can read or capture on-screen content, including content displayed inside other apps. Google&\#x27;s own Gemini privacy notice, which warns users not to share personal information with the assistant, has already underscored how much data these agents can collect. For an end-to-end encrypted messenger like Signal, this exposes a structural gap: encryption protects messages in transit and at rest, but not what the operating system itself can observe on screen.

**「Impact」** For Signal users on mobile, the app now actively restricts OS-embedded AI agents from capturing and storing their conversations, closing one channel through which platform-level assistants could harvest private chats. The protection is inherently partial, because these agents operate above individual applications across the entire software stack, and it cannot control a contact&\#x27;s device, where a recipient&\#x27;s AI assistant can still expose the same conversation — a limitation raised in the community discussion. Users should also expect tighter screen-capture restrictions as a side effect: one commenter reports that ordinary screenshots of Signal chats on Windows are now blocked.

**「Community Discussion」** Commenters cited Signal president Meredith Whittaker&\#x27;s prior warning that even users without an AI app installed can have their chats leaked through a contact&\#x27;s device, and one commenter asked Signal to publish its &\#x27;forensics investigation&\#x27; findings as a living document so smaller developers could collaborate on defenses. Others argued that app-level blocking is ultimately a losing battle against platform-controlled spyware and recommended operating systems like GrapheneOS, while some reported practical friction from Signal&\#x27;s defenses, including an inability to screenshot chats on Windows and persistent captcha problems when using a VPN.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your screen</a></li>
<li><a href="https://www.zdnet.com/article/dont-tell-your-ai-anything-personal-google-warns-in-new-gemini-privacy-notice/">Don&#x27;t tell your AI anything personal, Google warns in new... - ZDNET</a></li>
<li><a href="https://signal.org/blog/protecting-your-privacy/">Signal &gt;&gt; Blog &gt;&gt; Signal is Serious About Protecting Your Privacy</a></li>
<li><a href="https://durapid.com/blog/how-os-level-ai-agents-will-fundamentally-change-enterprise-app-behaviour/">OS - Level AI Agents : How They&#x27;re Changing Enterprise Apps</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#security`, `#AI agents`, `#mobile operating systems`, `#encrypted messaging`

---

<a id="item-tech-news-11"></a>
### [Scott Aaronson skeptically examines claim an LLM proved the Riemann Hypothesis](https://scottaaronson.blog/?p=10344) ⭐️ 7.0/10

On November 20, 2026, a Scott Aaronson blog post drew substantial Hacker News discussion \(reported at 236 points and 210 comments\) under the ironic title &quot;The stochastic parrots have apparently proved the Riemann Hypothesis,&quot; taking up a claim that a large language model has proved one of mathematics&\#x27; most famous unsolved problems. The pointed &quot;apparently&quot; and the &quot;stochastic parrot&quot; epithet for LLMs that imitate fluently without understanding signal Aaronson&\#x27;s skepticism, and the surrounding debate centers on whether any such machine-generated proof could be verified by humans, or whether it reflects data leakage and fluent imitation rather than genuine reasoning. No breakthrough is established by this item: the blog post&\#x27;s full text was not available for review, so Aaronson&\#x27;s specific arguments and conclusions rest here on the title, the item&\#x27;s metadata, and the comment thread, and the alleged proof remains an unverified claim rather than a demonstrated result.

hackernews · stratos123 · Nov 20, 20:03 · [Discussion](https://news.ycombinator.com/item?id=50581084)

**「Background」** The Riemann hypothesis, formulated by Bernhard Riemann in 1859, posits that the seemingly random distribution of prime numbers follows a hidden, meaningful order, and it remains one of the most famous unsolved problems in mathematics. The claim under examination is described in Scientific American and The New York Times reporting as the work of an Anthropic AI &quot;mathematician,&quot; and it follows a related October 2026 result in which AI proved the weaker quasi-Riemann hypothesis. Aaronson&\#x27;s title invokes the &quot;stochastic parrot&quot; critique of large language models as statistical imitators rather than genuine reasoners.

**「Impact」** For mathematicians, the practical consequence is a verification task of unprecedented scale: OpenAI&\#x27;s October 6, 2026 release included 722 manuscripts claiming results on major open problems, among them partial results on the Riemann hypothesis, Birch and Swinnerton-Dyer, and Hodge conjectures \(tool-3-1\). Quanta reported that among the 377 announced results, the quasi-Riemann hypothesis proof stood out, with Stanford&\#x27;s Jared Duker Lichtman calling it &quot;the most significant AI-for-math achievement so far, by quite a margin&quot; \(tool-3-2\). Scientific American, reporting one day before Aaronson&\#x27;s post, stated that independent mathematicians — including Anthropic&\#x27;s Levent Alpöge — now regard the full Riemann proof as almost certainly real, meaning acceptance of what Quanta calls arguably math&\#x27;s biggest open question is resting on independent expert attestation rather than traditional journal refereeing \(tool-3-3\).

**「Community discussion」** The thread&\#x27;s most substantive comments concern comprehension rather than the truth of the claim: &quot;janalsncm&quot; argues by analogy to Stockfish, whose evaluations are aggregates of calculations stacked on the neural NNUE evaluator and thus leave unsatisfying answers to &quot;why&quot; questions, while &quot;jstummbillig&quot; wonders whether humans can accept becoming unable to contribute anything of substance as machines surpass them. &quot;elorant&quot; speculates how many mathematicians could reach similar breakthroughs with near-infinite compute, and &quot;alterom&quot; quotes the line &quot;We should still fix the leak&quot; from the discussed exchange, arguing that mindset applies well beyond this incident — an indication that leakage of training data into the alleged proof was part of the debate.

<details><summary>References</summary>
<ul>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>
<li><a href="https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/">AI Proved the Quasi- Riemann Hypothesis . | Quanta Magazine</a></li>
<li><a href="https://www.nytimes.com/2026/11/20/science/anthropic-ai-math-riemann-hypothesis.html">Anthropic Mathematician Claims to Solve Riemann Hypothesis With...</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenAI_bulk_release_of_mathematical_papers">OpenAI bulk release of mathematical papers - Wikipedia</a></li>
<li><a href="https://www.quantamagazine.org/ai-proved-the-quasi-riemann-hypothesis-what-happens-now-20261019/">AI Proved the Quasi-Riemann Hypothesis. What Happens Now?</a></li>
<li><a href="https://www.scientificamerican.com/article/the-ai-riemann-hypothesis-proof-is-almost-certainly-true-independent-mathematicians-attest/">The AI Riemann hypothesis proof is almost certainly true ...</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#llm-reasoning`, `#mathematics`, `#riemann-hypothesis`, `#interpretability`

---

<a id="item-tech-news-12"></a>
### [Apple Reportedly Building AI Agent for Coding, Browsing, and App Control](https://www.bloomberg.com/news/articles/2026-11-19/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding) ⭐️ 7.0/10

Bloomberg reports, based on job postings Apple added this week, that Apple is recruiting senior engineering managers to lead a &quot;proactive AI agent&quot; that would write code, browse the web, and control apps on a user&\#x27;s behalf, targeting a launch as early as the end of 2027; the project is described as early-stage, so this is a reported plan rather than a shipped product. The same reporting says macOS 27.3 adds warning pages that increase the steps a third-party agent needs to gain Mac control permission from 4 to 14, a concrete platform change arriving while Meta \(Muse\) and OpenAI already offer comparable agents.

telegram · zaihuapd · Nov 20, 08:59

**「Background」** OpenAI and Meta have already shipped autonomous agents — including Meta&\#x27;s Muse — that can browse the web, operate apps, and act on a user&\#x27;s behalf, leaving Apple a latecomer to the fast-growing AI assistant market. Apple&\#x27;s move into the category had been widely expected by observers, but the company has not publicly announced such a product; Bloomberg&\#x27;s account rests on job postings Apple added this week, indicating the effort is still at an early staffing stage.

**「Impact」** The concrete change affecting users now is platform-level rather than the 2027 product: macOS 27.3 deploys warning pages that discourage granting third-party agents full Mac access and stretches the permission process from 4 steps to 14, creating adoption friction for rivals such as Meta Muse, Instinct, Claude, and OpenAI Dots roughly a year before Apple&\#x27;s own competing agent is expected. Developers shipping Mac agents should re-verify their onboarding flows against the new permission sequence and set user expectations for the longer grant path.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-19/apple-is-working-on-ai-agent-for-device-control-apps-browsing-and-coding">Apple Is Working on AI Agent for Device Control, Apps ...</a></li>
<li><a href="https://tech.yahoo.com/ai/apple-intelligence/articles/apple-develops-ai-agent-control-160700103.html">Apple develops AI agent to control apps, browse web and write ...</a></li>
<li><a href="https://appleinsider.com/articles/26/11/19/apple-ai-agents-are-coming-to-help-you-code-browse-perform-tasks">Apple AI agents are coming to help you code, browse ...</a></li>
<li><a href="https://techcrunch.com/2026/11/19/apple-may-be-developing-its-own-ai-agent-that-runs-your-mac/">Apple may be developing its own AI agent that runs your... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#apple`, `#ai-agents`, `#macos`, `#coding-agents`, `#tech-industry`

---

<a id="item-tech-news-13"></a>
### [OpenAI launches background mode: 8-hour async tasks at up to 40% off tokens](https://developers.openai.com/api/docs/guides/background) ⭐️ 7.0/10

OpenAI&\#x27;s API documentation introduces a background mode, currently in public beta, that lets developers run long-running requests asynchronously by setting \`background: true\` and selecting a completion window of 2 hours or 8 hours via \`background\_options.completion\_window\`. The 2-hour window is billed at a 30% token discount and the 8-hour window at 40% versus standard pricing, while leaving the option unset defaults to &quot;soonest&quot; with no discount. The beta applies to GPT-6.2 Astra, GPT-6.2 Sol, GPT-6.1 Terra, and GPT-6 Luna. One caveat for compliance-sensitive workloads: background mode temporarily stores response data even when \`store\` is set to false or zero data retention is enabled. The details come from a Telegram repost of the documentation and have not been independently verified here.

telegram · zaihuapd · Nov 20, 11:15

**「What is background mode」** Background mode is an asynchronous option in OpenAI&\#x27;s Responses API: a request sent with background: true returns immediately and is completed later, with &quot;soonest&quot; as the default completion target that carries no discount. The discounted 2h and 8h completion windows are a recent addition — third-party coverage dates them to November 17, 2026 — and are currently in public beta across four GPT-6-family models, sharing rate limits with the Batch API while using separate prompt caches. OpenAI&\#x27;s developer forum positions the windows for single- or multi-turn workflows that can tolerate a delayed first response, with the discount applying to token rates on each eligible request including follow-ups.

**「Impact」** Developers running batch jobs, evaluations, or other latency-tolerant workloads can cut token costs by 30% or 40% by setting \`background: true\` with a 2h or 8h completion window on the four supported models, though the default \`soonest\` option carries no discount. Teams with strict data-handling requirements face a compatibility caveat: background mode temporarily stores responses even when \`store\` is set to false or zero data retention is enabled, so the discounted path does not honor those settings and may be unusable for compliance-sensitive workloads.

<details><summary>References</summary>
<ul>
<li><a href="https://developers.openai.com/api/docs/guides/background">Background mode | OpenAI API</a></li>
<li><a href="https://community.openai.com/t/reduce-costs-using-background-mode-with-completion-windows/1418130">Reduce costs using Background Mode with completion windows</a></li>
<li><a href="https://www.datastudios.org/post/openai-responses-api-background-2-hour-8-hour-windows-30-40-percent-off">OpenAI Responses API background mode: 30% off for 2-hour, 40% ...</a></li>

</ul>
</details>

**Tags**: `#openai`, `#api`, `#async-processing`, `#cost-optimization`, `#llm`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why Output Caching Doesn&\#x27;t Work for LLM Agents](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference economics depend on caching inputs \(the KV cache\) so conversation history isn&\#x27;t recomputed on each turn, and agents visibly repeat content — quoting code snippets, evidence documents, sample outputs — in output tokens that cost far more to generate one-at-a-time than input tokens cost to ingest. That asymmetry makes deduplicating or caching model output look like an obvious saving.

**「Solution」** The obvious fix, Goedecke writes, would be fine-tuning or prompting a model to emit references like &quot;src/script.py:12-15&quot; instead of regurgitating content, with the harness expanding them transparently to the user. But he argues this optimizes only the visible slice of output: per his own agent histories, roughly 6% of output tokens are user-visible, 50% are reasoning tokens, and 44% are tool calls. Amdahl&\#x27;s law then bites — even saving two-thirds of visible tokens, which he calls a ridiculously optimistic estimate, trims only about 4% of total output. The load-bearing assumption is that chain of thought doesn&\#x27;t repeat itself \(he is only moderately confident, noting early open-source reasoning models did loop\), and he leaves open whether models re-compose reasoning content inside tool calls; he also suspects inference providers already exploit n-gram repetition via speculative decoding. The real lever is the invisible 94%, which depends on intelligence: smarter models need fewer reasoning tokens and tool calls to reach an answer, which is why a model 5x pricier per token can cost less overall if it finishes with 6x fewer tokens.

**「Takeaway」** Per-token price is the wrong cost metric for agents: repetition in visible output is too small a fraction of tokens to be worth optimizing, so real savings come from model intelligence that shortens the invisible reasoning and tool-call sequences — the same reason the cheapest plumber isn&\#x27;t the cheapest hire.

**Tags**: `#llm-inference-economics`, `#caching`, `#ai-agents`, `#token-costs`, `#amdahls-law`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Prediction-Market Odds of S&amp;P 500 Hitting 8,000 in 2026 Slump Amid AI Sell-Off](https://www.cnbc.com/2026/11/20/sp-500-8000-kalshi-odds-ai-selloff.html) ⭐️ 7.0/10

Traders on prediction-market platform Kalshi now put just 6% odds on the S&amp;P 500 crossing 8,000 in 2026, down from 72% on Oct. 13, after an AI-driven tech sell-off dragged the Dow and S&amp;P 500 into correction territory \(roughly a 10% drop from recent highs\) and pushed the Nasdaq negative for the year. The S&amp;P 500&\#x27;s year-to-date gain has been cut to just over 2%.

rss · CNBC Finance · Nov 20, 19:59

**「Background」** Kalshi is a regulated exchange where traders bet real money on outcomes such as stock index milestones, and a market &quot;correction&quot; means an index has fallen more than 10% below its recent peak.

**「Impact」** Investors in AI-exposed tech stocks face continued pressure, and the Stock Trader&\#x27;s Almanac says hopes for a December rally are fading, warning &quot;more downside can&\#x27;t be ruled out&quot; as it draws a parallel to 2018, when Federal Reserve rate hikes in a midterm year preceded a late-December low; the Fed is widely expected to raise rates at its December meeting.

<details><summary>References</summary>
<ul>
<li><a href="https://kalshi.com/">Kalshi - Prediction Market for Trading the Future</a></li>
<li><a href="https://edition.cnn.com/2026/11/20/investing/us-stocks-anthropic-ai">Nasdaq wipes out gains for the year as Anthropic IPO fails to quell AI ...</a></li>

</ul>
</details>

**Tags**: `#prediction markets`, `#S&amp;P 500`, `#market correction`, `#AI stocks`, `#Federal Reserve`

---

<a id="item-finance-news-2"></a>
### [Fed officials talk more, not less, as Chair Warsh withholds rate guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve Chair Kevin Warsh&\#x27;s refusal to give forward guidance — telling markets in advance where interest rates are headed — has coincided with more Fed official speeches in the past two weeks than in any similar period since early 2025, according to a Bank of America analysis, as a divided committee debates how aggressively to raise rates against inflation running above 3% versus the Fed&\#x27;s 2% target. Traders now see a 100% chance of at least a quarter-point rate hike at the December meeting, with a small probability of a half-point move, according to CME Group&\#x27;s FedWatch.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** Kevin Warsh became Federal Reserve chair in May 2026 after Senate confirmation, succeeding Jerome Powell, and soon scrapped &quot;forward guidance&quot; — telling markets in advance where interest rates are headed — arguing it locks policymakers in before decisions are due. The rate-setting Federal Open Market Committee then held its benchmark rate steady in October while inflation ran above 3%, versus the Fed&\#x27;s 2% target.

**「Why it matters」** Traders now see a 100% chance of at least a quarter-percentage-point rate hike at the Fed&\#x27;s December meeting, per CME Group&\#x27;s FedWatch — a market-implied forecast, not a decision — that would lift the benchmark rate above its current 3.75%–4.00% range and raise borrowing costs on mortgages, credit cards and business loans; Bank of America economist Aditya Bhave also warns that the flood of conflicting Fed commentary itself is producing &quot;undue rates volatility.&quot;

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/business/2026/may/13/kevin-warsh-federal-reserve-chair">US Senate confirms Kevin Warsh as Federal Reserve chair ...</a></li>
<li><a href="https://www.financialexpress.com/market/global-market-pulse/why-fed-chair-warsh-scrapped-forward-guidance-in-a-132-word-pivot/4272071/">Why Fed Chair Warsh scrapped forward guidance in a 132-word ...</a></li>
<li><a href="https://btw.co/node/12840040/fomc-meeting/">FOMC Meeting Trending #101 - Break The Web</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#forward guidance`, `#inflation`

---

<a id="item-finance-news-3"></a>
### [U.S. Companies Turn From Buying Back Shares to Selling Them](https://www.cnbc.com/2026/11/20/equity-issuance-bull-market-problem.html) ⭐️ 7.0/10

U.S. corporations have shifted from net buying back their own shares to net issuing new stock, with net new issuance equal to 3.1% of total market capitalization as of late last week, according to Acadian Asset Management — turning share supply into a headwind for the four-year-old bull market. Recent large raises, including Anthropic&\#x27;s $81 billion IPO, Alphabet&\#x27;s $84.8 billion equity sale, and SpaceX&\#x27;s $85.7 billion IPO, have added to that supply; Acadian&\#x27;s Owen Lamont says issuance remains below tech-bubble and covid-bubble peaks and that he cannot rule out an AI bubble now.

rss · CNBC Finance · Nov 20, 14:15

**「Background」** Before 2026, U.S. companies were net buyers of their own stock, and those buybacks shrank the pool of shares available to investors — more money chasing fewer shares — which helped support prices and lifted per-share earnings, the reverse of what issuing new shares does.

**「Impact」** The reversal removes a key support for U.S. stock investors generally: buybacks that once shrank the share count and lifted earnings per share are giving way to new share supply, and research cited in the analysis \(Baker-Wurgler\) found that heavy equity issuance has historically been followed by lower market returns, though the writer frames this as a potential headwind rather than a certain outcome.

**Tags**: `#equity issuance`, `#share buybacks`, `#bull market`, `#IPO market`, `#AI investment`

---