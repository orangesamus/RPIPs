---
layout: other-content
title: Introduction to the Tokenomics Rework
nav-title: Part 2 - Introduction to the Tokenomics Rework
description: Describes the contents and benefits of the tokenomics rework at a high level in comparison to the original tokenomics. 
author: Valdorff (@Valdorff), LongForWisdom (@LongForWisdom), Paladin (@Paladin147)
custom-next: /tokenomics-explainers/003-rework-foundation
custom-prev: /tokenomics-explainers/001-why-rework
depth: Intro
---

{% assign cPrev=site.pages | where:"url", page.custom-prev | first %}
{% assign cNext=site.pages | where:"url", page.custom-next | first %}

<div class="prev-next-container">
{%if cPrev %}<a href="{{cPrev.url|relative_url}}">Previous - {{cPrev.title}}</a>{%else%}<span>Previous</span>{% endif %}
{%if cNext %}<a href="{{cNext.url|relative_url}}">Next - {{cNext.title}}</a>{%else%}<span>Next</span>{% endif %}
</div>

## Introduction

Given the issues described in Part 1, we now propose a rework of RPL’s tokenomics. These proposals are a community initiative and are being widely discussed. The proposals directly address issues with the current RPL tokenomics and include changes that should benefit the Rocket Pool protocol as a whole. We are aiming to improve the value and utility of Rocket Pool as a protocol, as well as drive new value to the RPL token, ensuring the protocol’s continued development and longevity.

## Items that directly address tokenomics issues

With the rework, speculation and node operation are separated. It becomes **possible to run a Rocket Pool node with only an ETH bond.**

For the variants of the rework that introduce RPL buy and burn or RPL buy and LP, it **may be sensible to hold RPL as a standalone investment** at protocol maturity because a share of ETH revenue may drive value to the token.

**Staking RPL alongside ETH bonds still has value** with the rework. 
- This is the only group that has pDAO vote weight.
- This group receives a share of protocol revenue proportional to their vote-eligible RPL.
- Vote-eligible RPL maxes out at 150% of bonded ETH.

With the rework, **we do not impose a fixed level of RPL staking exposure onto the market**. Node operators can freely value providing any level of RPL stake alongside their ETH bond. If the revenues make the speculation worthwhile, node operators can speculate but are not forced to do so.

There is **no RPL reward threshold/cliff** with the rework, so we avoid losing rETH supply from node operators exiting minipools to maintain the staking threshold.

## Items addressing other issues

With the rework, smaller ETH bonds will be possible. This **dramatically increases capital efficiency.** Arguably, this is the most important single item in the rework; while other changes impact how revenue is distributed, this change increases how much revenue each unit of capital can generate.

Consider ETH-Only validators receiving a 5% commission on borrowed ETH with various bonds[^1]:
* 8 ETH bond: **15% boost** compared to solo staking rewards.
* 4 ETH bond: **35% boost** compared to solo staking rewards.
* 1.5 ETH bond: **102% boost** compared to solo staking rewards.

Megapool-level penalties and forced validator exits are also included in the rework and are key to making smaller ETH bonds safe enough to use.

Megapools will enable multiple validators to share the same Ethereum withdrawal address – this **reduces initial and ongoing gas costs** for node operators.

**RPL issuance will be reduced from 5% to 1.5%**, because the current 3.5% issuance used for RPL rewards to node operators is no longer necessary.

Forced delegate upgrades (with a grace period) will limit the technical debt the Rocket Pool protocol accumulates from previous versions.

A security council veto will decrease the trust assumptions we currently have (it would take two "rogue" parties to force through an illegitimate proposal).

## Personas

|Persona|Now|With Rework|
|-|-|-|
|**Existing Rocket Pool Node Operator**|I need RPL to create minipool validators. I have to remain collateralized at an RPL staked value of at least 10% of my borrowed ETH to receive RPL issuance rewards. My commission is 14% of my borrowed ETH.|I do not need RPL to create megapool validators. My commission is 5% of my borrowed ETH. If I choose to stake RPL I will receive additional ETH rewards (5% of borrowed ETH revenue from all megapools) proportional to my share of staked RPL. I do not need to maintain a minimum stake to receive these rewards. I may benefit from value accrual to RPL (4% of borrowed ETH revenue from all megapools) or from this revenue being used to increase the rewards for staking RPL. I will no longer receive rewards in RPL. The 5%, 5%, and 4% revenue splits may be adjusted by future pDAO votes.
|**rETH holder**|My staking rewards are a function of solo staking APY and the fee I am charged by Rocket Pool. Currently my rewards are ~86% of solo staking APY since I am charged a fee of ~14%.|My staking rewards are a function of solo staking APY and the fee I am charged by Rocket Pool. Initially my rewards are unchanged at ~86% of solo staking APY since I am still charged a total fee of ~14%. The total fee may be adjusted by future pDAO votes.|
|**Passive RPL Holder**|Holding RPL is speculation on the liquid staking narrative and the utility of RPL as a bond.|In addition to the liquid staking narrative, holding RPL is speculation that the tokenomics changes will cause rETH supply to grow and generate surplus ETH revenue, which *may* be used to accrue value to RPL (via buy+burn or buy+LP) or may go to node operators staking RPL.|
|**ETH-Only Node Operator**|I cannot operate a node with Rocket Pool (unless I form a semitrusted partnership with a speculator)|I can now operate a node with Rocket Pool without exposure to RPL. I initially receive a 5% node operator commission on my borrowed ETH. The 5% commission may be adjusted by future pDAO votes.|



<div class="prev-next-container">
{%if cPrev %}<a href="{{cPrev.url|relative_url}}">Previous - {{cPrev.title}}</a>{%else%}<span>Previous</span>{% endif %}
{%if cNext %}<a href="{{cNext.url|relative_url}}">Next - {{cNext.title}}</a>{%else%}<span>Next</span>{% endif %}
</div>

---

[^1]: ROI is calculated using the following formula `(bonded_eth + commission_pct * borrowed_eth) / bonded_eth` 
