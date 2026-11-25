---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 27 条内容中筛选出 1 条重要资讯。

---

**科技新闻**
1. [Check Point 管理服务器遭 V8 随机数状态重建攻击，管理员会话可被伪造](#item-tech-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Check Point 管理服务器遭 V8 随机数状态重建攻击，管理员会话可被伪造](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 8.0/10

威胁情报机构 GreyNoise 发布报告，披露一场针对 Check Point 安全管理服务器（Security Management Server）的仍在进行中的入侵活动。攻击者向 HFS 服务器的 loginSrp1 端点连续发起登录请求，每次 POST 都会返回一个含 sid 值的签名会话 Cookie，而该 sid 由 JavaScript 的 Math.random\(\) 生成；攻击者通过连续多次登录收集足够的伪随机数输出，重建 Node.js V8 伪随机数生成器的内部状态，进而恢复 HFS 会话 Cookie 的签名密钥，并伪造出已签名的管理员会话 Cookie。报告引用的日志显示，针对 HFS 服务器的扫描与利用始于 2026 年 10 月 2 日 13:17 UTC。攻击者获得初始访问的具体途径在现有材料中未被说明。

hackernews · louiereederson · 11月24日 16:32 · [社区讨论](https://news.ycombinator.com/item?id=50630594)

**「背景」** Check Point 安全管理服务器（Security Management Server/MDS）是集中管理防火墙与安全策略的组件，该产品线此前已暴露多个可远程利用的漏洞：CVE-2026-16232 的利用条件是攻击者能够网络访问管理服务器的 IP 地址，而零日漏洞 CVE-2026-93616 则无需账号、密码或管理员交互即可在管理服务器上远程执行脚本。就本次攻击的核心技术而言，JavaScript 的 Math.random\(\) 由 V8 引擎中的非加密伪随机数生成器实现，观察足够多的连续输出即可重建其内部状态，因此这类输出历来不适合作为会话标识符等安全令牌的随机来源。

**「影响」** 对运行 Check Point Security Management Server\(含 Multi-Domain Security Management Server\)的组织,Check Point 官方公告 sk1000171 已确认 CVE-2026-93616\(目录遍历与文件上传,CVSS 9.8\)正在野外被利用,并有少数客户遭到攻击,且利用过程无需任何账号、密码或管理员交互;管理员应立即按公告完成修复,并排查管理服务器是否已被入侵——GreyNoise 博客公开的利用脚本摘录显示,攻击者据称正是借此向受害服务器发送命令。对更广泛的开发者,这条攻击链给出了可迁移的教训:用 Math.random\(\) 等非加密随机源生成会话 ID,在攻击者收集到足够输出样本后即可重建 V8 PRNG 状态并伪造签名管理员会话 Cookie,因此所有安全令牌都应改用加密安全的随机数生成器。

**「社区讨论」** 评论中的实质性讨论集中在两个问题上：用户 omh 表示尚不清楚攻击者如何取得初始访问，并推测多个 Check Point 客户之间的关联可能指向 CVE-2026-16232，进而质疑这些组织是否将安全管理服务器直接暴露在互联网上；用户 20after4 则主张应从 Math.random\(\) 本身入手、让随机数生成器至少具备基本安全性，而不是逐一修复数以百计错误使用它的应用。以上均为评论者的个人推测与观点，并非已证实的事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.securitylab.ru/news/577784.php">Check Point закрыла zero-day. Для взлома не нужен даже пароль</a></li>
<li><a href="https://alekseycheremnykh.ru/post/uyazvimost-bdu2026-10493-cve-2026-16232-v-check-point/">Уязвимость BDU:2026-10493 (CVE-2026-16232) в Check Point</a></li>
<li><a href="https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign">An Active Intrusion Campaign Against Check Point Security ...</a></li>
<li><a href="https://support.checkpoint.com/results/sk/sk1000171/">sk1000171 - CVE - 2026 -93616: Directory Traversal and File upload...</a></li>
<li><a href="https://www.securitylab.ru/news/577784.php">Check Point закрыла zero-day. Для взлома не нужен даже пароль</a></li>

</ul>
</details>

**标签**: `#security`, `#vulnerability`, `#prng`, `#threat-intelligence`, `#session-management`

---