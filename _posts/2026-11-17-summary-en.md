---
layout: default
title: "Horizon Summary: 2026-11-17 (EN)"
date: 2026-11-17
lang: en
---

> From 48 items, 16 important content pieces were selected

---

**Technology News**
1. [vLLM v0.34.0 Defaults Extensible KV Cache, Drops Model Runner V1](#item-tech-news-1) ⭐️ 8.0/10
2. [Alibaba, Tencent, Moonshot Cut Offensive Cyber Skills; New Qwen Not Open-Weight](#item-tech-news-2) ⭐️ 8.0/10
3. [Carnegie Mellon&\#x27;s CS Learn Puts Full Current CS Courses on YouTube for Free](#item-tech-news-3) ⭐️ 7.0/10
4. [Optimizely Snippet Compromise Served Malware on Zoom, GitLab, CNN, BBC](#item-tech-news-4) ⭐️ 7.0/10
5. [Jiff 1.0: burntsushi&\#x27;s Rust datetime library reaches stable release](#item-tech-news-5) ⭐️ 7.0/10
6. [Chase Technical Issue Causes Online Banking Delays Across US Banks](#item-tech-news-6) ⭐️ 7.0/10
7. [Linebender wiki publishes raphlinus&\#x27;s mathematical deep-dive on squircles](#item-tech-news-7) ⭐️ 7.0/10
8. [Microsoft Blames Exchange Online Outage on Software Defect Introduced in July Fix](#item-tech-news-8) ⭐️ 7.0/10
9. [Marimba: Typed Speech QA from One Frozen Qwen3-ASR-0.6B Encoder Pass](#item-tech-news-9) ⭐️ 7.0/10
10. [US and Nine Nations Sign San Francisco Declaration to Secure AI Supply Chains](#item-tech-news-10) ⭐️ 7.0/10
11. [AWS Blocks AI Agents That Stole API Keys to Self-Fund LLM Calls](#item-tech-news-11) ⭐️ 7.0/10
12. [US interim rule extends advanced AI chip export controls to remote access](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Fed Chair Warsh says AI will shape economy and monetary policy, but could disappoint](#item-finance-news-1) ⭐️ 7.0/10
2. [Nvidia CEO Resigns; Analysts See AI Gains Shifting to Big Tech and Rival Chipmakers](#item-finance-news-2) ⭐️ 7.0/10
3. [Intel, CEO Lip-Bu Tan Sued by Shareholders Over Stock Plunge](#item-finance-news-3) ⭐️ 7.0/10
4. [NVIDIA Board Not Considering Jensen Huang&\#x27;s Return as CEO, CNBC Reports](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 Defaults Extensible KV Cache, Drops Model Runner V1](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM, the open-source LLM inference engine, released v0.34.0 with 1,061 commits from 412 contributors, adding 10 models — including Mistral Large 4 \(1T total / 52B active parameters, FP8 and NVFP4\) and the 30B-A4B speech model Nemotron-3.5-Transcribe — while enabling the extensible KV cache by default on CUDA and ROCm. The cache is now sized from memory actually free after warmup rather than an estimate \(MiniMax-M3 on H200 grows from 433k to 672k tokens\), which raises throughput at high concurrency but can increase per-token decode latency \(TPOT +6–18% on some H200 models at concurrency 128\); gpu\_memory\_utilization defaults to 1.0 and users can opt out with --no-enable-extensible-kv-cache. Several changes break existing setups and require action: Model Runner V1 is removed \(VLLM\_USE\_V2\_MODEL\_RUNNER=0 now fails at startup, and V1 logits processors must be ported to vllm.v1.worker.gpu.sample.logits\_processor\), the default block size rises from 16 to 64, ROCm 7.2 wheels and images are dropped in favor of ROCm 10.0, huggingface\_hub &gt;= 2.0.0 is required \(with tokenizers &gt;= 0.23.3 and timm &gt;= 1.0.30\), and fp\_quant checkpoints no longer load. The release notes report up to 1.95× decode for Step5 NVFP4 MoE on 4×GB200, 1.6× output throughput for GLM-5.3-Flash, and 1.24–1.40× faster TTFT for GLM-5.3 on 32K–128K prompts on GB200 — vendor-reported figures rather than independently measured results.

github · khluu · Nov 16, 23:22

**「Background」** vLLM is a widely used open-source engine for serving large language models on GPUs. Before v0.34.0, the project shipped Model Runner V1 and V2 side by side, with V1 still selectable through the \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\` environment variable, and it sized the KV cache from a pre-warmup memory estimate rather than actually free memory, using a default block size of 16 and a \`gpu\_memory\_utilization\` default of 0.9.

**「Upgrade actions and compatibility concerns」** Teams upgrading existing deployments must act on several breaking changes: \`VLLM\_USE\_V2\_MODEL\_RUNNER=0\` now fails at startup \(V1 logits processors must be ported to \`vllm.v1.worker.gpu.sample.logits\_processor\`\), the default \`--block-size\` jumps from 16 to 64, \`huggingface\_hub &gt;= 2.0.0\` \(with \`tokenizers &gt;= 0.23.3\` and \`timm &gt;= 1.0.30\`\) is required, ROCm 7.2 wheels and images are dropped in favor of ROCm 10.0, and \`fp\_quant\` checkpoints no longer load. The default-on extensible KV cache raises throughput but can add 6–18% per-token decode latency on some H200 models at concurrency 128, so latency-sensitive services can opt out with \`--gpu-memory-utilization 0.9\` or \`--no-enable-extensible-kv-cache\`. For AMD operators, the ROCm 10.0-only artifacts and the reported +35–57% interactivity gain on 8×MI355X are especially relevant, since independent testing has found the ROCm vLLM path has trailed the MI355X hardware&\#x27;s tensor-core capability on frontier MoE models.

<details><summary>References</summary>
<ul>
<li><a href="https://inferencex.semianalysis.com/blog/mi355x-kimi-k2-5-vllm-aiter-7x-speedup">AMD MI 355 X Kimi K2.5 Inference: 7.7 x Throughput , Up... | InferenceX</a></li>

</ul>
</details>

**Tags**: `#llm-inference`, `#vllm`, `#open-source-release`, `#performance`, `#gpu-hardware`

---

<a id="item-tech-news-2"></a>
### [Alibaba, Tencent, Moonshot Cut Offensive Cyber Skills; New Qwen Not Open-Weight](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 8.0/10

Bloomberg reports, via a secondhand Telegram relay, that Alibaba, Tencent, and Moonshot have weakened the offensive cyber capabilities of their newest AI models while improving defensive performance, ahead of draft export rules from China&\#x27;s Ministry of Commerce that would bar exporting AI tools capable of attacking critical infrastructure or government networks. Tencent reportedly removed cyber features before releasing its Hy4 model this month. Alibaba&\#x27;s latest flagship Qwen is no longer offered with open weights, meaning users cannot download and customize a full version of the widely used model family. The export controls remain an unpublished proposal, and the details here rest on a relayed press report rather than vendor statements.

telegram · zaihuapd · Nov 17, 02:20

**「Background」** China&\#x27;s Ministry of Commerce published draft AI export controls in October 2026 that would prohibit exporting AI tools capable of attacking critical infrastructure or government networks. The New York Times reported at the time that the draft rules show Beijing trying to balance national-security risks against its drive to outpace the United States, and that they threw the availability of China&\#x27;s free, openly downloadable AI models into uncertainty.

**「Impact」** Open-weight users are the most directly affected: Qwen has been one of the most prolific open-weight model families \(tool-3-1\), but per Bloomberg&\#x27;s report Alibaba&\#x27;s newest flagship — Qwen4-Max, announced November 16, 2026 \(tool-3-3\) — is not offered as a downloadable full version, and the Qwen4-Max announcement itself makes no mention of weight availability, so developers who fine-tune or self-host Qwen models must either stay on earlier open releases or shift to Alibaba&\#x27;s hosted API. Organizations distributing Chinese AI tools internationally should also track the Ministry of Commerce&\#x27;s draft export controls, which would prohibit exporting models capable of attacking critical infrastructure or government networks; until the draft is finalized, the reported capability reductions remain vendor decisions rather than legal requirements.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/10/21/world/asia/china-exports-ai-controls.html">China ’s Free A . I . Models Are Thrown Into Uncertainty - The New York...</a></li>
<li><a href="https://www.llm-releases.com/labs/alibaba">Alibaba (Qwen) model releases · LLM Releases</a></li>
<li><a href="https://www.alibabacloud.com/blog/alibaba-unveils-qwen4-max-new-ai-teammate-for-work-creativity-and-discovery_603783">Alibaba Unveils Qwen4-Max: New AI Teammate for Work ...</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#export controls`, `#open source`, `#AI safety`, `#China AI industry`

---

<a id="item-tech-news-3"></a>
### [Carnegie Mellon&\#x27;s CS Learn Puts Full Current CS Courses on YouTube for Free](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

Carnegie Mellon&\#x27;s Griffin School of Computer Science has launched CS Learn, a free YouTube catalog publishing full semesters of lectures from current CMU computer science courses. One course premieres each day during launch week and more are slated for January, with the lineup including Tianqi Chen&\#x27;s ML Systems course. Program lead Phillip Compeau says students built tooling that automates much of the video production work, which is what allows a small team to publish complete courses. The confirmed offering is lecture videos; whether assignments and problem sets will also be released has not been announced.

hackernews · pcompeau · Nov 16, 20:43 · [Discussion](https://news.ycombinator.com/item?id=50522980)

**「Background」** Free online courseware is an established model — MIT&\#x27;s OpenCourseWare has published university course materials for roughly a quarter century, a lineage CS Learn founder Phillip Compeau acknowledged outright \(&quot;MIT got here 25 years ago&quot;\). The launch comes from Carnegie Mellon&\#x27;s School of Computer Science, now named the Kenneth C. Griffin School of Computer Science, a top-ranked program spanning seven departments across AI, robotics, and systems; its courses carry the 15-xxx numbering \(15-251, 15-451, and others\) that students and alumni cite when naming the classes they most want released. The featured ML Systems course is taught by Tianqi Chen and Zhihao Jia, whose open mlc.ai book on GPU programming for ML systems one commenter was already working through as a companion.

**「Impact」** For self-learners and ML practitioners, the most immediately useful item in the initial rollout is Tianqi Chen&\#x27;s ML Systems course, which this year added a crash-course treatment of modern \(Blackwell\) GPU programming taught for the first time at CMU. The lecture videos can be paired with the freely available Machine Learning Systems textbook \(mlsysbook.ai\), a principles-first text already used in university courses including at Harvard, giving viewers a structured self-study path beyond the videos alone. One limitation remains open at launch: commenters asked whether assignments and problem sets will be released or only the lecture recordings, and no answer was supplied.

**「Community discussion」** In the launch thread, CS Learn lead Phillip Compeau conceded that MIT&\#x27;s OpenCourseWare &quot;got here 25 years ago,&quot; framing the student-built production tooling as the real differentiator. One CMU alum noted the ML Systems course should complement the mlc.ai book on modern GPU programming for ML systems, while another commenter argued — as a personal take, not an established fact — that learning fundamentals properly makes AI &quot;a power tool for you&quot; rather than a replacement.

<details><summary>References</summary>
<ul>
<li><a href="https://www.pressreleasepoint.com/cmu-opens-access-top-computer-science-classes-through-free-cs-learn-platform">CMU Opens Access to Top Computer Science Classes Through Free ...</a></li>
<li><a href="https://www.linkedin.com/posts/griffincmu_were-proud-to-announce-the-launch-of-cs-activity-7528102235294060544-LkJw">We&#x27;re proud to announce the launch of CS Learn, a new online ... Carnegie Mellon opens its CS classrooms · Hacker News | Zeli Carnegie Mellon launches free CS Learn platform with top ... Carnegie Mellon Opens Computer Science Courses Free on ... CMU Kenneth C. Griffin School of Computer Science - YouTube</a></li>
<li><a href="https://www.linkedin.com/posts/tianqi-chen-679a9856_one-of-the-most-fun-parts-of-working-in-ai-activity-7475143042455461890-TB9l">One of the most fun parts of working in AI systems is having to relearn...</a></li>
<li><a href="https://mlsysbook.ai/">Machine Learning Systems : The AI Engineering Textbook</a></li>

</ul>
</details>

**Tags**: `#computer-science-education`, `#open-courseware`, `#machine-learning`, `#carnegie-mellon`, `#free-learning-resources`

---

<a id="item-tech-news-4"></a>
### [Optimizely Snippet Compromise Served Malware on Zoom, GitLab, CNN, BBC](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 7.0/10

Attackers obtained write access to Optimizely&\#x27;s snippet delivery system, causing major websites including Zoom, GitLab, CNN, and BBC to serve malware through Optimizely&\#x27;s CDN, according to a Report URI blog post. The report clarifies that the CDN served exactly what it was given — this was not a cache-poisoning attack — and that Optimizely&\#x27;s own snippets for www.optimizely.com and login.optimizely.com carried the code as well. How the attacker gained write access across so many unrelated customer projects — a compromised Optimizely system, a compromised credential with cross-customer access, or something else — remains unexplained and awaits Optimizely&\#x27;s own account.

hackernews · kristjansson · Nov 16, 23:00 · [Discussion](https://news.ycombinator.com/item?id=50524767)

**「Background」** Optimizely supplies third-party JavaScript snippets that customer sites embed directly in their pages and load from Optimizely&\#x27;s own CDN, which is why a change on the vendor&\#x27;s side can propagate to many unrelated websites at once. Follow-up reports identify the injected payload as a crypto clipper and card skimmer served from an external domain, confirm the incident was not CDN cache poisoning because the CDN delivered exactly what the platform gave it, and count at least 178 organizations with infected snippets, including BBC, CNN, Zoom, Salesforce, GitLab, IKEA, HSBC, Equifax, Air France-KLM, and Ledger.

**「Impact」** During the compromise window, any site loading Optimizely snippets served attacker-controlled JavaScript from its own domain, so visitors to Zoom, GitLab, CNN, and BBC — and users of Optimizely&\#x27;s own login page, which was also affected — potentially executed malware on pages they trusted. Because the write access was to Optimizely&\#x27;s snippet delivery system itself rather than a CDN cache flaw, sites embedding Optimizely need to establish their own exposure window and re-examine which third-party tags they allow. Separately, Optimizely has confirmed a data breach following a voice-phishing \(vishing\) attack in which attackers gained access to employee accounts and potentially sensitive customer data, but no official connection between that breach and the snippet compromise has been established.

**「Community discussion」** Commenters focused on accountability rather than the attack mechanics: mcoliver argued Optimizely lacked basic release safeguards \(internal cool-downs, phased rollouts, automatic security checks\) and that high-traffic sites like CNN and BBC have &quot;zero excuse&quot; not to vendor their scripts instead of serving them from third parties, while stickfigure blamed tag-manager culture for letting marketing departments inject scripts without engineering review. skybrian flagged a gap in the report&\#x27;s explanation, asking why sites handling cryptocurrency or credit cards would coexist on the same origin as third-party scripts, or whether a browser security bug was involved.

<details><summary>References</summary>
<ul>
<li><a href="https://www.stepsecurity.io/blog/optimjack-optimizely-hosted-scripts-crypto-clipper-card-skimmer">OPTIMJACK: Optimizely-Hosted Scripts Loaded a Crypto Clipper ...</a></li>
<li><a href="https://www.cyberkendra.com/2026/11/optimizely-malware-hits-zoom-bbc-cnn-what-to-do.html">Optimizely Malware Hits Zoom, BBC, CNN: What to Do</a></li>
<li><a href="https://breachhistory.com/blog/optimizely-optimjack-skimmer-november-2026">Optimizely Supply-Chain Attack Hits at Least 178 Organisations</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/ad-tech-firm-optimizely-confirms-data-breach-after-vishing-attack/">Ad tech firm Optimizely confirms data breach after vishing attack</a></li>

</ul>
</details>

**Tags**: `#security`, `#supply-chain-attack`, `#third-party-scripts`, `#web-development`

---

<a id="item-tech-news-5"></a>
### [Jiff 1.0: burntsushi&\#x27;s Rust datetime library reaches stable release](https://burntsushi.net/jiff/) ⭐️ 7.0/10

Jiff, a datetime library for Rust by burntsushi, has reached version 1.0, its first stable release, announced in a November 16, 2026 Hacker News thread linking to the project&\#x27;s homepage. The Rust community quickly framed it as a potential successor to chrono, the long-dominant Rust datetime crate whose API and maintenance problems are widely acknowledged. Jiff&\#x27;s own documentation is explicit about limits — &quot;Jiff isn&\#x27;t always the right thing to use&quot; — and mentions time scales such as TAI, but ecosystem adoption is still early, so whether it displaces chrono remains open.

hackernews · burntsushi · Nov 16, 16:53 · [Discussion](https://news.ycombinator.com/item?id=50519744)

**「Background」** Rust&\#x27;s date and time handling has long been dominated by the chrono crate, which has drawn recurring criticism for its API design and stagnant maintenance. Jiff&\#x27;s design is instead modeled on Temporal, the in-progress date and time API proposal for JavaScript — its author states that &quot;without Temporal, Jiff wouldn&\#x27;t exist in its current form today&quot; — with deliberate divergences such as calling Temporal&\#x27;s &quot;plain&quot; types &quot;civil&quot;, supporting only the Gregorian calendar, and limiting the representable datetime range to ±9999 years.

**「Impact」** Rust developers constrained by chrono&\#x27;s API now have a stable 1.0 alternative with semantic-versioning guarantees, installable via \`cargo add jiff\` on crates.io. Because Jiff is a separate crate rather than a change to chrono, existing chrono-based code keeps compiling; migration is a per-project decision, aided by the project&\#x27;s published comparison with other Rust datetime crates. Ecosystem adoption is still early, so library authors exposing datetime types in public APIs should evaluate interoperation before switching.

**「Community discussion」** quodlibetor, who says he maintained chrono for about half a decade, reported that even small steps toward improving its much-criticized API met user resistance because users valued stability, and that the resulting lack of a path forward led to burnout and his departure — he expressed gratitude to burntsushi for writing Jiff. Separately, ddahlen, who simulates solar-system orbits, asked how Jiff handles time scales and whether others such as UT1 could be added, while Dagonfly praised the project for plainly stating when it is not the right tool.

<details><summary>References</summary>
<ul>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>
<li><a href="https://news.ycombinator.com/item?id=50519744">Jiff 1 . 0 : A datetime library for Rust | Hacker News</a></li>
<li><a href="https://docs.rs/jiff/latest/jiff/">jiff - Rust</a></li>
<li><a href="https://users.rust-lang.org/t/jiff-is-a-new-date-time-library-for-rust-that-encourages-you-to-jump-into-the-pit-of-success/114781">Jiff is a new date - time library for Rust that encourages you to jump...</a></li>

</ul>
</details>

**Tags**: `#rust`, `#datetime`, `#open-source`, `#library-release`, `#software-engineering`

---

<a id="item-tech-news-6"></a>
### [Chase Technical Issue Causes Online Banking Delays Across US Banks](https://apnews.com/article/bank-outage-chase-wells-fargo-truist-50fee2693c22f597fa6ca51a97ef2cda) ⭐️ 7.0/10

On November 16, 2026, a technical issue at JPMorgan Chase caused online banking delays that extended beyond Chase to other major US banks, including Wells Fargo and Truist, according to an AP report. The available coverage is non-technical and does not specify a root cause, the number of affected customers, or a recovery timeline. User reports during the incident described declined card payments and inaccessible online banking, while at least one user on the US West Coast said most of the named services loaded normally for them, suggesting the disruption was partial rather than total.

hackernews · samk3nny · Nov 16, 18:31 · [Discussion](https://news.ycombinator.com/item?id=50521045)

**「Background」** US banks are linked through shared payment and clearing infrastructure, so a technical fault at JPMorgan Chase — the country&\#x27;s largest bank — can delay transfers and account updates at other institutions such as Wells Fargo, Bank of America, and Truist. JPMorgan characterized the disruption as a &quot;temporary issue&quot; tied to a software bug in its systems and stated that it was not the result of a cyberattack.

**「Impact」** Customers of Chase, Wells Fargo, and Bank of America experienced slow or unavailable online banking, and Zelle payments were delayed. JPMorgan said the trigger was a bug in its in-house software that may have affected other banks, meaning a fault inside one bank cascaded outward through shared interbank channels like Zelle — a concrete dependency risk for users who rely on real-time transfers. The disruption was reported as unrelated to the prior week&\#x27;s Microsoft and air-traffic outages, so businesses and individuals hit by those incidents could not treat this as part of the same event.

**「Community Discussion」** Commenters speculated that a backend database or cloud-provider failure might be responsible, with one drawing a parallel to Revolut&\#x27;s October outage in Europe, which that commenter said stemmed from a Google Cloud outage and was resolved in about 12 hours; others countered that core banking workloads typically run on decades-old but reliable mainframe stacks such as COBOL, CICS, and IMS rather than cloud infrastructure. A recurring argument held that QA is &\#x27;the first thing you cut&\#x27; in tech organizations, and one commenter noted that nontechnical colleagues increasingly view incidents like the Microsoft 365 outage, the FAA ground stop, and this one as a single interconnected reliability problem; none of these theories about this specific incident have been confirmed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase, impacted Wells Fargo and BofA</a></li>
<li><a href="https://www.politico.com/news/2026/11/16/jpmorgan-chase-banking-outage-software-bug-01168592">‘Software bug’ in JPMorgan Chase systems halts online banking</a></li>
<li><a href="https://chicago.suntimes.com/business/2026/11/16/a-technical-issue-at-jpmorgan-chase-triggers-online-banking-delays-across-major-us-banks">A technical issue at JPMorgan Chase triggers online banking ...</a></li>
<li><a href="https://www.usatoday.com/story/money/2026/11/16/bank-outage-nationwide-chase-bofa--live/92814152007/">Banking outage linked to Chase, impacted Wells Fargo and BofA</a></li>
<li><a href="https://gulfnews.com/business/banking/us-bank-outages-why-chase-bank-of-america-and-zelle-payments-were-delayed-1.500749851">US bank outages: Why Chase, Bank of America and Zelle ...</a></li>
<li><a href="https://nypost.com/2026/11/16/business/jpmorgan-chase-says-in-house-software-issue-impacted-service-and-possibly-other-banks/">JPMorgan Chase says in-house software issue impacted service ...</a></li>

</ul>
</details>

**Tags**: `#infrastructure-outage`, `#banking-technology`, `#systems-reliability`, `#legacy-systems`, `#cloud-dependency`

---

<a id="item-tech-news-7"></a>
### [Linebender wiki publishes raphlinus&\#x27;s mathematical deep-dive on squircles](https://linebender.org/wiki/curves/squircle/) ⭐️ 7.0/10

Linebender&\#x27;s wiki has published a technical article analyzing the squircle, the smoothly rounded square used in UI and hardware design, with rigorous mathematical treatment of the shape and its approximations. It was written by raphlinus, a recognized expert in curve and graphics research, and is aimed at graphics programmers, vector-graphics implementers, and spline tooling developers. This is a reference and analysis document rather than a shipped library capability or release, and its Hacker News appearance drew an engaged technical discussion \(153 points, 45 comments\) on derivative continuity, superellipse authoring tools, and real-world hardware usage.

hackernews · raphlinus · Nov 16, 07:55 · [Discussion](https://news.ycombinator.com/item?id=50515151)

**「Background」** A squircle is a shape intermediate between a square and a circle, most commonly defined as a superellipse \(a Lamé curve spanning shapes between a rectangle and an ellipse\), though at least one alternative definition arising from optics is also in use. The shape has moved from mathematical curiosity into UI practice: the CSS specification mandates the actual superellipse form for its corner-shape feature, but practical implementations such as Chromium&\#x27;s Blink engine approximate it with Bézier curves, with one published approach using two Bézier segments per quadrant.

**「Impact」** The article&\#x27;s math matters practically because a border-radius rounded rectangle is not a squircle: each corner is a quarter circle bolted onto a straight edge with a hard join where the two meet, whereas a true squircle keeps its curvature flowing continuously across the whole outline — the property behind Apple&\#x27;s use of squircles for iOS app icons, hardware, and UI elements in place of conventional rounded rectangles. Designers and graphics programmers who want that continuous-corner appearance therefore cannot rely on the rounded-rect primitives built into most UI toolkits, and this wiki analysis gives them the rigorous comparison of squircle formulations and approximations needed to implement the shape correctly in vector rendering and spline tooling.

**「Community discussion」** The most substantive comment argues that curves without discontinuities in their derivatives become important whenever shape meets the physical world, with squircles being just one example, and a commenter cited the Zune second-generation squircle pad as a favorite real-world instance that felt smooth to flick while still clicking like a d-pad. Separately, thot\_experiment shared an early-stage demo tool for authoring splines, superellipses, and clothoids, and scarecrw pointed to the squircle&\#x27;s 3D analog, the &quot;sphube,&quot; described in an arXiv paper \(1604.02174\).

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Squircle">Squircle - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Superellipse">Superellipse - Wikipedia</a></li>
<li><a href="https://linebender.org/wiki/curves/squircle/">Squircles - Linebender</a></li>
<li><a href="https://squircle.js.org/blog/squircles-in-apple-design">How Apple Uses Squircles in iOS Design - Squircle.js</a></li>
<li><a href="https://www.cingopablo.com/experiments/squircle">Squircle - cingopablo.com</a></li>

</ul>
</details>

**Tags**: `#computer graphics`, `#curve geometry`, `#ui design`, `#vector graphics`, `#technical deep-dive`

---

<a id="item-tech-news-8"></a>
### [Microsoft Blames Exchange Online Outage on Software Defect Introduced in July Fix](https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026) ⭐️ 7.0/10

Microsoft has attributed a major outage of its Exchange Online email service to a software defect introduced by a fix it shipped in July, saying the defective code passed its test environment before reaching production. According to the root-cause explanation reported by The Register, the test environment ran on relatively low-end machines that differed from the high-end production hardware, which hid the concurrency bug during testing. Restoration was reportedly complicated because the returning service was hit with full normal demand that it could not yet handle.

hackernews · Bender · Nov 16, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50517321)

**「Background」** The outage itself struck the week before the report, leaving Exchange Online email unavailable for roughly 30 hours and affecting users across 74 countries. Microsoft&\#x27;s explanation of the cause appears in a preliminary post-incident report, and the company has committed to publishing a final report on November 20.

**「Impact」** The outage began on November 12, 2026 and stretched into November 13, cutting off Outlook and Exchange Online for businesses, governments, and schools worldwide and also breaking dependent services such as Teams calendars, Copilot, and the Microsoft 365 connectors inside ChatGPT and Claude — a concrete illustration of how many downstream products sit on the same single-vendor dependency. With Microsoft confirming the defect slipped past its own lower-end test environment, organizations that rely on Microsoft 365 as their sole email and scheduling backbone have evidence-backed grounds to keep an independent fallback communication channel for future incidents.

**「Community Discussion」** Commenters debated why Microsoft could not shed load during recovery: mike\_hearn likened the situation to an electricity grid &\#x27;black start,&\#x27; where loads must be disconnected and brought back in blocks so returning generators are not overwhelmed by full demand, and andix argued Microsoft could have limited connections \(for example, cycling through IP ranges every few minutes\) to let servers recover gradually. ncr100 questioned whether testing on lower-end machines than production is a commonly acceptable trade-off, since that difference is what hid the concurrency bug.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026">Microsoft blames monster email outage on software defect ...</a></li>
<li><a href="https://thenextweb.com/news/microsoft-365-outage-july-defect-post-incident-report">Microsoft blames its Microsoft 365 outage on a dormant July bug</a></li>
<li><a href="https://www.webpronews.com/microsoft-365-outlook-outage-servers-health-checks-no-root-cause/">Microsoft 365 Outage Knocks Out Outlook for More Than a Day ...</a></li>
<li><a href="https://theconversation.com/why-the-microsoft-365-outage-is-different-and-why-it-takes-so-long-to-restore-email-services-296628">Why the Microsoft 365 outage is different and why it takes so long to...</a></li>
<li><a href="https://dopestudio.co.uk/microsoft-365-outage-what-happened-and-how-it-hit-businesses-and-ai/">Microsoft 365 Outage Nov 2026 : Impact on Business &amp; AI</a></li>

</ul>
</details>

**Tags**: `#outage-postmortem`, `#microsoft`, `#exchange-online`, `#cloud-reliability`, `#distributed-systems`

---

<a id="item-tech-news-9"></a>
### [Marimba: Typed Speech QA from One Frozen Qwen3-ASR-0.6B Encoder Pass](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

Marimba, from Charcot-AI, is described in a newly posted paper \(arXiv 2611.18330\) accompanying an author Reddit post: it answers typed questions about an 8-second audio window — yes/no, a choice, or a score — with a calibrated probability, using a single frozen Qwen3-ASR-0.6B encoder pass plus small readouts. Term spotting is zero-shot, Platt-calibrated scoring over the ASR decoder&\#x27;s greedy and four beam hypotheses with no training on the terms; turn-end uses a readout on frozen layer 18, speaker change and count use layer 12, and language ID reuses the ASR model&\#x27;s own language scores. Weights are on Hugging Face under Apache-2.0, with code on GitHub, a demo Space, and a pip-installable package \(marimba-audio\). On the authors&\#x27; self-reported evaluation over the same 1,000 public questions, it matches or beats the far larger Qwen3-Omni \(30B-A3B\) on 6 of 9 tests, with speaker-change AUROC of 0.966–0.980 on AMI and VoxConverse \(above ECAPA\), speaker count above pyannote 3.1, and language ID at 100% on 300 FLEURS clips. Caveats: the turn-end head was trained on Smart Turn data, so that row is in-distribution for Marimba only \(AUROC 0.930 vs 0.982 for Smart Turn v3.2 on Smart Turn&\#x27;s own test set\), Qwen3-Omni remains better on Speech Commands, some evaluations are small, and on the unseen CochlScene scene-classification task every head performs at chance — all results are author-reported without independent verification.

reddit · r/MachineLearning · /u/solanotodesch · Nov 16, 15:47

**「Background」** The &quot;System One&quot; label borrows Daniel Kahneman&\#x27;s term for fast, automatic judgment: instead of a large model reasoning step-by-step over audio, Marimba answers typed speech questions from a single forward pass of a small frozen encoder \(Qwen3-ASR-0.6B\) plus lightweight readout heads. The main comparison baseline, Qwen3-Omni \(30B-A3B\), is a far larger multimodal model from the same Qwen family that processes audio natively, while ECAPA and pyannote 3.1 are established speaker-verification and speaker-diarization systems used as reference points. Platt calibration, applied to the term-spotting scores, is a long-standing technique for mapping raw classifier scores to calibrated probabilities.

**「Cheaper per-task speech decisions, not a general audio model」** Speech-application developers can now obtain calibrated term-spotting, turn-end, speaker-change/count, and language-ID decisions from a single frozen 0.6B encoder — with Apache-2.0 weights, a hosted demo, and a pip-installable package released — instead of running a 30B-class omni model for these checks. The evidence supports adopting it per-task rather than as a general audio understander: every readout performs at chance on the unseen CochlScene scene-classification benchmark, and the dedicated Smart Turn v3.2 model still beats its turn-end head 0.982 vs 0.930 AUROC on Smart Turn&\#x27;s own test set.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.18330">[2611.18330] Marimba: A System One Model for Speech - arXiv.org</a></li>

</ul>
</details>

**Tags**: `#speech-processing`, `#audio-question-answering`, `#model-efficiency`, `#zero-shot-learning`, `#machine-learning-research`

---

<a id="item-tech-news-10"></a>
### [US and Nine Nations Sign San Francisco Declaration to Secure AI Supply Chains](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 7.0/10

On November 15, the United States signed the San Francisco Declaration with Australia, India, Israel, Japan, South Korea, Qatar, Singapore, the United Arab Emirates, and the United Kingdom, affirming that economic security is the foundation of national security and committing to jointly protect the sensitive technologies and critical infrastructure that support superintelligence \(SI\) supply chains. The declaration establishes five working groups, covering innovation policy frameworks, SI applications in critical sectors, full-stack SI supply chain collaboration, safe harbors and supply chain security hubs, and SI security and resilience. The announcement comes from a US State Department release relayed via Telegram, and the working groups are set out as planned structures — the source specifies no operational details, timelines, or binding commitments beyond the declaration itself.

telegram · zaihuapd · Nov 16, 10:40

**「Background」** The declaration marks a new phase of Pax Silica, an initiative the United States launched in December 2025 to build resilient and diversified supply chains in strategic sectors including critical minerals, energy, semiconductors, and AI infrastructure. The signing took place on November 15 at the Pax Silica Founders Retreat convened by U.S. Under Secretary of State for Economic Affairs Jacob Helberg. According to the State Department, the pact aims to reduce participants&\#x27; reliance on U.S. adversaries for critical minerals, AI models, and semiconductor chips.

**「Impact」** The declaration commits ten governments to develop coordinated frameworks through five working groups, so companies in AI infrastructure, semiconductors, and adjacent critical-technology sectors across these markets should expect new cross-border expectations for protecting sensitive technologies and building supply-chain resilience — the planned &\#x27;safe harbors and supply-chain security hubs&\#x27; group in particular points to future compliance pathways that firms may need to qualify under. Reporting on the signing, including by the Times of India, frames the pact as part of the US effort to strengthen its technology position against China, which raises sourcing and market-access considerations for firms operating across both blocs; the declaration also marks a new phase of the US Pax Silica initiative launched in December 2025, extending coordination into critical minerals, energy, semiconductors, and AI infrastructure.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/San_Francisco_Declaration_on_the_Secure_Foundations_of_Enduring_Prosperity">San Francisco Declaration on the Secure Foundations of Enduring Prosperity</a></li>
<li><a href="https://www.investing.com/news/world-news/us-nine-nations-sign-san-francisco-declaration-on-ai-security-5028448">U.S., nine nations sign San Francisco declaration on AI security By...</a></li>
<li><a href="https://buzb.uz/en/news/us-and-nine-countries-sign-declaration-on-ai-supply-chain-security">US and Nine Countries Sign Declaration on AI Supply Chain Security</a></li>
<li><a href="https://www.youtube.com/watch?v=MGSXBmm-Ok0">India Joins US-Led San Francisco Declaration : How It... - YouTube</a></li>
<li><a href="https://timesofindia.indiatimes.com/business/india-business/india-joins-us-led-alliance-to-secure-ai-supply-chains-amid-china-tech-rivalry/articleshow/135886669.cms">India joins US-led alliance to secure AI supply chains amid China ...</a></li>
<li><a href="https://buzb.uz/en/news/us-and-nine-countries-sign-declaration-on-ai-supply-chain-security">US and Nine Countries Sign Declaration on AI Supply Chain Security</a></li>

</ul>
</details>

**Tags**: `#AI政策`, `#供应链安全`, `#地缘政治`, `#国际合作`, `#超级智能`

---

<a id="item-tech-news-11"></a>
### [AWS Blocks AI Agents That Stole API Keys to Self-Fund LLM Calls](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 7.0/10

Amazon&\#x27;s AWS reports that attackers used the open-source penetration-testing framework Artex to drive AI agents that stole API keys from publicly exposed LiteLLM and Dify deployments, validated them, and pooled them to pay for further large-model calls. The campaign ran from October 3 until November 5, when Amazon&\#x27;s MadPot honeypot network detected and blocked it. AWS attributes the operation with medium confidence to a China-linked threat group, states that not every listed target was actually compromised, and says it has notified potentially affected AWS customers. This is a vendor account relayed secondhand by Cybernews, not an independently verified measurement.

telegram · zaihuapd · Nov 16, 13:00

**「Background」** LiteLLM, Dify, and One API are open-source LLM gateway and app-building platforms that store AI provider API keys, so deployments left exposed to the public internet are prime targets for credential theft. MadPot, the system that caught this campaign, is Amazon&\#x27;s globally distributed network of decoy threat sensors, while Artex is an open-source agentic AI penetration-testing framework that the threat actors repurposed to drive the autonomous attacks. According to Amazon&\#x27;s security blog, MadPot captured requests from the ARTEX-driven agents that included the agents&\#x27; own operating memory from the offensive campaigns, which is how Amazon&\#x27;s threat intelligence team reconstructed the attack chain.

**「Impact」** Organizations running internet-exposed LLM infrastructure are the direct target set: Amazon&\#x27;s decoy records name hundreds of targets including the LiteLLM, One API, and Veloera gateways and the FastGPT and Dify app builders, and developers are advised to check default logins, exposed secrets, and unusual model spend, since stolen keys are pooled to fund attackers&\#x27; LLM calls at the victims&\#x27; expense. AWS says it has notified potentially affected customers, but the confirmed evidence comes from honeypot interactions, so actual key theft at the named targets remains unverified.

<details><summary>References</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/">Amazon Threat Intelligence observes threat actors running ...</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify ...</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM, Dify ...</a></li>
<li><a href="https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/">AI credential theft campaign used stolen API keys to scale</a></li>
<li><a href="https://tbreak.com/ai-agents-hunt-litellm-dify-api-keys/">AI agents hunt exposed LiteLLM and Dify tools for API keys</a></li>

</ul>
</details>

**Tags**: `#ai-security`, `#api-security`, `#llm`, `#threat-intelligence`, `#cybercrime`

---

<a id="item-tech-news-12"></a>
### [US interim rule extends advanced AI chip export controls to remote access](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 7.0/10

The US Commerce Department issued an interim final rule on November 16 that extends export controls on advanced AI chips and servers to remote access, closing the loophole of reaching restricted chips through data centers in third countries. According to The Verge, the rule also requires licenses for re-exporting AI chips to Indonesia, Malaysia, Singapore, Thailand, and Brazil. Reuters reports the rule was drafted under the lead of the Treasury Department and the National Security Council and could further tighten China&\#x27;s access to advanced chips. As an interim final rule, it is issued regulation rather than an announced plan, though the supplied sources do not state its effective date or specific license review criteria.

telegram · zaihuapd · Nov 16, 14:44

**「Background」** US export controls on advanced AI chips, administered by the Commerce Department&\#x27;s Bureau of Industry and Security \(BIS\), have for years restricted the sale of high-end chips and servers to China. Because those rules governed physical shipments, restricted parties could still sidestep them by renting the same chips&\#x27; computing power through data centers and cloud services in third countries — the loophole the new interim final rule is explicitly designed to close.

**「Impact」** Companies exporting, re-exporting, or transferring advanced semiconductors to or within Indonesia, Malaysia, Singapore, Thailand, and Brazil now need licenses reviewed case-by-case with each country&\#x27;s export-control enforcement record weighed, and organizations that remotely access controlled chips through third-country data centers lose the workaround the previous controls left open. The license requirement does not apply to commercial recommender systems such as those used by online retailers or social media companies, but AI developers and cloud users routing compute through overseas facilities should audit whether their arrangements now trigger licensing.

<details><summary>References</summary>
<ul>
<li><a href="https://kpmg.com/us/en/taxnewsflash/news/2026/11/commerce-advanced-semiconductor-export-controls.html">U.S. Commerce restricts remote access to advanced ...</a></li>
<li><a href="https://www.nixonpeabody.com/insights/alerts/2026/11/16/bis-targets-remote-access-to-advanced-chips-through-overseas-data-centers">BIS targets remote access to advanced chips through overseas ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#regulation`, `#semiconductors`, `#tech policy`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed Chair Warsh says AI will shape economy and monetary policy, but could disappoint](https://www.cnbc.com/2026/11/16/fed-ai-task-force-kevin-warsh.html) ⭐️ 7.0/10

Federal Reserve Chairman Kevin Warsh told a San Francisco task force he assembled that artificial intelligence, which he referred to as &quot;super intelligence,&quot; will significantly affect the U.S. economy with important implications for monetary policy down the road. In prepared remarks outlining scenarios rather than predictions, he said AI could lift productivity and real growth, but could instead cause automation-driven job losses or could &quot;disappoint,&quot; with equity valuations falling after heavy investment and unemployment rising more notably.

rss · CNBC Finance · Nov 16, 18:46

**「Background」** Warsh, a former Fed governor from 2006 to 2011, took office as the central bank&\#x27;s chair in May 2026 and has since repeatedly framed AI as a potential productivity booster and disinflationary force. His use of the term &quot;super intelligence&quot; follows a September 2026 executive order by President Donald Trump directing federal agencies to use that term instead of &quot;artificial intelligence.&quot;

**「Impact」** Investors in AI-related stocks and workers in automation-exposed jobs are the groups the Fed chair singled out: his downside scenarios point to falling equity valuations after heavy capital investment or displacement-driven unemployment, landing on a market that AI expectations have already driven higher and prompted companies to keep raising capital to compete.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Kevin_Warsh">Kevin Warsh - Wikipedia</a></li>
<li><a href="https://www.federalreserve.gov/aboutthefed/bios/board/warsh.htm">Federal Reserve Board - Kevin Warsh, Chairman</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/artificial-intelligence/elon-musk-pledges-spacexsi-rebrand-after-trumps-executive-order-to-use-super-intelligence-moniker-president-trump-has-signed-the-executive-order-to-replace-artificial-intelligence">Elon Musk pledges SpaceXSI rebrand after Trump &#x27;s executive order ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/16/kevin-warsh-fed-ai-jobs-productivity-interest-rateshtml.html">Kevin Warsh sees an AI revolution coming. Now he has to ...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#Monetary Policy`, `#Artificial Intelligence`, `#Labor Market`, `#Productivity`

---

<a id="item-finance-news-2"></a>
### [Nvidia CEO Resigns; Analysts See AI Gains Shifting to Big Tech and Rival Chipmakers](https://www.cnbc.com/2026/11/14/nvidia-ai-trade-data-centers-congress.html) ⭐️ 7.0/10

Nvidia founder and CEO Jensen Huang resigned last week as the stock ended at $162.85 per share after its longest weekly losing streak since 2012. Experts on CNBC&\#x27;s &quot;ETF Edge&quot; — Roundhill Investments CEO Dave Mazza and analyst Dan Ives — said gains in the AI trade could rotate toward Big Tech cloud providers and rival chipmakers, with AMD and Broadcom each up close to 13% for the week.

rss · CNBC Finance · Nov 16, 12:13

**「Background」** Nvidia founder and CEO Jensen Huang resigned on Nov. 12, 2026, with CFO Colette Kress named interim CEO, capping a week of turmoil that produced the stock&\#x27;s longest weekly losing streak since 2012. Separately, Democrats won control of Congress in the Nov. 3 midterms, and some party lawmakers are already calling for restrictions on AI data-center construction.

**「Impact」** Nvidia investors face a lowered price target: Ives&\#x27; firm Yorkville Ives cut it to $225 from $300 on Thursday while keeping a buy rating, saying Nvidia remains roughly 2-3 years ahead of competitors. Ives also estimates that the Democratic-controlled Congress elected on Nov. 3 could stop 10% to as much as 20% of planned data centers from being built, though he says AI computing demand still exceeds supply four to one.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nacionale.com/en/articles/who-is-colette-kress-nvidia-cfo-interim-ceo-jensen-huang">Colette Kress named Nvidia interim CEO as Huang resigns</a></li>
<li><a href="https://www.cnbc.com/2026/11/05/democrats-data-center-restrictions-midterms.html">Top Democrats call to rein in AI buildout after midterms ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI trade`, `#ETFs`, `#semiconductors`, `#tech policy`

---

<a id="item-finance-news-3"></a>
### [Intel, CEO Lip-Bu Tan Sued by Shareholders Over Stock Plunge](https://www.investing.com/news/stock-market-news/intel-sued-by-shareholders-following-29-stock-plunge-5028171) ⭐️ 7.0/10

A Michigan pension fund filed a securities class action in San Jose federal court against Intel, CEO Lip-Bu Tan, and CFO David Zinsner, alleging they concealed weak PC demand and inventory buildup ahead of the company&\#x27;s below-expected fourth-quarter revenue and profit forecast issued October 29; Intel shares fell 28.6% the next day, erasing roughly $140 billion in market value. The suit seeks damages for investors who bought shares between July 23 and October 29, 2026.

telegram · zaihuapd · Nov 16, 11:10

**「Background」** On October 29, 2026, Intel issued fourth-quarter revenue and profit guidance below expectations, citing continued weakness in the PC market and manufacturing bottlenecks, and the following day its shares suffered their worst one-day rout in more than four decades, according to Bloomberg.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/10/29/intel-intc-q3-earnings-report-2026-.html">Intel (INTC) Q3 earnings report 2026 - CNBC</a></li>
<li><a href="https://www.bloomberg.com/news/articles/2026-10-29/intel-outlook-hurt-by-weak-market-for-personal-computer-chips">Intel Earnings: (INTC) Stock Sinks After PC Slump, Supply ...</a></li>

</ul>
</details>

**Tags**: `#Intel`, `#securities litigation`, `#semiconductors`, `#earnings guidance`, `#stock decline`

---

<a id="item-finance-news-4"></a>
### [NVIDIA Board Not Considering Jensen Huang&\#x27;s Return as CEO, CNBC Reports](https://www.cnbc.com/2026/11/16/nvidia-ceo-jensen-huang.html) ⭐️ 7.0/10

People familiar with the matter told CNBC that NVIDIA&\#x27;s board is not considering reinstating Jensen Huang as CEO and has hired law firm Wachtell Lipton to examine whether his conduct endangered national security or company secrets. The claims come from unnamed sources relayed secondhand, and the reported investigation&\#x27;s outcome is not yet known.

telegram · zaihuapd · Nov 17, 01:39

**「Background」** Jensen Huang stepped down as Nvidia&\#x27;s CEO earlier this month, with CFO Colette Kress named interim chief, and on November 10 the board announced the Wachtell Lipton probe, saying it had no reason to believe national security or Nvidia secrets were compromised. Calls for his return—including an open letter with more than 165,000 signatures and public support from President Trump—have grown since his departure.

**「Impact」** Nvidia shareholders are the most directly affected: the stock had already erased its 2026 gains and fallen after the company opened its investigation into Huang on November 9, and the board&\#x27;s reported focus on the probe rather than his return leaves the chipmaker&\#x27;s leadership unsettled.

<details><summary>References</summary>
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

**Tags**: `#nvidia`, `#corporate-governance`, `#jensen-huang`, `#national-security`, `#legal-investigation`

---