---
layout: default
title: "Horizon Summary: 2026-11-25 (EN)"
date: 2026-11-25
lang: en
---

> From 27 items, 1 important content pieces were selected

---

**Technology News**
1. [Attackers forge admin session cookies on Check Point management servers via V8 PRNG reconstruction](#item-tech-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Attackers forge admin session cookies on Check Point management servers via V8 PRNG reconstruction](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 8.0/10

GreyNoise reports an active intrusion campaign against Check Point security management servers, with the report&\#x27;s timeline showing the actor scanning and beginning exploitation of an HFS server at 2026-10-02 13:17:45 UTC. According to the report, each POST to the HFS loginSrp1 endpoint returns a new signed session cookie whose &quot;sid&quot; value is drawn from JavaScript&\#x27;s Math.random\(\), which is not a cryptographically secure random source; by conducting several logins in succession, the actor collected enough output to reconstruct the internal state of the V8 PRNG, recover the HFS session-cookie signing key, and forge a signed admin session cookie. The forged cookie gives the actor a valid administrator session, and GreyNoise describes the campaign as still active.

hackernews · louiereederson · Nov 24, 16:32 · [Discussion](https://news.ycombinator.com/item?id=50630594)

**「Background」** Check Point&\#x27;s Security Management Server and its Multi-Domain variant \(MDS\) are the central consoles used to manage an organization&\#x27;s Check Point firewalls, and vulnerabilities affecting them, such as CVE-2026-16232, can be exploited with nothing more than network access to the management server&\#x27;s IP address \(tool-2-3\). Check Point has also patched a critical management-server zero-day, CVE-2026-93616, which allowed attackers to run scripts remotely on the server without any account, password, or administrator action \(tool-2-2\). On the technical side, JavaScript&\#x27;s Math.random\(\) is not a cryptographic random source: in V8 it is produced by a predictable pseudorandom number generator whose internal state can be reconstructed from enough observed outputs, which is why session IDs or signing material derived from it can be predicted and forged.

**「Who is affected and what to do now」** Organizations running Check Point Security Management or Multi-Domain Security Management servers face active exploitation of CVE-2026-93616, a directory traversal and file upload flaw rated CVSS 9.8 that lets an attacker execute scripts on the server without any account, password, or administrator action, and Check Point acknowledges a handful of customers have already been attacked. Administrators should apply the vendor fix described in advisory sk1000171 and verify management servers are not reachable from the internet, since Grey Noise ties the campaign to exploit code for CVE-2026-16232 adapted from a public Metasploit module, which lowers the barrier for copycat attacks. For developers, the reported attack chain is concrete evidence that session identifiers derived from JavaScript&\#x27;s Math.random\(\) can be predicted from a modest sample of observed outputs, so any authentication token still built on non-cryptographic randomness should be moved to a cryptographically secure generator.

**「Community discussion」** omh points out that the report does not make clear how the attacker gained initial access, speculating that CVE-2026-16232 was the entry vector and questioning whether all of the affected organizations had their Check Point Security Management Servers exposed to the internet. 20after4 argues that Math.random\(\) itself should be made secure rather than fixing the hundreds of applications that use it incorrectly.

<details><summary>References</summary>
<ul>
<li><a href="https://www.securitylab.ru/news/577784.php">Check Point закрыла zero-day. Для взлома не нужен даже пароль</a></li>
<li><a href="https://alekseycheremnykh.ru/post/uyazvimost-bdu2026-10493-cve-2026-16232-v-check-point/">Уязвимость BDU:2026-10493 (CVE-2026-16232) в Check Point</a></li>
<li><a href="https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign">An Active Intrusion Campaign Against Check Point Security ...</a></li>
<li><a href="https://support.checkpoint.com/results/sk/sk1000171/">sk1000171 - CVE - 2026 -93616: Directory Traversal and File upload...</a></li>
<li><a href="https://www.securitylab.ru/news/577784.php">Check Point закрыла zero-day. Для взлома не нужен даже пароль</a></li>

</ul>
</details>

**Tags**: `#security`, `#vulnerability`, `#prng`, `#threat-intelligence`, `#session-management`

---