# Vultr vs UpCloud: Cheaper Entry Price or Cheaper at Equal RAM? Plan Prices, Egress Costs and Benchmark Grades Compared (Plan Table + Cost Math)

Vultr is the cheaper way in. Cloud Compute starts at **$2.50/month**, the network covers roughly 30+ locations, and every instance carries a monthly transfer allowance. UpCloud starts at **$3.50** and is the cheaper way up: at 1, 2, 4 and 8 GB of RAM its Starter plans cost $3.50, $7, $14 and $24 against Vultr's $5, $10, $20 and $40. Both numbers are correct, which is why most comparisons of these two never reach a conclusion.

Which one costs you less depends on whether your bill is dominated by compute, by outbound traffic, or by the add-ons around the VM. What follows is the plan-by-plan pricing, the three invoice lines most comparisons skip, and what the October 2026 benchmark grades mean for a real workload.

> **The 30-second version**
> - **Lowest monthly entry:** Vultr, $2.50/mo for the smallest Cloud Compute tier, then $5.00 for 1 GB with 1 TB of transfer included.
> - **Lowest at matched RAM:** UpCloud, at all four sizes where the two lineups overlap.
> - **Bandwidth-heavy:** UpCloud's egress is free inside its fair-use policy; Vultr includes 0.5 to 15 TB per instance depending on plan, then bills $10/TB.
> - **Storage-heavy:** Vultr, where block storage is about 60% cheaper at the reference configuration.
> - **Footprint and GPU choice:** Vultr, with roughly 30+ locations against about 15 and 9 GPU models against 6.
>
> 👉 [See Vultr's current Cloud Compute prices and full plan list](https://www.vultr.com/pricing/?ref=9738262-9J)

## Vultr's plan families and what each one costs

Vultr sells three lines. Cloud Compute is the shared-CPU VPS range and starts at $2.50/month. Optimized Cloud Compute, which covers dedicated-CPU general purpose, CPU-optimized, memory-optimized and storage-optimized shapes, starts at $28.00/month. Bare Metal starts at $120.00/month.

The table covers one representative tier from each family plus every Regular Performance size that has a direct UpCloud counterpart. The full Cloud Compute catalog runs to more than a hundred configurations, so treat this as a working selection by family and confirm the exact tier on the pricing page before you deploy.

| Plan | Configuration | Transfer | USD/mo | Provision |
| --- | --- | --- | --- | --- |
| Cloud Compute, entry tier | 0.5 GB RAM | plan allowance | **$2.50** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Regular Performance vc2-1c-1gb | 1 vCPU / 1 GB / 25 GB SSD | 1 TB | **$5.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Regular Performance vc2-1c-2gb | 1 vCPU / 2 GB / 55 GB SSD | 2 TB | **$10.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Regular Performance vc2-2c-4gb | 2 vCPU / 4 GB / 80 GB SSD | 3 TB | **$20.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Regular Performance vc2-4c-8gb | 4 vCPU / 8 GB / 160 GB SSD | 4 TB | **$40.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| High Performance 2 GB | 2 GB RAM | plan allowance | **$12.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| High Performance 4 GB | 4 GB RAM | plan allowance | **$24.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| High Performance 8 GB | 8 GB RAM | plan allowance | **$48.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| High Frequency 2 GB | 2 GB RAM | plan allowance | **$12.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| CPU Optimized 1-2-25 | 1 vCPU / 2 GB / 25 GB | plan allowance | **$28.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| General Purpose voc-g-1c-4gb-30s | 1 vCPU / 4 GB / 30 GB | plan allowance | **$30.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| CPU Optimized 2-4-50 | 2 vCPU / 4 GB / 50 GB | plan allowance | **$40.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| VX1 GP 2C 8G 50S | 2 vCPU / 8 GB / 50 GB | plan allowance | **$48.80** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| VX1 GP 2C 8G 120S | 2 vCPU / 8 GB / 120 GB | plan allowance | **$55.48** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| VX1 GP 4C 16G 240S | 4 vCPU / 16 GB / 240 GB | plan allowance | **$110.16** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |
| Bare Metal | dedicated server | plan allowance | **from $120.00** | [View price](https://www.vultr.com/pricing/?ref=9738262-9J) |

Prices are monthly list in USD. Hourly billing is available on every tier, and a full month on Cloud Compute is capped at 672 billed hours, so running an instance around the clock costs the monthly rate and no more.

## Same RAM, side by side: UpCloud wins four for four

Compare plans that match on RAM rather than on price point and UpCloud is cheaper at every size the two lineups share.

| RAM | Vultr (Regular Performance) | UpCloud (Starter) |
| --- | --- | --- |
| 1 GB | vc2-1c-1gb, **$5.00**, 25 GB SSD, 1 TB transfer | 1xCPU-1GB, **$3.50**, 10 GB SSD |
| 2 GB | vc2-1c-2gb, **$10.00**, 55 GB SSD, 2 TB | 1xCPU-2GB, **$7.00**, 20 GB SSD |
| 4 GB | vc2-2c-4gb, **$20.00**, 80 GB SSD, 3 TB | 2xCPU-4GB, **$14.00**, 30 GB SSD |
| 8 GB | vc2-4c-8gb, **$40.00**, 160 GB SSD, 4 TB | 4xCPU-8GB, **$24.00**, 40 GB SSD |
| 16 GB | no tier at this size | Premium 8xCPU-16GB, **$164.00**, 200 GB SSD |

The savings run from 30% at 1 and 2 GB to 40% at 4 and 8 GB. Vultr's counter is disk and transfer: its 1 GB plan carries 2.5 times the SSD of UpCloud's, and the gap widens to 4x at 8 GB, with 1 to 4 TB of traffic bundled in. If your workload fits inside UpCloud's smaller volumes, the per-month gap is real money. If you would otherwise attach extra storage or pay for overage, it shrinks or disappears.

The 16 GB row shows where the lineups stop overlapping. UpCloud's only 16 GB entry is the $164.00 Premium plan. Vultr's closest 16 GB option sits in the VX1 family at $110.16, which makes the more expensive brand at small sizes the cheaper one at this size.

## The three invoice lines that decide the real bill

Compute is the visible number. These are the ones that move it.

**Egress.** Vultr bills outbound traffic at **$10/TB ($0.01/GB)** once an instance exceeds its included allowance, which ranges from 0.5 to 15 TB per month depending on plan size. Inbound traffic is free. UpCloud charges nothing for egress inside its fair-use policy and publishes no per-TB rate.

Put numbers on it. A 4 GB instance pushing 8 TB outbound in a month:

- Vultr vc2-2c-4gb: $20.00 base, 3 TB included, 5 TB overage at $10 = **$70.00**
- UpCloud 2xCPU-4GB: $14.00 base, egress within fair use = **$14.00**

At that volume the two are not in the same price bracket, and no amount of plan-level comparison will show it. The catch is that "fair use" is not defined in public pricing, so if you sustain tens of terabytes, get the limit in writing before you migrate.

**Block storage.** At the reference configuration these comparison sites use, UpCloud's block storage lists at $25.00/month against Vultr's $10.00, a 60% difference in Vultr's favour. Volumes are billed separately from the SSD in the plan, so a media library, a backup target or a database with a large working set changes the total.

**Load balancing and managed services.** UpCloud includes a load balancer at no charge where Vultr lists $10.00/month. Other services split both ways:

| Service (closest match, USD/mo) | Vultr | UpCloud |
| --- | --- | --- |
| Small VM | $5.00 | **$3.50** |
| Medium VM | $40.00 | **$24.00** |
| Large VM | $160.00 | **$92.00** |
| Block storage | **$10.00** | $25.00 |
| Object storage | **$18.00** | $20.00 |
| PostgreSQL | **$60.00** | $69.00 |
| Redis | $15.00 | **$8.00** |
| Load balancer | $10.00 | **Free** |
| Egress | $10.00/TB after allowance | **Free within fair use** |

These figures take each provider's closest plan to a common setup and vary by region and usage, so re-check them against your own configuration. The pattern holds: a bandwidth-heavy site lands on UpCloud, a storage-heavy one lands on Vultr, and a three-tier app with two load balancers and a Redis cache leans UpCloud before you price a single VM.

👉 [Price out a Vultr instance against your own storage and transfer volume](https://www.vultr.com/pricing/?ref=9738262-9J)

## What the benchmark grades actually say

vpsbenchmarks tested 18 plans across the two providers and published grades in October 2026, scoring web performance, raw CPU, stability, disk I/O and network on an A to F scale. A few rows are worth reading closely.

| Plan | Listed price | Web | CPU | Stability | Disk | Network |
| --- | --- | --- | --- | --- | --- | --- |
| Vultr VX1 GP 2C 8G 120S | $55.48 | B | D | A | A | C |
| Vultr VX1 GP 4C 16G 240S | $110.16 | B | C | B | B | B |
| Vultr Regular 2GB 1 core | $10.00 | E | F | C | C | D |
| UpCloud Native 4GB 2 cores | €18.40 | B | D | A | E | C |
| UpCloud Native 16GB 8 cores | €93.60 | B | A | D | E | C |
| UpCloud Premium 1 core 2GB | €12.00 | C | E | D | D | D |

Prices here are as listed by the tester, USD for Vultr and EUR for UpCloud. Don't convert them into a single ranking; the grades are what matter.

Three conclusions follow from the grades.

**A higher price does not buy a better all-round machine.** UpCloud's €93.60 Native 16GB plan earns the only A for raw CPU in this set and simultaneously a D for stability and an E for disk I/O. Paying 5x the price of its 4 GB plan bought cores, not I/O. Anyone assuming the expensive tier is uniformly stronger should look at the disk column first.

**The one plan with top grades on both stability and disk is a Vultr VX1.** The VX1 GP 2C 8G 120S at $55.48 scored A on stability and A on disk I/O, which is the combination that matters for databases and anything that writes to disk on every request. The VX1 GP 4C 16G 240S is the most balanced machine in the list, with nothing below a C and B across web, stability, disk and network.

**Cheap tiers are weak on both sides.** Vultr's Regular 2GB 1 core scores F on raw CPU and E on web performance. UpCloud's Premium 1 core 2GB scores C, E, D, D and D. Neither is a sensible home for a latency-sensitive application; the $10 to $12 tier is for a static site, a jump box or a cron runner.

UpCloud's own comparison page still cites a 2015 Cloud-Spectator study for claims of up to 2x the I/O of Vultr. That is a vendor claim built on decade-old data, and the 2026 grades above hand disk I/O wins to specific Vultr plans, so weight the independent test over the marketing page.

Match the family to your bottleneck rather than to the brand: CPU-bound batch work points at the VX1 GP 4C 16G 240S or UpCloud's Native 16GB; write-heavy workloads point at the VX1 GP 2C 8G 120S.

👉 [Browse the VX1 and High Performance tiers](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J)

## Locations, SLA and where your data sits

Vultr publishes roughly 30+ locations across six continents; counts taken in October and November 2026 ranged from 31 to 33 depending on when the page was tallied. UpCloud publishes about 15, with counts between 14 and 15. Both have servers in Amsterdam, Chicago, Frankfurt, London, Madrid, New York, San Jose, Singapore, Stockholm, Sydney and Warsaw, which covers most of what a European or North American audience needs.

The differences that decide enterprise purchases sit elsewhere. UpCloud is headquartered in Finland and offers a **100% SLA with 50x compensation** for outages, which is easier to put in front of a procurement team and easier to defend under GDPR. Vultr is US-headquartered and competes on breadth: more regions, more payment methods (cards, PayPal, crypto, Alipay and wire, against cards and PayPal at UpCloud), and a wider GPU menu.

On GPUs, Vultr lists 9 models to UpCloud's 6. The H100 rents for $2.06/GPU-hour on UpCloud against $2.30 on Vultr, and the B200 for $4.23 against $3.20. Vultr is the only one of the two with the A100 ($1.49), MI300X ($1.85), MI325X ($2.00) and MI355X ($2.59). UpCloud is the only one with the B300 ($5.99), RTX PRO 6000 ($0.99) and L4 ($0.68). Both bill on-demand and spot.

DDoS protection is where published comparisons disagree. One scorecard credits Vultr with DDoS filtering included at entry level and marks UpCloud as not included, while the benchmark site's feature table lists protection as available from both. The likely difference is bundling at the cheapest tier rather than capability, so don't read the scorecard as evidence that UpCloud offers no filtering.

## What users actually complain about

On G2, UpCloud scores **9.3/10 for quality of support** across 78 responses against Vultr's **8.1/10** across 206. The rest of the gap is narrower: 8.9 vs 8.8 on meeting requirements, 9.3 vs 9.1 on ease of use, 9.4 vs 9.1 on ease of setup, and 9.1 vs 8.1 on product direction.

Text mining of the same reviews points the same way. UpCloud's most-cited positives are customer support (21 mentions) and ease of use (19); its most-cited complaint is price (9 mentions). Vultr's positives are ease of use (11) and affordability (8); its complaints are poor support (5) and payment problems (3). Vultr also has nearly three times as many responses, so its average is the more settled of the two.

Treat these as direction, not decimals. Other aggregators use unexplained scales, and one scores Vultr 1.6/5 and UpCloud 3.0/5 on "customer reputation" from a few hundred reviews, a number that cannot be lined up next to G2's 8.8/10. The one consistent signal across sources is that support is UpCloud's strongest attribute and Vultr's weakest.

## When UpCloud is the better buy

Vultr is the recommendation for most readers here, but there are workloads where choosing it costs money:

- **Sustained high egress.** Multi-terabyte outbound traffic is free within fair use on UpCloud and $10/TB on Vultr after the allowance.
- **A contract that needs an EU entity and a compensation clause.** UpCloud's Finnish headquarters and 100% SLA with 50x compensation are the easier documents to sign.
- **You want the cheapest VM at a given RAM size and small disks are fine.** UpCloud wins all four matched sizes.
- **Redis and load balancing are core to the stack.** $8 against $15 for Redis, and a free load balancer against $10/month.
- **You need a B300, an L4 or an RTX PRO 6000.** Vultr doesn't list those.

## Vultr billing details that change the math

A few things about Vultr's billing only show up in the docs, and they affect what you actually pay:

- **Stopping is not destroying.** A stopped instance keeps billing in full until you destroy it. If you spin up a test server and shut it down, the meter keeps running.
- **Cloud Compute is capped at 672 hours per month.** Hourly billing works out to the monthly price for a server that runs continuously, so there is no penalty for hourly over monthly on a long-lived instance. VX1 instances bill on actual hours in the month instead, with no 672-hour cap.
- **One public IPv4 is included per instance.** Reserved IPs cost $3/month.
- **Snapshots cost $0.05/GB-month** on compressed size and can be used in any region to clone a filesystem, though not memory.
- **Regional pricing varies.** Some locations carry a premium on many plans, so the same tier can cost more depending on where you deploy.
- **New-account credits exist but are not cash.** Vultr's coupons page currently lists new-customer codes including FLY300VULTR ($300 credit), FLYTWOHUNDRED ($200) and VULTRMATCH (deposit matched up to $100). All are new customers only, apply to select products and cannot be combined. Credits are non-refundable and unused balances do not convert to cash, so size the trial to what you'll actually use.

👉 [Start on the $2.50 tier and resize once you know the load](https://www.vultr.com/products/cloud-compute/?ref=9738262-9J)

## Pick by workload, not by headline

The decision rule is short enough to apply before you finish your coffee:

- **A small site, API or side project under 1 TB of monthly egress:** Vultr, starting at $2.50 and moving to the $5.00 or $12.00 High Performance tier when the workload gets dynamic.
- **Storage and disk-heavy workloads:** Vultr, where block storage is roughly 60% cheaper at the reference configuration.
- **Need a region Vultr covers and UpCloud doesn't, or a wider GPU menu:** Vultr, with roughly 30+ locations and 9 GPU models.
- **Multi-terabyte egress, an EU contracting entity, a Redis-heavy stack or a free load balancer:** UpCloud, and the savings there can exceed the compute difference several times over.
- **H100 or L40S work:** compare per-hour rates at both, since UpCloud is cheaper on those two models while Vultr is cheaper on the B200.

Two things to confirm before you provision anywhere: the price in your specific region, since list prices vary by location, and whether the plan's included transfer covers a normal month for you, because overage is where budget estimates break.

👉 [Compare Vultr's plan families and current prices](https://www.vultr.com/pricing/?ref=9738262-9J)
