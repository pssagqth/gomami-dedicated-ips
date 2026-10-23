# vps with dedicated ip: What GoMami Includes by Default, What Extra Addresses Cost, and Which Plan Fits

A VPS with a dedicated IP means one public IPv4 assigned to your instance alone, with no NAT layer in front of it and no port range split between tenants. GoMami assigns exactly one dedicated IPv4 to every instance and documents where to find it: the control panel's Network tab, which lists the interface name, network type (Public), MAC address, inbound and outbound bandwidth, the IPv4 address, gateway, subnet mask and resolvers.

That's where the documentation ends. Nothing in it mentions an IPv6 allocation. Additional addresses are priced on a single product line. Swapping an address costs $5 and permanently releases the old one. If you're shopping on the phrase "dedicated IP" alone, those three details matter more than the phrase does.

**Quick version:** the cheapest way onto GoMami's network with a dedicated IPv4 is a Nano plan at $29/month in Tokyo, Singapore or Los Angeles. If mainland China latency is the actual reason you're reading this, pay the Hong Kong premium instead. 👉 [Check the $29 JPN.Pulse.Nano specs and order page](https://gomami.io/store/jpn-pulse?aff=415)

## What a dedicated IP on GoMami actually gives you

You get one public IPv4 per instance, viewable in the panel, and you can point the instance at your own primary and secondary DNS resolvers from that same screen. There's no published IPv6 range to configure, so plan for IPv4-only networking.

Reverse DNS is settable, with a wrinkle. The docs describe clicking the RDNS column in the IPv4 address table to set PTR records, and separately tell you to make sure the matching forward record exists at your DNS provider first. The same page then says mail-server reverse DNS should go through a support ticket. Both paths exist; if email is involved, open the ticket rather than assume the panel is sufficient.

Provisioning is automatic. Deployment normally completes within a few minutes of payment, and the welcome email carries the IP address and login credentials. There's also a documented RESTful API for managing your account and servers programmatically, which is useful if you're spinning instances up from your own tooling.

## Extra IPs, IP swaps, and blocked addresses

Only one product line publishes a price for additional addresses. HKG.Forge lists extra IPs at $10 each, capped at four per server. For Turin, Pulse and the rest, the network FAQ simply says to contact support via ticket, with no price published anywhere. If your design needs three addresses on a $29 Nano, get a quote before you pay, not after.

GoMami's Forge line is the one place where multiple addresses come with a stated price. 👉 [See the HKG.Forge plan page and additional-IP terms](https://gomami.io/store/hkg-forge?aff=415)

Self-service IP changes are $5 per swap. You select the instance from a dropdown, submit, and the system charges the fee and assigns a new address immediately. The old IP is released and cannot be recovered. A $5 swap is cheap until you remember that an address you've spent months warming for email deliverability or allowlisting with a payment processor doesn't come back.

If an IP becomes unreachable from mainland China, the documented order is: confirm whether it's globally unreachable (which points at your server rather than the network), run `ping` and `traceroute` to inspect the path, then open a ticket so support can verify the address's status. Confirmed blocks get help with a change. The docs also note that IP blocking usually relates to what's running on the machine.

| Situation | Cost | What happens |
| --- | --- | --- |
| Extra IP on HKG.Forge | $10/month each, max 4 | Listed on the Forge plan page |
| Extra IP on Turin or Pulse | Not published | Ticket to support for a quote |
| Self-service IP change | $5 per change | Immediate; old IP released permanently |
| Reverse DNS | No charge | Panel RDNS column, or ticket for mail use |
| IPv6 | Not offered in docs | Plan for IPv4 only |

## All GoMami plans

One fact from the section above is worth carrying into these tables: only HKG.Forge publishes a price for additional IPs. If you need several addresses on one box, that single detail may pick the product line for you and the six tables below become secondary.

The specs here come from GoMami's own store pages, which list full configurations without prices. The monthly figures are from third-party plan trackers recorded in mid-2026, so confirm your number in the cart before paying.

### HKG.Turin (Hong Kong, performance tier)

| Plan | vCPU / RAM | NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- |
| Mini | 2 / 4GB | 100GB | 1TB / 2Gbps | $69 | [ Order Turin.Mini](https://gomami.io/store/hkg-turin?aff=415) |
| Air | 4 / 8GB | 140GB | 2TB / 2Gbps | $129 | [ Order Turin.Air](https://gomami.io/store/hkg-turin?aff=415) |
| Pro | 6 / 16GB | 180GB | 5TB / 5Gbps | $299 | [ Order Turin.Pro](https://gomami.io/store/hkg-turin?aff=415) |
| Ultra | 12 / 32GB | 220GB | 10TB / 5Gbps | $599 | [ Order Turin.Ultra](https://gomami.io/store/hkg-turin?aff=415) |

Pro and Ultra are flagged Windows-ready. The store page doesn't say whether a licence is included, so assume you supply your own unless support tells you otherwise.

### HKG.Pulse (Hong Kong, balanced tier)

| Plan | vCPU / RAM | NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- |
| Nano | 2 / 2GB | 40GB | 500GB / 1Gbps | $49 | [ Order HKG.Pulse.Nano](https://gomami.io/store/hkg-pulse?aff=415) |
| Mini | 2 / 4GB | 60GB | 1TB / 1Gbps | $59 | [ Order HKG.Pulse.Mini](https://gomami.io/store/hkg-pulse?aff=415) |
| Air | 4 / 8GB | 80GB | 2TB / 1Gbps | $119 | [ Order HKG.Pulse.Air](https://gomami.io/store/hkg-pulse?aff=415) |
| Pro | 8 / 16GB | 100GB | 5TB / 3Gbps | $269 | [ Order HKG.Pulse.Pro](https://gomami.io/store/hkg-pulse?aff=415) |
| Ultra | 12 / 32GB | 300GB | 10TB / 3Gbps | $499 | [ Order HKG.Pulse.Ultra](https://gomami.io/store/hkg-pulse?aff=415) |

On the Mini tier specifically, the reported price is inconsistent. An August 2025 review and a May 2026 article both worked from $39, and GoMami's homepage still shows a $39 EPYC Mini in a block that doesn't map cleanly onto any single regional plan. A June 2026 third-party plan table lists $59, which is what the table above uses. Treat the cart total as the real number.

### JPN.Pulse (Tokyo)

| Plan | vCPU / RAM | NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- |
| Nano | 2 / 2GB | 40GB | 500GB / 1Gbps | $29 | [ Order JPN.Pulse.Nano](https://gomami.io/store/jpn-pulse?aff=415) |
| Mini | 2 / 4GB | 60GB | 1TB / 1.5Gbps | $49 | [ Order JPN.Pulse.Mini](https://gomami.io/store/jpn-pulse?aff=415) |
| Air | 4 / 8GB | 80GB | 2TB / 1Gbps | $89 | [ Order JPN.Pulse.Air](https://gomami.io/store/jpn-pulse?aff=415) |
| Pro | 8 / 16GB | 100GB | 5TB / 3Gbps | $169 | [ Order JPN.Pulse.Pro](https://gomami.io/store/jpn-pulse?aff=415) |
| Ultra | 12 / 32GB | 300GB | 10TB / 3Gbps | $338 | [ Order JPN.Pulse.Ultra](https://gomami.io/store/jpn-pulse?aff=415) |

### SIN.Pulse (Singapore)

| Plan | vCPU / RAM | NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- |
| Nano | 2 / 2GB | 40GB | 500GB / 1Gbps | $29 | [ Order SIN.Pulse.Nano](https://gomami.io/store/sin-pulse?aff=415) |
| Mini | 2 / 4GB | 60GB | 1TB / 1Gbps | $49 | [ Order SIN.Pulse.Mini](https://gomami.io/store/sin-pulse?aff=415) |
| Air | 4 / 8GB | 80GB | 2TB / 1Gbps | $89 | [ Order SIN.Pulse.Air](https://gomami.io/store/sin-pulse?aff=415) |
| Pro | 8 / 16GB | 100GB | 5TB / 3Gbps | $169 | [ Order SIN.Pulse.Pro](https://gomami.io/store/sin-pulse?aff=415) |
| Ultra | 12 / 32GB | 300GB | 10TB / 3Gbps | $338 | [ Order SIN.Pulse.Ultra](https://gomami.io/store/sin-pulse?aff=415) |

### LAX.Pulse (Los Angeles)

| Plan | vCPU / RAM | NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- |
| Nano | 2 / 2GB | 40GB | 1TB / 1Gbps | $29 | [ Order LAX.Pulse.Nano](https://gomami.io/store/lax-pulse?aff=415) |
| Mini | 2 / 4GB | 60GB | 2TB / 1Gbps | $59 | [ Order LAX.Pulse.Mini](https://gomami.io/store/lax-pulse?aff=415) |
| Air | 4 / 8GB | 80GB | 4TB / 2Gbps | $129 | [ Order LAX.Pulse.Air](https://gomami.io/store/lax-pulse?aff=415) |
| Pro | 6 / 16GB | 100GB | 8TB / 3Gbps | $259 | [ Order LAX.Pulse.Pro](https://gomami.io/store/lax-pulse?aff=415) |
| Ultra | 12 / 32GB | 300GB | 15TB / 5Gbps | $599 | [ Order LAX.Pulse.Ultra](https://gomami.io/store/lax-pulse?aff=415) |
| Titan | 12 / 32GB | 600GB | 30TB / 10Gbps | $999 | [ Order LAX.Pulse.Titan](https://gomami.io/store/lax-pulse?aff=415) |

### HKG.Forge (dedicated-class hardware)

| Plan | CPU / RAM | NVMe | Traffic / Port | Price/mo | Order |
| --- | --- | --- | --- | --- | --- |
| Mini | EPYC 7663, 56C/112T, 128GB | 960GB | 10TB / 2Gbps | $599 | [ Order Forge.Mini](https://gomami.io/store/hkg-forge?aff=415) |
| Air | EPYC 7663, 56C/112T, 256GB | 4TB | 20TB / 2Gbps | $899 | [ Order Forge.Air](https://gomami.io/store/hkg-forge?aff=415) |

Forge runs on TYAN B8033 hardware with dual EPYC 7663 processors, activates immediately after payment, and allows OS reinstalls from the panel at any time. It's also the only line with a published overage rate: $0.06/GB past your included traffic.

## Choosing between them

Geography decides this purchase; the spec ladder is generous on every line. A 2 vCPU/4GB instance runs a WordPress site, an API backend or a jump host without complaint. What you can't upgrade your way out of later is where the box sits.

GoMami's own latency table puts Hong Kong under 30ms to mainland China, Japan under 50ms and Singapore under 70ms. The site-wide "<50ms" headline is broader marketing copy, and the docs say outright that real latency depends on your ISP and that you should test before buying.

- Mostly mainland China users, latency is the product → Hong Kong. Pulse.Mini at $59 for balance, Turin.Mini at $69 if single-core speed is your bottleneck.
- Cheap dedicated IPv4 with China-friendly routing and 60ms is tolerable → JPN.Pulse.Nano or SIN.Pulse.Nano at $29. Tokyo wins if China is the target; Singapore wins if Southeast Asia matters too.
- Traffic volume rather than latency → LAX.Pulse, where Nano ships 1TB and Titan 30TB with ports up to 10Gbps. There's no published Los Angeles-to-China latency figure, so don't buy it expecting Hong Kong behaviour.
- Dozens of cores and a large memory footprint on one instance → Forge, and only Forge.
- Windows needed → pick Pro or Ultra, the tiers flagged Windows-ready.

Worth stating plainly: if all you want is a dedicated IPv4 on a $3 box, GoMami is the wrong shop. Entry is $29/month and the value is the route.

## What the monthly price doesn't cover

Traffic is billed outbound only. Inbound traffic is free, which is a genuine advantage for a web server or media relay and is stated both in the network FAQ and on the Forge plan page.

Exceed your allowance and you don't have to change plans. Traffic packs are self-service, applied to the current cycle immediately: 100GB $6, 500GB $30, 1TB $60, 2TB $120, 5TB $300, 10TB $600, 20TB $1,200. They expire at the end of the billing cycle and don't roll over.

Do the upgrade math before you buy packs. On JPN.Pulse or SIN.Pulse, going from Nano to Mini costs $20/month and adds 2GB of RAM plus 500GB of traffic. A 500GB pack alone costs $30. One month of packs buys more than the upgrade and leaves you with less RAM. A single 1TB pack at $60 covers a Nano's entire remaining headroom and still costs three times the tier jump.

DDoS protection is where the marketing and the documentation diverge. The homepage advertises up to 600Gbps mitigation capacity, which reads like a standard inclusion. The network FAQ is more precise: every instance gets best-effort protection with automatic detection and scrubbing, and 600Gbps advanced scrubbing is a paid add-on. Under attack conditions that affect other customers, your IP gets blackholed for 30 to 60 minutes and released automatically, with no manual override.

## Billing terms that affect your IP

Your dedicated address lives as long as the instance does, so renewal terms are effectively IP-retention terms.

Service suspends on the due date with no grace period. At 5 days overdue it's terminated and data may not be recoverable; at 6 days the invoice auto-cancels. Reminders go out at 2 and 3 days overdue, so the gap between "I forgot" and "it's gone" is short.

Annual billing typically saves 15% to 20% against monthly, varying by product line. GoMami doesn't publish per-plan annual prices, so the discount has to be read off the checkout page rather than calculated in advance.

Refunds run on a 24-hour window for new purchases: full amount, back to the original payment method, limited to one per user, renewals excluded. Alipay refunds land in 1–3 business days, card refunds in 5–10. That window is short next to hosts offering 30 days, but it's long enough for the one test that decides everything here. Provision the instance, then benchmark latency from your users' actual locations during the 20:00–23:00 China peak, before the window closes. 👉 [Start with a monthly Hong Kong Pulse plan and test the route](https://gomami.io/store/hkg-pulse?aff=415)

Payment methods are card via Stripe, Alipay via Stripe, and cryptocurrency. Discount codes circulate on third-party blogs from time to time; none of them appear on GoMami's own site or documentation, and whether they still work, whether they're restricted to new customers, or whether they stack with annual pricing is unknown. Don't build a budget around them.

## How this compares to cheap dedicated-IP hosts

If a dedicated IP is your only requirement, there are far cheaper places to get one, and the trade-off is worth understanding before you pay GoMami's premium.

Cloudzy's own product pages state that every VPS ships with a dedicated static IPv4 plus a routable IPv6 /64, across 13 regions, with entry pricing at $2.48/month, floating IPs at $2.50/month each, and a 14-day money-back window. That's roughly a tenfold difference at the entry level, with IPv6 included as standard and a longer refund period.

The difference is what surrounds the address. Cloudzy's pitch is geography and IP hygiene; it doesn't market a CN2 / AS9929 / CMIN2 triple-route stack aimed at mainland China. GoMami's premium buys the path your packets take, plus a published additional-IP option on its Forge line, which is not something the budget hosts are set up around.

The reverse also holds and deserves saying: if your audience is in Frankfurt or Virginia, paying for China-optimised routing is money spent on nothing. Take a cheap box with a dedicated IPv4 and put the savings into RAM. Those hosts' figures are their own published claims, so verify current pricing on their sites rather than on a listicle.

## FAQ

**Does every GoMami plan include a dedicated IP?**
Yes. Each instance is assigned a dedicated IPv4, shown in the panel's Network tab with gateway, netmask and resolvers.

**Can I get more than one IP?**
On HKG.Forge, $10 per additional IP up to four per server. On other lines, additional IPs require a support ticket and no price is published.

**Is IPv6 supported?**
Nothing in the published documentation mentions IPv6. The documented allocation is one dedicated IPv4 per instance.

**What if my IP gets blocked in China?**
Check global reachability first, run ping and traceroute, then open a ticket for support to verify the address status. Confirmed blocks get help with a change; self-service changes cost $5 and release the old IP for good.

**Can I run a mail server?**
The docs cover reverse DNS specifically for mail servers and route that case to support. Set the forward record first, then use the RDNS column or open a ticket.

**Is there a trial?**
No trial is documented. The 24-hour refund on first purchases functions as a short testing window.

## Before you pay

Two numbers are worth reading off the cart rather than trusting from any article, including this one: the actual monthly price for your chosen plan, since GoMami's store pages list specifications without prices and the figures above come from third-party trackers, and where annual billing lands inside that 15–20% range. If you're looking at HKG.Pulse.Mini, the reported price has varied between sources, so that checkout total deserves a second look in particular.

Then run the test. Provision the instance immediately after payment, take baseline latency from your real users' locations, and repeat it during the 20:00–23:00 China peak while the 24-hour refund window is still open. Routing quality during evening congestion is the thing you're actually buying, and it's the one thing no spec sheet can tell you.

👉 [Compare all GoMami plans and check current checkout pricing](https://bit.ly/Gomami)
