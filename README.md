# Linux VPS: A Practical Buyer's Guide to Choosing the Right Plan, Specs, and Provider for Your Workload

So you typed "Linux VPS" into a search box. That could mean a lot of things — a $5/mo box to mess around with, a production server for a side project, a low-latency node for users in mainland China, or a beefy machine to run containers. The specs that matter for each of those are very different, and most buying guides gloss over the part where you actually match a plan to what you're trying to do.

This guide walks through what to look for in a Linux VPS in 2026, then uses BandwagonHost (often called 搬瓦工 in Chinese-speaking communities) as a concrete example — because their catalog happens to span the full range from $49.99/year budget KVM boxes to $1,889.99/month premium CN2 GIA nodes in Hong Kong. That range makes it useful for explaining how the trade-offs actually work.

## What You're Actually Paying For When You Buy a Linux VPS

A VPS is a slice of a physical server, virtualized so you get your own OS install, root access, and dedicated resources. The "Linux" part means the host gives you a Linux distribution — typically AlmaLinux, RockyLinux, CentOS, Debian, Ubuntu, CentOS Stream, or Fedora — and you're responsible for everything above the kernel.

The price of a VPS reflects four things, roughly in this order:

**Network quality.** This is the single biggest cost driver, and the one most beginners underestimate. A $49.99/year box on a commodity route and a $89.99/month box on China Telecom's CN2 GIA network might have similar CPU and RAM, but the network behind them is not even in the same category. We'll get into why below.

**Hardware tier.** Enterprise-grade RAID-10 SSD storage, owned equipment (vs. leased), and owned IP space all cost more. They also fail less and recover faster when they do fail.

**Resource allocation.** RAM, CPU cores, storage, and monthly transfer (bandwidth). KVM virtualization gives you real resource isolation — a noisy neighbor on the same physical box can't tank your performance the way it can on container-based virtualization.

**Support model.** Self-managed means the provider handles hardware, network, and infrastructure, and you handle everything above the OS. That's why budget VPS pricing is what it is. If you want someone to fix your Apache config, you're shopping in the wrong category.

## The CN2 GIA Question (And Why It Matters for Linux VPS Buyers)

If your users are anywhere near mainland China, or you're running cross-border VOIP, video conferencing, online gaming, or serving web content to Chinese visitors, the network tier matters more than almost any spec on the sheet.

China Telecom offers four tiers of IP transit. The cheapest, AS4134 (ChinaNet/163), is what most cloud operators use. It's cheap, has huge capacity (good for absorbing DDoS), and gets congested during peak hours — packet loss rates can hit 30% or more. At that level, reliably serving web content or holding a video call is basically impossible.

CN2 GIA (AS4809, Global Internet Access) is the other end. It's the most expensive tier — transit prices can run up to $120 per megabit in some markets, which is why a 1 Gbps CN2 GIA commit can theoretically run into six figures a month. It's also capacity-limited and not DDoS-tolerant. But it's stable. The third option, CTGNet (AS23764), is the newest and in practice performs about the same as CN2 GIA.

The practical takeaway: if you're buying a Linux VPS and your audience isn't in China, you don't need CN2 GIA and paying for it is waste. If your audience is in China, CN2 GIA (or the equivalent CTGNet/CMIN2/CUP routing) isn't a luxury — it's the difference between a service that works and one that doesn't.

## BandwagonHost as a Worked Example

BandwagonHost is operated by IT7 Networks Inc., a Canadian company that's been in the VPS business since 2004. They own their hardware and IP space, run KVM virtualization, and use a self-developed control panel called KiwiVM. The service is strictly self-managed, which is how they keep pricing competitive.

What makes them useful for this guide is that their plan catalog spans the full price range, so you can see exactly what each tier gets you. They also have a feature that's genuinely rare: free, in-panel datacenter migration without data loss. If you buy a plan that's eligible for multiple datacenters and traffic patterns shift, you can move your VPS between locations from the control panel.

KiwiVM gives you: start/stop, OS reload, emergency console, rDNS (PTR) management, snapshots, usage statistics, API access, and the migration feature mentioned above. Over 20 OS templates are available, in 32 and 64-bit versions, and you can request ISO images that aren't in the default list.

All plans include 1–10 Gigabit uplink, 24/7 service monitoring (nodes checked every minute), weekly security audits, and a 30-day refund policy. IPv4 is one dedicated address; IPv6 is a routed /64 subnet. Full root access is standard.

## The Full Plan Lineup (Verified Against the Official Site)

Below is every plan currently listed on BandwagonHost's official site, grouped by tier. Prices are in USD. I've included purchase links that deep-link to each specific plan using the affiliate structure — these go through the affiliate redirect and then to the cart page for that exact product.

### Standard KVM VPS (Budget Tier — No Premium Routing)

These are the entry-level plans. Multiple US, EU, and other datacenter locations. No CN2 GIA routing. Best for personal sites, dev environments, learning Linux, and anything where the user isn't in mainland China.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 20G KVM | 1 GB | 2 vCPU | 20 GB RAID-10 SSD | 1 TB/mo | 1 Gigabit | $49.99/year | [Order 20G KVM](https://bwh81.net/aff.php?aff=77528&pid=44) |
| 40G KVM | 2 GB | 3 vCPU | 40 GB RAID-10 SSD | 2 TB/mo | 1 Gigabit | $52.99/half-year | [Order 40G KVM](https://bwh81.net/aff.php?aff=77528&pid=45) |
| 80G KVM | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 3 TB/mo | 1 Gigabit | $19.99/month | [Order 80G KVM](https://bwh81.net/aff.php?aff=77528&pid=46) |
| 160G KVM | 8 GB | 5 vCPU | 160 GB RAID-10 SSD | 4 TB/mo | 1 Gigabit | $39.99/month | [Order 160G KVM](https://bwh81.net/aff.php?aff=77528&pid=47) |
| 320G KVM | 16 GB | 6 vCPU | 320 GB RAID-10 SSD | 5 TB/mo | 1 Gigabit | $79.99/month | [Order 320G KVM](https://bwh81.net/aff.php?aff=77528&pid=48) |
| 480G KVM | 24 GB | 7 vCPU | 480 GB RAID-10 SSD | 6 TB/mo | 1 Gigabit | $119.99/month | [Order 480G KVM](https://bwh81.net/aff.php?aff=77528&pid=49) |

The 20G KVM at $49.99/year is one of the better budget VPS deals you'll find. If you just need a Linux box to learn on, run a personal blog, or host a small project, this is the tier. Don't overbuy here — the money is better spent on the next tier up only if you actually need CN2 GIA routing.

### CN2 GIA-E (E-Commerce Tier — Premium Routing, Best Value for China)

This is the middle tier and the one most people with China-facing workloads should actually be looking at. Plans get access to DC6 (CN2 GIA-E) and DC9 (CN2 GIA) in Los Angeles, plus Japan Softbank, Netherlands (9929 routing), and other locations. Triple-network routing (CN2 GIA + CMIN2 + China Unicom Premium) is included. Bandwidth is 2.5–10 Gigabit depending on plan size.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| CN2 GIA-E 20G | 1 GB | 2 vCPU | 20 GB RAID-10 SSD | 1 TB/mo | 2.5 Gigabit | $49.99/quarter | [Order CN2 GIA-E 20G](https://bwh81.net/aff.php?aff=77528&pid=87) |
| CN2 GIA-E 40G | 2 GB | 3 vCPU | 40 GB RAID-10 SSD | 2 TB/mo | 2.5 Gigabit | $89.99/quarter | [Order CN2 GIA-E 40G](https://bwh81.net/aff.php?aff=77528&pid=88) |
| CN2 GIA-E 80G | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 3 TB/mo | 2.5 Gigabit | $56.99/month | [Order CN2 GIA-E 80G](https://bwh81.net/aff.php?aff=77528&pid=89) |
| CN2 GIA-E 160G | 8 GB | 6 vCPU | 160 GB RAID-10 SSD | 5 TB/mo | 5 Gigabit | $86.99/month | [Order CN2 GIA-E 160G](https://bwh81.net/aff.php?aff=77528&pid=90) |
| CN2 GIA-E 320G | 16 GB | 8 vCPU | 320 GB RAID-10 SSD | 8 TB/mo | 5 Gigabit | $159.99/month | [Order CN2 GIA-E 320G](https://bwh81.net/aff.php?aff=77528&pid=91) |
| CN2 GIA-E 640G | 32 GB | 10 vCPU | 640 GB RAID-10 SSD | 10 TB/mo | 10 Gigabit | $289.99/month | [Order CN2 GIA-E 640G](https://bwh81.net/aff.php?aff=77528&pid=92) |
| CN2 GIA-E 1TB | 64 GB | 12 vCPU | 1 TB RAID-10 SSD | 12 TB/mo | 10 Gigabit | $549.99/month | [Order CN2 GIA-E 1TB](https://bwh81.net/aff.php?aff=77528&pid=93) |

The entry plan at $49.99/quarter (which works out to $169.99/year if you go annual) is the sweet spot for most cross-Pacific use cases. Annual billing on this plan saves about $30 versus paying quarterly, so if you're committing, go annual.

### Hong Kong CN2 GIA (Premium Tier — Lowest Latency to China)

These are the premium plans. Equinix HK2/HK3/HK8 facilities, CN2 GIA for China Telecom, direct connections for China Unicom and China Mobile. AMD EPYC with NVMe RAID-10 in HK3 and HK8. This is the tier where 5ms vs 30ms latency actually matters to your revenue — VOIP, gaming, financial applications, anything where being physically closest to mainland China users is the point.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HK CN2 GIA 40G | 2 GB | 2 vCPU | 40 GB RAID-10 SSD | 500 GB/mo | 1 Gigabit | $89.99/month | [Order HK 40G](https://bwh81.net/aff.php?aff=77528&pid=95) |
| HK CN2 GIA 80G | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 1 TB/mo | 1 Gigabit | $155.99/month | [Order HK 80G](https://bwh81.net/aff.php?aff=77528&pid=96) |
| HK CN2 GIA 160G | 8 GB | 6 vCPU | 160 GB RAID-10 SSD | 2 TB/mo | 1 Gigabit | $299.99/month | [Order HK 160G](https://bwh81.net/aff.php?aff=77528&pid=97) |
| HK CN2 GIA 320G | 16 GB | 8 vCPU | 320 GB RAID-10 SSD | 4 TB/mo | 1 Gigabit | $589.99/month | [Order HK 320G](https://bwh81.net/aff.php?aff=77528&pid=98) |
| HK CN2 GIA 640G | 32 GB | 10 vCPU | 640 GB RAID-10 SSD | 6 TB/mo | 1 Gigabit | $989.99/month | [Order HK 640G](https://bwh81.net/aff.php?aff=77528&pid=122) |
| HK CN2 GIA 1TB | 64 GB | 12 vCPU | 1 TB RAID-10 SSD | 8 TB/mo | 1 Gigabit | $1,889.99/month | [Order HK 1TB](https://bwh81.net/aff.php?aff=77528&pid=124) |

These are priced for businesses. If you're an individual running a personal project, you almost certainly don't need this tier — the CN2 GIA-E plans in Los Angeles give you most of the network benefit at a fraction of the cost.

### Tokyo CN2 GIA (Premium Tier — Japan, Equinix TY8)

Equinix TY8 location. CN2 GIA (China Telecom), 9929 (China Unicom), CMI (China Mobile). A middle-ground between Hong Kong pricing and Los Angeles latency — useful if you want Japan-based hosting with premium China routing but don't need Hong Kong's specific latency profile.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Tokyo 40G | 2 GB | 2 vCPU | 40 GB RAID-10 SSD | 500 GB/mo | 1.2 Gigabit | $89.99/month | [Order Tokyo 40G](https://bwh81.net/aff.php?aff=77528&pid=108) |
| Tokyo 80G | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 1 TB/mo | 1.2 Gigabit | $155.99/month | [Order Tokyo 80G](https://bwh81.net/aff.php?aff=77528&pid=109) |
| Tokyo 160G | 8 GB | 6 vCPU | 160 GB RAID-10 SSD | 2 TB/mo | 1.2 Gigabit | $299.99/month | [Order Tokyo 160G](https://bwh81.net/aff.php?aff=77528&pid=110) |
| Tokyo 320G | 16 GB | 8 vCPU | 320 GB RAID-10 SSD | 4 TB/mo | 1.2 Gigabit | $589.99/month | [Order Tokyo 320G](https://bwh81.net/aff.php?aff=77528&pid=111) |
| Tokyo 640G | 32 GB | 10 vCPU | 640 GB RAID-10 SSD | 6 TB/mo | 1.2 Gigabit | $989.99/month | [Order Tokyo 640G](https://bwh81.net/aff.php?aff=77528&pid=123) |
| Tokyo 1TB | 64 GB | 12 vCPU | 1 TB RAID-10 SSD | 8 TB/mo | 1.2 Gigabit | $1,889.99/month | [Order Tokyo 1TB](https://bwh81.net/aff.php?aff=77528&pid=125) |

### Osaka CN2 GIA (Premium Tier — Japan, 1.5 Gbps)

Same premium China routing as Tokyo, slightly higher bandwidth (1.5 Gigabit vs 1.2 Gigabit), and notably cheaper at the entry tier — $49.99/month vs $89.99/month for the 40G plan. If you want Japan-based CN2 GIA and don't specifically need Tokyo, Osaka is the better value.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Osaka 40G | 2 GB | 2 vCPU | 40 GB RAID-10 SSD | 500 GB/mo | 1.5 Gigabit | $49.99/month | [Order Osaka 40G](https://bwh81.net/aff.php?aff=77528&pid=134) |
| Osaka 80G | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 1 TB/mo | 1.5 Gigabit | $86.99/month | [Order Osaka 80G](https://bwh81.net/aff.php?aff=77528&pid=135) |
| Osaka 160G | 8 GB | 6 vCPU | 160 GB RAID-10 SSD | 2 TB/mo | 1.5 Gigabit | $165.99/month | [Order Osaka 160G](https://bwh81.net/aff.php?aff=77528&pid=136) |
| Osaka 320G | 16 GB | 8 vCPU | 320 GB RAID-10 SSD | 4 TB/mo | 1.5 Gigabit | $329.99/month | [Order Osaka 320G](https://bwh81.net/aff.php?aff=77528&pid=137) |
| Osaka 640G | 32 GB | 10 vCPU | 640 GB RAID-10 SSD | 6 TB/mo | 1.5 Gigabit | $549.99/month | [Order Osaka 640G](https://bwh81.net/aff.php?aff=77528&pid=138) |
| Osaka 1TB | 64 GB | 12 vCPU | 1 TB RAID-10 SSD | 8 TB/mo | 1.5 Gigabit | $1,059.99/month | [Order Osaka 1TB](https://bwh81.net/aff.php?aff=77528&pid=139) |

### Singapore CN2 GIA (Premium Tier — SG8, 1.5 Gbps)

Singapore-based CN2 GIA. Same 1.5 Gigabit bandwidth as Osaka. The entry plan at $49.99/month is roughly half the price of the Hong Kong equivalent at $89.99/month, which makes it a strong value if you want Southeast Asia presence with premium China routing.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Singapore 40G | 2 GB | 2 vCPU | 40 GB RAID-10 SSD | 500 GB/mo | 1.5 Gigabit | $49.99/month | [Order Singapore 40G](https://bwh81.net/aff.php?aff=77528&pid=173) |
| Singapore 80G | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 1 TB/mo | 1.5 Gigabit | $86.99/month | [Order Singapore 80G](https://bwh81.net/aff.php?aff=77528&pid=174) |
| Singapore 160G | 8 GB | 6 vCPU | 160 GB RAID-10 SSD | 2 TB/mo | 2.5 Gigabit | $165.99/month | [Order Singapore 160G](https://bwh81.net/aff.php?aff=77528&pid=175) |
| Singapore 320G | 16 GB | 8 vCPU | 320 GB RAID-10 SSD | 4 TB/mo | 2.5 Gigabit | $329.99/month | [Order Singapore 320G](https://bwh81.net/aff.php?aff=77528&pid=176) |
| Singapore 640G | 32 GB | 10 vCPU | 640 GB RAID-10 SSD | 6 TB/mo | 5 Gigabit | $549.99/month | [Order Singapore 640G](https://bwh81.net/aff.php?aff=77528&pid=177) |
| Singapore 1TB | 64 GB | 12 vCPU | 1 TB RAID-10 SSD | 8 TB/mo | 5 Gigabit | $1,059.99/month | [Order Singapore 1TB](https://bwh81.net/aff.php?aff=77528&pid=178) |

### Dubai E-Commerce (Middle East Tier — Local Peering)

Dubai-based plans with direct local peering with DU and Etisalat networks. These are E-Commerce tier plans (same structure as the CN2 GIA-E plans above) but with Dubai as the home location. They can also migrate to the CN2 GIA-E, CN2 GIA, and standard KVM datacenters if needed. Useful if your audience is in the Middle East or you need a Gulf-region presence.

| Plan | RAM | CPU | Storage | Transfer | Link Speed | Price (shortest cycle) | Purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Dubai 20G | 1 GB | 2 vCPU | 20 GB RAID-10 SSD | 1 TB/mo | 2.5 Gigabit | $49.99/quarter | [Order Dubai 20G](https://bwh81.net/aff.php?aff=77528&pid=114) |
| Dubai 40G | 2 GB | 3 vCPU | 40 GB RAID-10 SSD | 2 TB/mo | 2.5 Gigabit | $89.99/quarter | [Order Dubai 40G](https://bwh81.net/aff.php?aff=77528&pid=115) |
| Dubai 80G | 4 GB | 4 vCPU | 80 GB RAID-10 SSD | 3 TB/mo | 2.5 Gigabit | $56.99/month | [Order Dubai 80G](https://bwh81.net/aff.php?aff=77528&pid=116) |
| Dubai 160G | 8 GB | 6 vCPU | 160 GB RAID-10 SSD | 5 TB/mo | 5 Gigabit | $86.99/month | [Order Dubai 160G](https://bwh81.net/aff.php?aff=77528&pid=117) |
| Dubai 320G | 16 GB | 8 vCPU | 320 GB RAID-10 SSD | 8 TB/mo | 5 Gigabit | $159.99/month | [Order Dubai 320G](https://bwh81.net/aff.php?aff=77528&pid=118) |
| Dubai 640G | 32 GB | 10 vCPU | 640 GB RAID-10 SSD | 10 TB/mo | 10 Gigabit | $289.99/month | [Order Dubai 640G](https://bwh81.net/aff.php?aff=77528&pid=119) |
| Dubai 1TB | 64 GB | 12 vCPU | 1 TB RAID-10 SSD | 12 TB/mo | 10 Gigabit | $549.99/month | [Order Dubai 1TB](https://bwh81.net/aff.php?aff=77528&pid=120) |

## How to Actually Choose a Linux VPS Plan

Now that you've seen the full range, here's how to match it to what you're doing.

**If you're learning Linux or running a personal project:** Start with the 20G KVM at $49.99/year. You get root access, full SSH, the ability to install whatever you want, and a real Linux environment to break and fix. If you outgrow it, KiwiVM lets you upgrade by paying the price difference — you don't lose your setup or any discounts attached to your subscription.

**If you're running a small production site with non-China users:** The 80G KVM at $19.99/month (4 GB RAM, 4 vCPU, 80 GB SSD, 3 TB transfer) is a reasonable starting point. You can run a real web stack on this — Nginx, a database, a small app — without immediately hitting resource limits.

**If your users are in mainland China but latency isn't revenue-critical:** The CN2 GIA-E 20G at $49.99/quarter ($169.99/year annual) is the plan most people in this situation end up on. You get premium triple-network routing at a price that's still in the "reasonable for an individual" range.

**If you're running cross-border VOIP, video conferencing, gaming, or anything where 5ms vs 30ms matters:** Hong Kong CN2 GIA. The 40G entry plan at $89.99/month is the floor. If that price makes you uncomfortable, you probably don't actually need this tier — the CN2 GIA-E plans in Los Angeles will give you most of the benefit.

**If you want Japan presence with premium China routing:** Osaka over Tokyo. Same routing quality, higher bandwidth (1.5 Gbps vs 1.2 Gbps), and the entry plan is $40/month cheaper.

**If you want Southeast Asia presence with premium China routing:** Singapore CN2 GIA. The $49.99/month entry plan is roughly half the Hong Kong equivalent.

**If your audience is in the Middle East:** Dubai E-Commerce. Local peering with DU and Etisalat, plus the ability to migrate to CN2 GIA-E locations if needed.

## On Promo Codes and Saving Money

As of the most recent checks, there's no verified active BandwagonHost promo code. The NODESEEK2026 code (6.77% recurring) was live briefly in February 2026 but has since expired. Older codes like BWHCGLUKKB were retired in late 2025. BandwagonHost tends to release new codes around major events — Double 11 (November), Black Friday, New Year — so it's worth checking before you buy, but don't let the absence of a code stop you if you need a server now.

The reliable savings levers that don't depend on promo codes:

- **Go annual over quarterly on plans that offer both.** On the CN2 GIA-E 20G, quarterly billing works out to roughly $200/year; annual is $169.99. That $30 is automatic savings.
- **Match the tier to your actual use case.** A personal dev server does not need Hong Kong CN2 GIA at $89.99/month. A China-facing production service probably shouldn't be on the $49.99/year standard KVM.
- **Watch for limited-edition plan restocks.** BandwagonHost periodically releases limited-edition plans (THE PLAN, MINICHICKEN, Box series) at prices that can be one-third to one-fifth of equivalent regular plans. These sell out fast and require monitoring, but long-time users swear by them.
- **Use in-panel upgrades.** If you outgrow a plan, KiwiVM lets you upgrade to a higher tier by paying only the price difference, without re-provisioning. This preserves your setup and any discounts attached to your existing subscription.

## What BandwagonHost Is Not

It's worth being clear about the trade-offs. BandwagonHost is self-managed. They handle hardware, network, and infrastructure. You handle everything above the OS level — security hardening, firewall configuration, software updates, backups (though KiwiVM does offer snapshots), and troubleshooting when something breaks at 3 AM.

If you need cPanel, managed WordPress hosting, or someone to call about your Apache configuration, this isn't the right product. If you're comfortable on a Linux command line, or willing to get comfortable, the pricing reflects that you're not paying for hand-holding.

The 30-day refund policy gives you a window to test whether the service actually works for your use case. If you're uncertain, buy a smaller plan first, run real workloads through it, and upgrade only if you need to.

## Final Notes on Getting Started

Once you pick a plan, the workflow is: order → instant activation → log into KiwiVM → pick your OS (Ubuntu, Debian, AlmaLinux, RockyLinux, CentOS, CentOS Stream, Fedora, or a custom ISO) → SSH in as root → start configuring. The whole thing from payment to a usable SSH prompt is typically under a few minutes.

If you want to look at the current plan availability and pricing directly, you can 👉 [browse all BandwagonHost VPS plans here](https://bit.ly/BandWaGon). Stock varies by datacenter and plan tier — the limited-edition plans in particular sell out quickly — so if you're eyeing a specific tier, checking current availability before deciding is worth the 30 seconds.

The short version of all this: figure out where your users are, figure out what you're running, and pick the cheapest tier that handles both. The most expensive plan is only worth it if the network or latency it buys you is something your workload actually needs.
