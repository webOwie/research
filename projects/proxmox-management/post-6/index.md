---
layout: default
title: "Proxmox Manager Series · Post 6 — Drift detection after deployment"
description: "Continuously compare intended infrastructure state with running state to detect configuration drift before it becomes failure."
---

# Drift detection after deployment.

**Proxmox Manager Series · Post 6**  
**Topic:** Desired state · Drift detection · Operations

<img class="deep-dive-visual" src="/assets/images/proxmox-management/post-06.jpg" alt="Proxmox Manager Series Post 6: drift detection after deployment">

Infrastructure changes after deployment. CPU and memory allocations get edited, interfaces move, backup jobs disappear, firewall rules drift and emergency fixes quietly become permanent configuration. If the intended state is not compared with the running state, documentation turns into historical fiction.

## Desired state versus actual state

The drift monitor compares normalized configuration records rather than raw provider output. Examples include:

- VM / container template
- CPU allocation
- memory allocation
- disk configuration
- network bridge, VLAN and addressing
- firewall policy
- DNS and certificate state
- backup policy

## Detection pipeline

`Desired state → Observe running state → Normalize → Compare → Classify → Explain → Optional remediation`

A useful drift report should explain **what changed, why it matters and which desired-state declaration is being violated**.

## Classification

Not every difference should trigger the same response:

- **critical** — breaks security, availability or an explicit invariant
- **warning** — meaningful deviation requiring review
- **informational** — expected or low-impact difference
- **ignored** — explicitly accepted divergence

Automatic remediation should be policy-controlled. Some drift can safely converge automatically; destructive or ambiguous differences should stop at a proposed repair plan and require operator approval.

## LinkedIn-ready summary

**Deployment is not the end of infrastructure automation.**

The running system keeps changing. So the intended state and actual state have to be compared continuously.

CPU changed? Memory reduced? Network bridge moved? Backup disappeared?

Detect it. Classify it. Explain it. Then decide whether the system may repair it automatically or needs operator approval.

That closes the Proxmox Manager Series with the part many automation workflows forget: **keeping the deployed system aligned with what was actually intended.**

**Full architecture:** <https://research.webowie.com/projects/proxmox-management/>

[Previous: Post 5](/projects/proxmox-management/post-5/) · [Back to the series](/projects/proxmox-management/)