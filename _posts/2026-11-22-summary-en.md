---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 24 items, 9 important content pieces were selected

---

**Technology News**
1. [Riemann Hypothesis formalized and verified in Lean](#item-tech-news-1) ⭐️ 10.0/10
2. [GPGME double-free vulnerability before 2.3.0 prompts broad patching](#item-tech-news-2) ⭐️ 8.0/10
3. [Zhejiang University Demonstrates QRAM on Superconducting Chip Tianmu 2](#item-tech-news-3) ⭐️ 8.0/10
4. [Microsoft Previews RDMA over USB4 to Cluster PCs for Local AI](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenRouter Warns MiniMax Model Prompts May Have Been Read by Third Parties](#item-tech-news-5) ⭐️ 7.0/10
6. [Tesla Begins Rolling Out FSD v15 With Reality View, Claimed 25x Safety Gain](#item-tech-news-6) ⭐️ 7.0/10

**Technology Blog**
1. [Avoiding Blunders Beats Brilliant Insights in Code](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Trump, Xi, and Putin Hold First In-Person Trilateral Meeting at APEC in Shenzhen](#item-finance-news-1) ⭐️ 7.0/10
2. [Trump Threatens &\#x27;Huge Taxes&\#x27; on US Firms Building AI Data Centers Abroad](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Riemann Hypothesis formalized and verified in Lean](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 10.0/10

On November 20, 2026, Levent Alpöge released a Lean formalization of the Riemann Hypothesis, a codebase of roughly 17 million lines produced with Claude and a human expert in the loop. The following day, the Lean FRO and the Mathlib Initiative issued a joint statement certifying the result, reporting that the formalized statement matches Mathlib&\#x27;s existing RiemannHypothesis definition, that the codebase compiles without errors, and that multiple independent proof checkers verified the proof. If the certification holds, the machine-checked proof settles one of the Clay Millennium Prize Problems, and the effort required formalizing a large portion of modern mathematics along the way.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** The Riemann Hypothesis, posed by Bernhard Riemann in 1859, concerns the location of the zeros of the Riemann zeta function and is one of the Clay Mathematics Institute&\#x27;s Millennium Prize Problems, having resisted proof for more than a century and a half. Lean is a proof assistant whose small trusted kernel mechanically verifies formal proofs, and Mathlib is its large community-maintained library of formalized mathematics, which already contained a canonical RiemannHypothesis statement that the new work was checked against. The formalization was produced with Anthropic&\#x27;s Claude writing much of the proof code under the guidance of human expert Levent Alpöge, part of a recent shift toward using large language models to formalize mathematics at a scale that previously demanded years of expert human effort.

**「Impact」** Mathematicians now have a machine-checked settlement of the 167-year-old conjecture: with the Lean FRO and Mathlib Initiative certifying that the formalized statement matches Mathlib&\#x27;s RiemannHypothesis definition and that the roughly 17-million-line proof compiles and passes multiple independent checkers, results long proved only &quot;conditional on RH&quot; can be grounded in a verified proof, though formal award of the Millennium Prize would still depend on the prize process&\#x27;s acceptance. The proof&\#x27;s author, number theorist Levent Alpöge, is on Anthropic&\#x27;s technical staff and produced the proof with Claude, so the result also stands as large-scale evidence that AI-assisted formalization can carry a major open problem end to end.

**「Community discussion」** Commenters disagreed about how much trust the verification deserves: rcr-anti argued that exploiting a kernel bug is now vanishingly unlikely because multiple independent kernels with their own consistency proofs \(con-leche and con-ron\) would all have to fail, while thejokeisonme countered that a fake Collatz refutation previously passed one of these independent checkers and noted that the certification&\#x27;s stated points do not rest on the human expert&\#x27;s involvement. Others, such as trio8453, argued the result owes as much to Alpöge&\#x27;s skill in directing Claude as to the model itself.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Levent_Alp%C3%B6ge">Levent Alpöge - Wikipedia</a></li>
<li><a href="https://www.clarin.com/us-news/who-is-levent-alpoge-the-anthropic-mathematician-who-claims-solved-the-riemann-hypothesis-with-claude_0_2WdGvYKBVM.html">Who is Levent Alpöge ? The Anthropic mathematician who claims he...</a></li>

</ul>
</details>

**Tags**: `#formal-verification`, `#theorem-proving`, `#ai-assisted-mathematics`, `#lean`, `#riemann-hypothesis`

---

<a id="item-tech-news-2"></a>
### [GPGME double-free vulnerability before 2.3.0 prompts broad patching](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 8.0/10

A coordinated security announcement discloses a double-free vulnerability with potential code execution in GPGME versions prior to 2.3.0, affecting all software that links the library—whether as a shared library, DLL, or statically—including Gpg4win, GnuPG Desktop, GnuPG VS-Desktop, most mail clients, many XMPP clients, Samba, and Flatpak. Per advisory text quoted in the discussion, the bug was found by Johan Carlsson, GitLab notified the developers on 2026-11-12, and disclosure originally planned for 2026-11-25 was moved up to 2026-11-20 after GitLab had to ship an early update for the separate Ruby2Shell bug. Commenters note that code execution in GitLab&\#x27;s signed-commit path is especially serious, with a related patch for GitLab Omnibus already available; GPGME 2.3.0 is the first version outside the affected range.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is GnuPG&\#x27;s library for integrating OpenPGP signing and encryption into applications, and every program using a version earlier than 2.3.0 is affected regardless of whether the library is loaded as a shared library, a Windows DLL, or statically linked; named consumers include Samba, Gpg4win, GnuPG Desktop, GnuPG VS-Desktop, most mail clients, many XMPP clients, and Flatpak. The flaw is tracked as CVE-2026-129975 and was discovered by Johan Carlsson, with GnuPG notified through GitLab on 2026-11-12; the original coordinated disclosure date of 2026-11-25 was moved up to 2026-11-20 after GitLab had to update early for the separate Ruby2Shell bug. The advisory notes that version 2.3.0 itself was never publicly available, so a patch for older versions is attached to the announcement.

**「Impact」** Applications linking GPGME before version 2.3.0—whether as a shared library, DLL, or statically linked—are exposed to potential code execution, and the affected software spans most email clients, most XMPP clients, Flatpak, Samba, and Gpg4win. Administrators should update the shared library to GPGME 2.3.1 \(Windows users can get the fixed DLL via Gpg4win 5.1.2\), while vendors of statically linked binaries must rebuild against 2.3.1, since replacing only the shared library leaves those builds vulnerable.

**「Community discussion」** Commenters debated the severity framing, with one arguing it is &quot;a double free bug, not an RCE chain&quot; and asking whether vulnerability reports are intentionally overstated, while another reported that Red Hat&\#x27;s downstream gpgme package appears to have contained a fix for roughly five years—found via conventional tooling—without it ever reaching upstream. Another commenter quoted the advisory&\#x27;s affected-software list and asked whether apt is affected, a question the supplied comments do not definitively answer.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[ Announce ] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://www.openwall.com/lists/oss-security/2026/11/20/13">oss-security - Fwd: GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html">[Announce] GnuPG Security Advisory for GPGME ...</a></li>
<li><a href="https://www.phoronix.com/news/GnuPG-GPGME-Critical">GnuPG&#x27;s GPGME Affected By Critical Security Bug In Turn... - Phoronix</a></li>
<li><a href="https://thehackernews.com/2026/11/gnupg-warns-critical-gpgme-flaw-could.html">GnuPG Warns Critical GPGME Flaw Could Expose App Data via...</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerability`, `#cryptography`, `#open-source`, `#memory-safety`

---

<a id="item-tech-news-3"></a>
### [Zhejiang University Demonstrates QRAM on Superconducting Chip Tianmu 2](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

A Zhejiang University team has implemented quantum random access memory \(QRAM\) on a real superconducting quantum processor for the first time, running prototypes on its self-fabricated &quot;Tianmu 2&quot; chip, according to a Sina Finance report. The results, said to be published in Nature Physics, show retrieval of 4-bit and 8-bit data at accuracies of 80.9% and 60.4% respectively, with circuit depth reduced by more than 30% compared with an unoptimized scheme. The team also reports verifying for the first time that the architecture has local noise resilience. The researchers&\#x27; stated next step is work on scaling QRAM.

telegram · zaihuapd · Nov 21, 08:31

**「What is QRAM?」** Quantum random access memory \(QRAM\) is a long-theorized component that would let quantum computers load classical data in quantum superposition — the &quot;high-speed memory&quot; that algorithms such as quantum search and quantum machine learning assume, but which real hardware has struggled to provide. Accessing classical data is a recognized bottleneck for practical quantum computing, and memory readout is highly sensitive to noise, so QRAM has previously existed largely as a theoretical proposal rather than a demonstrated architecture on an actual quantum processor.

**「Impact」** The demonstration gives quantum algorithm researchers hardware evidence that QRAM, a long-theorized component needed for quantum search and quantum machine learning, can run on superconducting chips with reduced circuit depth and tolerance of local noise. However, with a maximum capacity of 8 bits and retrieval accuracy dropping to 60.4% at that size, the practical usefulness of the memory at algorithm-relevant scales remains unproven.

<details><summary>References</summary>
<ul>
<li><a href="https://ukquantum.org/chinese-scientists-demonstrate-quantum-random-access-memory-architecture-aimed-at-solving-data-bottleneck/">Chinese Scientists Demonstrate Quantum Random Access Memory ...</a></li>

</ul>
</details>

**Tags**: `#quantum computing`, `#quantum hardware`, `#QRAM`, `#superconducting qubits`, `#research`

---

<a id="item-tech-news-4"></a>
### [Microsoft Previews RDMA over USB4 to Cluster PCs for Local AI](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft has released a developer preview of RDMA over USB4 for Windows, allowing multiple PCs to share memory and GPU compute over ordinary USB4 cables—without dedicated network cards or switches—to run a single large local AI model. The capability was demonstrated on three AMD Ryzen AI Max+ 395 machines jointly running Qwen3-235B-A22B at 4-bit quantization at roughly 18.5 tokens/s. The feature is still a preview and will be delivered through the Windows Insider program rather than shipping as a generally available Windows capability, and the demonstrated throughput of ~18.5 tokens/s reflects a vendor demo rather than an independently measured result.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA \(Remote Direct Memory Access\) is a long-standing data-center technique that lets one machine read and write another computer&\#x27;s memory directly, but it has conventionally required dedicated network adapters and switches rather than ordinary cables — exactly the hardware Microsoft&\#x27;s USB4 approach removes. The appeal for local AI is memory capacity: even at 4-bit quantization, a 235-billion-parameter model needs roughly 120 GB before KV-cache and system overhead, which strains or exceeds a single consumer machine. AMD&\#x27;s Ryzen AI Max+ 395, available in a 128 GB configuration, is already a popular platform for this kind of local inference — one community benchmark shows a single unit running a much smaller 27B model at 4-bit quantization at about 12 tokens per second.

**「What it changes」** For local-LLM developers, the concrete consequence is that support must be built rather than inherited: the feature reaches applications only through Windows&\#x27; NetworkDirect API — the same interface Windows uses with datacenter RDMA adapters — so an inference framework has to be made compatible before existing tools see any benefit. For users, trying it requires Windows 11 machines with working host-to-host USB4 networking, since the preview layers RDMA onto that existing peer-to-peer USB4 tunnel instead of requiring dedicated network cards or switches.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=MGS4ZnL8fwg">External GPU vs Desktop Tower For Local AI - YouTube</a></li>
<li><a href="https://gagadget.com/ru/artificial-intelligence/735249-resursyi-neskolkih-pk-dlya-zapuska-tyazhelogo-ii-nauchilas-obedinyat-microsoft-cherez-usb4/">Microsoft реализовала RDMA через USB 4 для ИИ-кластеров</a></li>
<li><a href="https://techcommunity.microsoft.com/blog/microsoftusbblog/introducing-rdma-over-usb4%C2%AE-on-windows-run-larger-local-ai-models-across-pcs/4574602">Introducing RDMA over USB 4 ® on Windows : run larger local AI...</a></li>
<li><a href="https://www.techpowerup.com/355062/microsoft-brings-rdma-over-usb4-to-windows-11-for-daisy-chained-pcs">Microsoft Brings RDMA over USB 4 to Windows 11 for... | TechPowerUp</a></li>

</ul>
</details>

**Tags**: `#distributed inference`, `#RDMA`, `#USB4`, `#local LLM`, `#Microsoft Windows`

---

<a id="item-tech-news-5"></a>
### [OpenRouter Warns MiniMax Model Prompts May Have Been Read by Third Parties](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

OpenRouter has reportedly emailed users warning that requests sent to MiniMax models may have been read by third parties. According to the notification, security researchers sent prompts containing test \(canary\) URLs to MiniMax models between July and October 2026, and third parties accessed those URLs 40 to 130 hours after the prompts were sent. OpenRouter attributes the problem to MiniMax and its forwarding providers AtlasCloud, Novita, and StreamLake, has removed the &quot;zero data retention&quot; label from the affected endpoints, and advises users who sent sensitive credentials to rotate their API keys and passwords. The warning is based on email notifications; as of the report, OpenRouter had not published related information on its official website, and the findings have not been independently confirmed.

telegram · zaihuapd · Nov 21, 06:53

**「Background」** OpenRouter operates an API marketplace that routes each user request to a chosen model provider, so prompts sent through it pass through upstream forwarders and suppliers rather than going directly to the model&\#x27;s developer. Endpoints listed on the marketplace can carry a &quot;zero data retention&quot; designation signaling that request content is not stored — a distinction that matters because upstream providers can still see prompts on third-party models. The evidence in this case came from canary-style testing, in which researchers embed unique URLs in prompts so that any later fetch of a URL reveals the prompt content was accessed after the fact.

**「Impact」** Users who sent prompts containing secrets — API keys, passwords, or internal URLs — to MiniMax models via OpenRouter between July and October should rotate those credentials as OpenRouter&\#x27;s notification advises; the 40–130 hour delay before third parties accessed the canary URLs indicates prompts were retained and later read rather than only passed through in transit. Removal of the &quot;zero data retention&quot; labels also means compliance-sensitive workloads can no longer assume MiniMax-routed traffic is ephemeral, and OpenRouter&\#x27;s model page still lists StreamLake, one of the implicated forwarders, among the seven providers serving MiniMax M3, so developers who keep using these models should pin routing to unaffected providers.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/">OpenRouter</a></li>
<li><a href="https://cdn.venice.ai/blog/venice-vs-openrouter">Venice.ai vs OpenRouter : API Comparison (2026)</a></li>
<li><a href="https://openrouter.ai/minimax/minimax-m3">MiniMax M3 - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**Tags**: `#llm-security`, `#data-privacy`, `#openrouter`, `#minimax`, `#api-data-retention`

---

<a id="item-tech-news-6"></a>
### [Tesla Begins Rolling Out FSD v15 With Reality View, Claimed 25x Safety Gain](https://x.com/Tesla/status/2124222447855743019) ⭐️ 7.0/10

Tesla announced it has begun rolling out FSD v15, a new major version of its neural-network-based Full Self-Driving software, to vehicles in overseas markets \(outside China, per the Chinese-language relay of the company&\#x27;s post\). Tesla claims the update improves handling of safety-critical scenarios by 25x, a vendor figure that has not been independently verified or measured. New in this version is a &quot;Tesla Reality View&quot; interface that overlays live camera imagery with FSD&\#x27;s driving plan on the in-car screen, with full-screen, map, split-screen, and quiet modes. The release also overlays turn information on the navigation view, softens the turn-signal chime so it fades gradually, and refines behavior over potholes and road debris as well as speed control in school zones and bad weather.

telegram · zaihuapd · Nov 22, 00:03

**「Background」** Tesla&\#x27;s Full Self-Driving \(FSD\) is a driver-assistance system whose driving behavior is produced by an end-to-end neural network, and Tesla describes v15 as an upgrade to every part of that network. Ahead of the rollout, Tesla had signaled that v15 would implement roughly a 10x increase in model parameters to let the system handle more driving nuances, and coverage of the release notes that its improvement list matches FSD&\#x27;s most-cited current weaknesses, including sign detection, potholes, and school-zone speed handling.

**「Impact」** For Tesla owners with a paid FSD \(Supervised\) subscription, the update brings concrete driving refinements — smoother handling of potholes and road debris, adjusted speed control near schools and in bad weather — plus the new Reality View overlay showing camera imagery with the system&\#x27;s planned path; however, the headline 25x improvement in safety-critical scenarios is Tesla&\#x27;s own claim and has not been independently measured. The rollout also appears staged rather than fleet-wide: Musk previously indicated v15 would reach wide release with the upcoming holiday update, so many FSD owners will likely receive the features later rather than immediately.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=eNBqkc7V1nU">Introducing Tesla Self-Driving V 15 - YouTube</a></li>
<li><a href="https://www.notateslaapp.com/news/5057/tesla-fsd-v15-coming-next-month-with-holiday-update-musk">Tesla FSD V 15 Arriving Next Month: Home Garage... - Not a Tesla App</a></li>
<li><a href="https://electrek.co/">Electrek | EV and Tesla News, Green Energy, Ebikes, and more</a></li>
<li><a href="https://www.notateslaapp.com/news/5057/tesla-fsd-v15-coming-next-month-with-holiday-update-musk">Tesla FSD V 15 Arriving Next Month: Home Garage... - Not a Tesla App</a></li>

</ul>
</details>

**Tags**: `#autonomous-driving`, `#tesla`, `#artificial-intelligence`, `#machine-learning`, `#software-update`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Avoiding Blunders Beats Brilliant Insights in Code](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Many engineers treat programming as a search for brilliant insights and beautiful abstractions. Sean Goedecke argues this is the wrong frame: writing good code is mainly about not making catastrophic mistakes.

**「Solution」** His central observation is that programming, unlike basketball—where a 99-1 lead can absorb blunders—offers no durable winning advantage: one bad decision can turn an elegant codebase into a janky one. Characteristic blunders include building a parallel system for an existing task, adding a second source of truth for key data, turning a safe synchronous operation into a delicate async one, and complicating a key interface. The cardinal sins are inconsistency, which breaks the trust that code works the sensible way and forces engineers to hunt for surprises, and unnecessary requirements, which are sticky—only the original implementer had the context to question them, so later readers must assume they are necessary—and interact combinatorially, forcing every new feature to be checked against every existing one. He advises placing your task where it fits most normally into the current codebase and trimming it to the smallest set of requirements, so single-mindedly that the thought &quot;I could use this clever pattern&quot; is itself a warning sign of distraction. He scopes the claim to large commercial codebases \(&quot;impure engineering&quot;\), admits his chess estimate \(never blundering ≈ a 1600-1700 rating\) is only a guess, and notes that current coding agents match humans on consistency but are far worse at avoiding unnecessary requirements.

**「Takeaway」** You don&\#x27;t have to be clever to do great programming work—sometimes cleverness is a disadvantage. Whether writing code by hand or driving an AI agent, the winning discipline is attention to detail and focus on maintaining consistency while refusing unnecessary requirements.

**Tags**: `#software-engineering`, `#code-quality`, `#engineering-judgment`, `#opinion-essay`, `#complexity-management`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Trump, Xi, and Putin Hold First In-Person Trilateral Meeting at APEC in Shenzhen](https://www.cnbc.com/2026/11/21/china-xi-trump-putin-global-diplomacy-shenzhen.html) ⭐️ 7.0/10

U.S. President Donald Trump, Chinese President Xi Jinping, and Russian President Vladimir Putin held their first-ever in-person meeting together at the APEC summit in Shenzhen on Thursday, where Trump said the three countries are &quot;uniquely positioned&quot; to discuss reducing nuclear weapons, and a Chinese readout said they discussed Ukraine, the Middle East, and the Korean Peninsula. At the same meeting, Xi announced China would provide $20 million in support for the Asia-Pacific region.

rss · CNBC Finance · Nov 21, 06:00

**「Background」** APEC, the Asia-Pacific Economic Cooperation forum, is holding its annual leaders&\#x27; meeting in Shenzhen, which China is hosting. The trilateral continues a pattern of Chinese summit diplomacy: in September 2025 Xi brought Putin and Indian Prime Minister Modi together at the Shanghai Cooperation Organization, a Eurasian regional grouping, in Tianjin, and in 2023 China provided the forum for restoring diplomatic ties between Saudi Arabia and Iran. Per CNBC&\#x27;s tally of official readouts, Xi has hosted more than 40 heads of state this year, on top of over 60 state visits in 2025.

**Tags**: `#geopolitics`, `#diplomacy`, `#US-China relations`, `#APEC`, `#Russia`

---

<a id="item-finance-news-2"></a>
### [Trump Threatens &\#x27;Huge Taxes&\#x27; on US Firms Building AI Data Centers Abroad](https://apnews.com/article/trump-artificial-intelligence-data-centers-f1ac03b73d13445400eeed8631d9d879) ⭐️ 7.0/10

At a Nov 20 White House press conference, President Trump said he intends to impose &quot;huge taxes&quot; on US tech companies that build AI data centers abroad, aiming to keep such facilities in the US and preserve America&\#x27;s AI lead over China; he gave no tax rate, legislative plan, or timeline, and said he had not yet told officials in his administration. He also urged US communities to accept data centers and to negotiate payments from developers, as local opposition to new projects has grown over electricity demand and noise.

telegram · zaihuapd · Nov 21, 03:26

**「Background」** AI data centers are warehouse-sized buildings packed with computers that train and run AI systems, and they consume huge amounts of electricity — a reason some US communities have resisted new projects. Trump views the data-center buildout as a boon to the US economy — an assessment most economists share, with caveats — and as key to staying ahead of China in AI.

**「Impact」** If carried out, the tax threat would land on US tech firms pouring money into AI data centers abroad — including OpenAI&\#x27;s announced overseas buildout plans and multi-gigawatt projects in places like Malaysia, a growing data center hub — raising the cost of expanding AI infrastructure outside the US.

<details><summary>References</summary>
<ul>
<li><a href="https://www.yahoo.com/news/politics/articles/trump-says-plans-penalize-us-174503646.html">Trump seeks to penalize US companies that build AI data centers ...</a></li>
<li><a href="https://tech.yahoo.com/general/article/trump-threatens-us-companies-that-build-data-centers-in-other-countries-as-americans-increasingly-oppose-the-facilities-in-their-communities-202048230.html">Trump threatens U . S . companies that build data centers in other...</a></li>
<li><a href="https://www.technologyreview.com/2025/05/20/1116327/ai-energy-usage-climate-footprint-big-tech/">We did the math on AI ’s energy footprint. | MIT Technology Review</a></li>

</ul>
</details>

**Tags**: `#US policy`, `#AI data centers`, `#corporate taxation`, `#US-China AI competition`, `#tech investment`

---