# 云 服务：DMIT 三大机房全套餐价格对比，CN2 GIA / Eyeball / Tier 1 线路怎么选不踩坑

挑云服务的时候，多数人卡在同一个地方：机房选哪个、线路选哪条、套餐选哪档。光看价格表就觉得头大，再加上一堆 Premium、Eyeball、Tier 1、CN2 GIA、CMIN2 的术语，新手很容易直接照着最便宜的下单，结果买回去发现晚高峰丢包、延迟飙到 200ms 以上，建站也好、跑服务也好，体验都谈不上。

这篇文章把 DMIT 当前在售的全套餐拉出来对比——洛杉矶、香港、东京三个机房，每条线路每个档位的价格、配置、流量、端口都列清楚，再按使用场景给出选型建议。看完你应该能判断自己到底需要哪一档。

## DMIT 是什么

DMIT 是一家主打中国优化线路的海外 VPS 服务商，机房分布在洛杉矶、香港、东京三个城市，虚拟化采用 KVM，硬件是企业级 SSD，每个实例标配 1 个 IPv4 和 1 个 IPv6 /64 地址，自带基础 DDoS 防护。它的卖点不是便宜，而是回程线路质量——尤其是面向中国大陆的三网优化。

和那些只做"国际线路"的廉价 VPS 不一样，DMIT 把网络分成三个明确的系列，对应不同的路由策略和价格档位。这也是为什么同一档配置在不同系列下价格能差出两三倍——你付的钱很大一部分买的是线路，不是 CPU 和内存。

## 三条网络线路：Premium、Eyeball、Tier 1

这是 DMIT 整个产品体系的底层逻辑，理解了这三条线，后面所有套餐对比才有意义。

**Premium Network（CN2 GIA 线路）**
Premium 是 DMIT 的旗舰线路，回程走中国电信 CN2 GIA（AS23764），同时对联通和移动也做了优化路由。官方给的数据是到中国大陆平均延迟约 15ms²、丢包率低于 0.1%。这条线路的定位是"对大陆用户访问体验有硬性要求的场景"——比如面向国内用户的建站、API 服务、跨境业务系统。价格最高，但晚高峰稳定性也最好。

**Eyeball Network（CMIN2 / CMI 线路）**
Eyeball 是 Premium 的"折中款"，官方说法是 Tier 1 transit 加 reasonable-effort 的 China routing，走 CMIN2 或 CMI 这类中国运营商的优化路由。它对中国大陆有优化，但不是 Premium 那种全程 CN2 GIA 级别。价格比 Premium 便宜不少，流量给得也更多，适合预算有限但又不希望完全放弃大陆优化的人。

**Tier 1 Network（国际线路，无大陆优化）**
Tier 1 就是纯国际线路，优化方向是亚美之间、欧亚之间的国际路由，不针对中国大陆做任何特殊处理。价格最低，流量最大，端口也大。如果你服务的用户主要在海外，或者你自己不在大陆、不需要 CN2 GIA，Tier 1 性价比最高。

一句话总结：要给大陆用户用、体验要稳，选 Premium；预算有限、能接受 reasonable-effort，选 Eyeball；服务对象在海外、跟大陆优化没关系，选 Tier 1。

## 三个机房的区别

**洛杉矶（LAX）**
DMIT 的旗舰机房，套餐最全，从 TINY 一直到 MEDIUM 都有。Premium 系列在洛杉矶端口给到 10Gbps，是三个机房里带宽最慷慨的。如果你不确定选哪个机房，洛杉矶是默认答案——线路成熟、套餐丰富、年付还有入门款可选。

**香港（HKG）**
距离大陆最近，理论上延迟最低，但价格也最贵。香港 Premium 起步价 $79.90/月，比洛杉矶 Premium STARTER 的 $34.90 高出一倍多。端口是 1Gbps，流量也相对少。适合对延迟极其敏感、预算充足的用户。

**东京（TYO）**
介于洛杉矶和香港之间，Premium 起步 $39.90/月。端口 1Gbps，流量比香港略多。东京机房适合服务日本及亚太用户的场景，或者作为香港的替代方案。

## 洛杉矶 Premium 全套餐对比

洛杉矶 Premium 是 DMIT 套餐最全的系列，从入门 TINY 到 MEDIUM 共 6 档，端口最高 10Gbps。以下是当前官网公开展示的配置与价格（月付）：

| 套餐 | vCore | 内存 | SSD | 流量 | 端口 | 月付价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.Pro.TINY | 1 | 2GB | 20GB | 1000GB | 1Gbps | $10.90 | [查看套餐](https://bit.ly/DmiT) |
| LAX.Pro.Pocket | 2 | 2GB | 40GB | 1500GB | 4Gbps | $16.90 | [查看套餐](https://bit.ly/DmiT) |
| LAX.Pro.STARTER | 2 | 2GB | 80GB | 3000GB | 10Gbps | $34.90 | [查看套餐](https://bit.ly/DmiT) |
| LAX.Pro.MINI | 4 | 4GB | 80GB | 5000GB | 10Gbps | $62.90 | [查看套餐](https://bit.ly/DmiT) |
| LAX.Pro.MICRO | 4 | 4GB | 160GB | 7000GB | 10Gbps | $87.90 | [查看套餐](https://bit.ly/DmiT) |
| LAX.Pro.MEDIUM | 6 | 8GB | 160GB | 15000GB | 10Gbps | $199.90 | [查看套餐](https://bit.ly/DmiT) |

TINY 和 Pocket 是入门档，端口只有 1Gbps 和 4Gbps，适合轻量用途——个人代理、小型站点、测试环境。从 STARTER 开始端口升到 10Gbps，流量也跳到 3000GB，这个档位开始才适合正经建站或跑业务。MEDIUM 是这个系列里配置最高的，6 核 8G 内存加 15TB 流量，跑中型应用够用。

> 官网提示：LAX AS3 系列平台仍在建设和优化中，期间可能出现磁盘性能下降和 SLA 低于成熟平台的情况。下单前留意你被分配到的是哪个平台。

## 洛杉矶 Eyeball 与 Tier 1 套餐

Eyeball 和 Tier 1 在洛杉矶只展示了 STARTER、MINI、MICRO 三档：

| 系列 | 套餐 | vCore | 内存 | SSD | 流量 | 端口 | 月付价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Eyeball | LAX.EB.STARTER | 2 | 2GB | 80GB | 5000GB | 10Gbps | $29.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | LAX.EB.MINI | 4 | 4GB | 80GB | 10000GB | 10Gbps | $58.88 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | LAX.EB.MICRO | 4 | 4GB | 160GB | 14000GB | 10Gbps | $74.99 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | LAX.T1.STARTER | 1 | 2GB | 40GB | 4000GB | 按性能 | $12.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | LAX.T1.MINI | 2 | 2GB | 60GB | 8000GB | 按性能 | $21.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | LAX.T1.MICRO | 4 | 4GB | 80GB | 16000GB | 按性能 | $32.90 | [查看套餐](https://bit.ly/DmiT) |

注意 Tier 1 的端口写的是"Based on performance"，不保证固定带宽，但流量给得非常大——MICRO 档 16TB，几乎是同档 Premium 的两倍多。这也是 Tier 1 性价比的来源：你拿不到 CN2 GIA，但拿到了大量流量和便宜的价格。

Eyeball 的流量比 Premium 同档多出不少，价格又低一截。如果你对大陆优化有需求但又不想付 Premium 的价，Eyeball 是值得考虑的中间选项。

## 香港全套餐对比

香港机房三个系列都有展示，但 Premium 和 Eyeball 的价格明显比洛杉矶高一档：

| 系列 | 套餐 | vCore | 内存 | SSD | 流量 | 端口 | 月付价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Premium | HKG.Pro.STARTER | 1 | 2GB | 40GB | 800GB | 1Gbps | $79.90 | [查看套餐](https://bit.ly/DmiT) |
| Premium | HKG.Pro.MINI | 2 | 2GB | 60GB | 1200GB | 1Gbps | $119.90 | [查看套餐](https://bit.ly/DmiT) |
| Premium | HKG.Pro.MICRO | 4 | 4GB | 80GB | 1600GB | 1Gbps | $159.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | HKG.EB.STARTERv2 | 1 | 2GB | 40GB | 2000GB | 2Gbps（不保证） | $59.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | HKG.EB.MINIv2 | 2 | 2GB | 60GB | 3000GB | 2Gbps（不保证） | $89.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | HKG.EB.MICROv2 | 4 | 4GB | 80GB | 4000GB | 4Gbps（不保证） | $129.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | HKG.T1.STARTER | 1 | 2GB | 40GB | 4000GB | 按性能 | $12.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | HKG.T1.MINI | 2 | 2GB | 60GB | 8000GB | 按性能 | $21.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | HKG.T1.MICRO | 4 | 4GB | 80GB | 16000GB | 按性能 | $32.90 | [查看套餐](https://bit.ly/DmiT) |

香港 Premium 的流量是硬伤——STARTER 只有 800GB，端口 1Gbps。同样 $79.90 在洛杉矶 Premium 能买到 MINI（4 核 4G、5000GB 流量、10Gbps 端口）。香港的溢价买的是地理位置带来的低延迟，不是配置。

有意思的是香港 Tier 1 的价格和洛杉矶 Tier 1 完全一样（$12.90 / $21.90 / $32.90），流量也一样。如果你纯粹要一个香港 IP 的国际线路 VPS，Tier 1 是非常划算的。

## 东京全套餐对比

东京机房定位介于洛杉矶和香港之间：

| 系列 | 套餐 | vCore | 内存 | SSD | 流量 | 端口 | 月付价格 | 购买 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Premium | TYO.Pro.STARTER | 1 | 2GB | 40GB | 500GB | 1Gbps | $39.90 | [查看套餐](https://bit.ly/DmiT) |
| Premium | TYO.Pro.MINI | 2 | 2GB | 60GB | 1000GB | 1Gbps | $79.90 | [查看套餐](https://bit.ly/DmiT) |
| Premium | TYO.Pro.MICRO | 4 | 4GB | 80GB | 2000GB | 1Gbps | $159.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | TYO.EB.STARTER | 1 | 2GB | 40GB | 2000GB | 2Gbps（不保证） | $55.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | TYO.EB.MINI | 2 | 2GB | 60GB | 3000GB | 2Gbps（不保证） | $85.90 | [查看套餐](https://bit.ly/DmiT) |
| Eyeball | TYO.EB.MICRO | 4 | 4GB | 80GB | 4000GB | 4Gbps（不保证） | $119.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | TYO.T1.STARTER | 1 | 2GB | 40GB | 4000GB | 按性能 | $12.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | TYO.T1.MINI | 2 | 2GB | 60GB | 8000GB | 按性能 | $21.90 | [查看套餐](https://bit.ly/DmiT) |
| Tier 1 | TYO.T1.MICRO | 4 | 4GB | 80GB | 16000GB | 按性能 | $32.90 | [查看套餐](https://bit.ly/DmiT) |

东京 Premium STARTER $39.90 比香港 Premium STARTER $79.90 便宜一半，流量少 300GB（500GB vs 800GB）。如果你对延迟没那么敏感、又想要 CN2 GIA 线路，东京 Premium 的入门门槛比香港友好得多。

## 月付还是年付：计费周期与差价

DMIT 支持月付和年付两种计费周期，官网明确写"flexible monthly or annual billing"。年付通常比月付折算下来便宜，这也是为什么很多第三方测评里提到的"年付 $36.9 起""年付 $49.9"这类价格——那是年付均摊到每个月的成本，不是月付价格。

具体到每个套餐的年付价格，官网 Pricing 页面的表格标注"products and prices in the table may not be updated in time due to adjustment, for reference only"，意思是页面价格不一定实时更新，最终以下单页为准。所以如果你看到第三方文章里的年付价格和官网表格对不上，以官网 checkout 页面显示的实际价格为准。

> 建议：确定要长期用的话，直接走年付更划算；不确定、想先试水，先月付跑一个月看线路质量再决定续不续。

## 优惠码和促销活动

DMIT 不定期推促销活动，历史上出现过 Summer Sale、Christmas Event 这类节日促销，通常是年付额外折扣或额外流量。当前能从第三方优惠码站点找到的码包括面向 LAX T1 年付套餐的终身 20% 折扣码、面向 Eyeball 季付/年付的 20% recurring 折扣码等。

但需要提醒：这些优惠码大多来自第三方聚合站点，不是 DMIT 官方页面直接公示的，存在过期或仅限特定套餐的情况。下单前最稳妥的做法是在 checkout 页面实际输入测试，能减就是有效，不能减就是过期了。不要看到"70% off""45% lifetime"这种标题就当真——很多是引流话术。

👉 [去 DMIT 官网查看当前实际可用的促销](https://bit.ly/DmiT)

## 按场景选型：不同需求怎么挑

**场景一：面向大陆用户的建站 / API 服务**
首选洛杉矶 Premium STARTER 及以上。$34.90/月拿到 2 核 2G、3000GB 流量、10Gbps 端口，CN2 GIA 回程保证晚高峰稳定性。如果流量吃紧，升到 MINI（$62.90，5000GB）或 MICRO（$87.90，7000GB）。

**场景二：预算有限、又想要大陆优化**
洛杉矶 Eyeball STARTER，$29.90/月，5000GB 流量比 Premium STARTER 还多 2000GB，价格便宜 $5。线路是 CMIN2 reasonable-effort，不如 CN2 GIA 稳，但日常使用完全够。

**场景三：服务对象在海外、不需要大陆优化**
洛杉矶 Tier 1 MINI，$21.90/月，2 核 2G、8000GB 流量。或者 MICRO，$32.90，4 核 4G、16TB 流量。这个性价比在海外 VPS 里相当能打。

**场景四：对延迟极度敏感、预算充足**
香港 Premium。但要做好心理准备：$79.90 起步只拿到 1 核 2G、800GB 流量。香港 Eyeball 是折中方案，$59.90 起步，2000GB 流量，2Gbps 端口（不保证）。

**场景五：日本及亚太用户为主**
东京 Premium STARTER，$39.90，比香港便宜一半，CN2 GIA 线路质量在线。如果预算够，东京 Eyeball 流量更大（2000GB 起）、价格更低（$55.90 起）。

## 常见疑问

**DMIT 支持 ISO 自定义系统吗？**
支持。官网明确提供 ISO 挂载功能，可以挂载 CDROM 安装非常规操作系统，常规 Linux 发行版支持一键安装。

**有没有备份和快照？**
有。在线备份按 $0.45/GB/月 起计费，Snapshot 可以随时对运行中的实例做快照并随时回滚。

**Tier 1 的 IP 能不能保证对中国大陆可达？**
不能。官方说明里，Premium 和 Eyeball 保证分配的首个 IP 可达，Tier 1 不保证这一点——IP 更可能是区域性广播。

**超流量会怎样？**
DMIT 对超流量的处理是按套餐走的，部分低价套餐（比如早期的 TINY、SHARE）超流量后会暂停服务，常规套餐一般是限速或按量计费。具体规则以下单时套餐说明为准，不同系列政策不一样。

## 购买流程

1. 进入 DMIT 官网，选择 Cloud Instance
2. 选机房（Los Angeles / Hong Kong / Tokyo）
3. 选网络系列
4. 选套餐档位和计费周期（月付 / 年付）
5. 有优惠码的在 checkout 页面输入
6. 完成支付，实例自动部署，几分钟内可用

支持支付宝、PayPal、信用卡等常见支付方式。新购套餐免设置费（Free Setup）。

## 写在最后

DMIT 的套餐体系看着复杂，拆开来看逻辑其实清楚：三个机房 × 三条线路 × 若干档位。真正决定你花钱多少的不是配置，是线路——同样是 2 核 2G，Tier 1 只要 $12.90，Premium 要 $34.90，香港 Premium 要 $79.90。差出来的钱买的全是路由质量。

如果你还在纠结，最简单的判断方式：先想清楚你的用户在哪里。用户在大陆、对体验有要求，Premium；用户在大陆、预算有限能接受波动，Eyeball；用户在海外，Tier 1。机房选洛杉矶基本不会错，香港留给预算充足、对延迟敏感的人，东京留给偏亚太的场景。

👉 [去 DMIT 看看当前全套餐和实时价格](https://bit.ly/DmiT)
