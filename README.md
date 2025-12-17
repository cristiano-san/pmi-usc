# USC-Wellhub Partner Platform Integration
## Post-Merger Integration Strategy

**Prepared by:** Cristiano Menezes dos Santos<br>
**For:** Urban Sports Club - Staff Product Manager Case Study<br>
**Date:** December 2025<br>

---

## 📑 Table of Contents

- [📋 Repository Overview](#-repository-overview)
- [📖 How to Use This Repository](#-how-to-use-this-repository)
- [📁 Repository Contents](#-repository-contents)
  - [🎯 Core Documents](#-core-documents)
  - [📊 Supporting Materials](#-supporting-materials)
- [🎯 Strategic Approach Summary](#-strategic-approach-summary)
- [💡 Key Strategic Decisions](#-key-strategic-decisions)
- [📞 Contact](#-contact)

---

## 📋 Repository Overview

Hey there! 👋

This repo contains my strategic plan for how we can integrate the USC and Wellhub Partner Platforms following the merger. The big picture: unite our two platforms to create Europe's largest, highest-quality partner network—without disrupting service or growth along the way.

**What we're solving:**
How do we merge two complex partner platforms with different data models, payment systems, and partner experiences while keeping everything running smoothly for our partners, members, and teams?

**How we'll do it:**
An 18-month risk-first approach across three 6-month phases. We'll start with the scary backend stuff (payouts—highest risk but lowest visibility) and work our way to a beautiful unified partner portal everyone will love.

---

## 📖 How to Use This Repository

### If you have **5 minutes:** 
Read this README for the [strategic overview](#-strategic-approach-summary)

### If you have **10 minutes:**
Explore the <a href="https://partnersusc.lovable.app" target="_blank" rel="noopener noreferrer">Unified Partner Portal (Live Demo)</a> to see the Phase 2 end-state

### If you have **15 minutes:**
Read the <a href="USC-Wellhub-PMI-One-Pager.md" target="_blank" rel="noopener noreferrer">One-Page Strategy Overview</a> + <a href="https://partnersusc.lovable.app" target="_blank" rel="noopener noreferrer">Unified Partner Portal</a>

### If you have **30 minutes:**
Review the <a href="https://drive.google.com/file/d/181PL80j-zX44LCDqxoWnO4z5L_kOqONp/view?usp=sharing" target="_blank" rel="noopener noreferrer">Presentation (PDF)</a> + <a href="https://partnersusc.lovable.app" target="_blank" rel="noopener noreferrer">Unified Partner Portal</a> + <a href="https://project-usc-guardian.lovable.app" target="_blank" rel="noopener noreferrer">Migration Dashboard</a> + <a href="https://docs.google.com/spreadsheets/d/1WMBTMieGeJQ6_LPnb1WElzF_vbuWtU-3LoWTMdI4v6s/edit?gid=313478831#gid=313478831" target="_blank" rel="noopener noreferrer">Dependency Mapping</a>

### If you need **full technical details:**
Read the <a href="USC-Wellhub-Partner-Platform-Integration-PRD.md" target="_blank" rel="noopener noreferrer">Product Requirements Document (PRD)</a>

---

## 📁 Repository Contents

### 🎯 Core Documents

#### **1. <a href="https://drive.google.com/file/d/181PL80j-zX44LCDqxoWnO4z5L_kOqONp/view?usp=sharing" target="_blank" rel="noopener noreferrer">Presentation (PDF)</a>**
8-slide presentation covering the complete PMI strategy<br>
**Covers:** 3-phase plan, MVP definition, dependencies, mitigation, metrics, risk management<br>
**Duration:** 20-minute presentation<br>
**Best for:** Complete strategic overview

---

#### **2. [One-Page Strategy Overview](USC-Wellhub-PMI-One-Pager.md)**
Executive summary of the entire PMI strategy
**Sections:**
- Executive Summary
- The Problem
- The Solution (all 3 phases)
- North Star Metric & Key Results
- Top 3 Dependencies
- Risk Management 
- Organizational Structure
- Success Definition

**Length:** ~1,800 words<br>
**Best for:** Quick executive review, high-level strategy overview

---

#### **3. [Unified Partner Portal (Live Demo)](https://partnersusc.lovable.app)**
Interactive prototype of the unified partner portal (Phase 2 deliverable)
**Features:**
- Single interface serving both USC and Wellhub partners
- Combined metrics with network breakdowns (teal for USC, purple for Wellhub)
- Official USC brand design system
- Cross-network announcement modal
- Dashboard, Earnings, Schedule, and My Studios pages
- Professional Lucide React icons throughout

**Technology:** React, Shadcn UI, Recharts, Tailwind CSS<br>

---

#### **4. [Phase 1 Migration Dashboard (Live Demo)](https://project-usc-guardian.lovable.app)**
Interactive monitoring dashboard for Germany MVP migration
**Features:**
- Real-time KR tracking (Platform Stability, Germany MVP Success, Organizational Velocity)
- North Star metric progress visualization
- Migration progress monitoring (1,000 partners)
- Early warning signals & risk monitoring
- Payout accuracy chart (last 30 days)

---

#### **5. [Product Requirements Document (PRD)](USC-Wellhub-Partner-Platform-Integration-PRD.md)**
Comprehensive technical specification for the integration
**Sections:**
- Executive Summary
- Problem Statement
- Goals & Success Metrics
- Solution Overview (3 phases)
- User Personas & Needs
- Phased Delivery Plan (month-by-month)
- Functional Requirements
- Technical Architecture
- Dependencies & Constraints
- Risks & Mitigation
- Organizational Requirements
- Success Criteria

**Length:** ~15,000 words<br>
**Best for:** Detailed technical reference, implementation planning

---

### 📊 Supporting Materials

#### **6. [Dependency Mapping (Google Sheets)](https://docs.google.com/spreadsheets/d/1WMBTMieGeJQ6_LPnb1WElzF_vbuWtU-3LoWTMdI4v6s/edit?gid=313478831#gid=313478831)**
Complete dependency register with priority scoring
**Contains:**
- 31 dependencies across all 3 phases
- Priority scoring methodology (Criticality × Complexity / Time)
- Mitigation strategies
- Owner assignments
- Risk levels

**Best for:** Understanding cross-functional dependencies, mitigation planning

---

## 🎯 Strategic Approach Summary

### Three-Phase Plan (18 Months)

**Phase 1 (H1 2026): Backend Unification**
- Unified payout reconciliation
- Data foundation (translation layer)
- Germany MVP: 1,000 partners validate approach
- **Why first:** Highest operational risk, lowest partner visibility

**Phase 2 (H2 2026): Partner-Facing Unification**
- Unified Partner Portal
- Single login, earnings dashboard, content management
- Wave-based rollout to all European markets
- **Why second:** Depends on Phase 1 data foundation

**Phase 3 (H1 2027): Cross-Network Value**
- Cross-network access (USC members → Wellhub partners)
- Legacy platform sunset
- Competitive moat established
- **Why last:** Highest business value, requires stable foundation

---

## 📊 Key Metrics & Numbers

### North Star Metric
**Single Partner Experience Achieved**
- Current: 0% (two separate platforms)
- Target: 90%+ by June 2027
- Phase 1 Milestone: Germany MVP validated (1,000 partners migrated)

### Phase 1 (H1 2026) Key Results

#### **KR1: Platform Stability**
Ensures the integration doesn't degrade existing service quality.

| Sub-Metric | Target | Calculation | Rationale |
|------------|--------|-------------|-----------|
| **Payout Accuracy** | 99.9% | (Correct payouts / Total payouts) × 100<br><br>*Correct = Amount matches calculation within €0.01 AND paid to correct account AND paid on correct date* | Partners churn immediately if paid incorrectly. 99.9% = max 1 error per 1,000 transactions. With 1,000 partners × avg 30 transactions/month = 30,000 transactions, allows max 30 errors/month. |
| **Platform Uptime** | 99.9% | (Total minutes - Downtime minutes) / Total minutes × 100<br><br>*Measured: Portal availability + API availability + Payment processing availability* | 99.9% = max 43 minutes downtime per month. Downtime blocks partner access to earnings data, schedule management, and payment reconciliation. Critical during month-end payout periods. |
| **Payment SLA** | 95% | (Payments processed within SLA / Total payments) × 100<br><br>*SLA = Payment initiated within 24 hours of trigger event (month-end for monthly, check-in for per-visit)* | 95% allows 5% late payments due to legitimate issues (bank holidays, verification holds). Late payments trigger support tickets and partner complaints. |

**Early Warning Signals:**
- Payout accuracy <99.5% → Immediate investigation
- Uptime <99.5% for 3 consecutive days → Escalate to CTO
- Payment SLA <90% → Review payment provider integration

---

#### **KR2: Germany MVP Success**
Validates that our migration approach works at scale before full European rollout.

| Sub-Metric | Target | Calculation | Rationale |
|------------|--------|-------------|-----------|
| **Partners Migrated** | 1,000 | 500 USC + 500 Wellhub partners successfully using unified portal<br><br>*Success = Partner logged in AND reviewed earnings AND no rollback requested* | Germany represents 12% of European network. 1,000 partners is statistically significant sample (95% confidence, ±3% margin of error) to validate both payment models and data mapping. |
| **Automated Migration Success** | >95% | (Partners migrated without manual intervention / Total partners migrated) × 100<br><br>*Manual intervention = Data correction, custom script, support ticket resolution* | 95% automation = max 50 manual fixes per 1,000 partners. Manual fixes don't scale to 8,000+ partners Europe-wide. <95% = migration process needs improvement before Phase 2. |
| **Support Tickets** | <10 | Critical tickets filed by migrated partners in first 30 days<br><br>*Critical = Cannot access portal, incorrect payout data, missing historical data* | <10 tickets from 1,000 partners = <1% complaint rate. Acceptable threshold for new system. >10 = systemic issues requiring fix before rollout. |

**Go/No-Go Criteria:**
- If automated success <95% → Pause rollout, investigate root causes
- If >10 critical tickets → Reassess partner communication and data validation
- If any payout accuracy issues → Extend Phase 1, do not proceed to Phase 2

---

#### **KR3: Organizational Velocity**
Ensures USC and Wellhub teams can make decisions quickly as one unified organization.

| Sub-Metric | Target | Calculation | Rationale |
|------------|--------|-------------|-----------|
| **Proposal → Decision Time** | <5 days | Average days from proposal submitted to Product Trio to final decision logged<br><br>*Measured: Date proposal raised → Date decision documented + communicated* | 5-day SLA prevents decision bottlenecks. Longer delays = engineering blocked, missed deadlines, Phase 2 at risk. Product Trio must resolve via data, A/B test, or Staff PM tiebreaker within 5 days. |
| **Blocker Resolution Time** | <2 days | Average days from blocker flagged to resolution or workaround implemented<br><br>*Blocker = Issue preventing critical path work (API dependency, data access, approval required)* | 2-day SLA keeps critical path moving. Blockers typically cross-functional (needs both USC + Wellhub resources). Domain Working Groups must resolve within 2 days or escalate. |
| **Team Happiness Score** | >80% | Quarterly pulse survey across both USC and Wellhub teams<br><br>*Survey question: "I'm confident in our integration approach"* | Leading indicator of organizational dysfunction. Low morale leads to high attrition, which impacts velocity. <80% positive sentiment requires leadership intervention. |

**Forcing Functions:**
- Daily standups across both orgs (identify blockers early)
- Weekly Product Trio meetings (decision-making forum)
- Blocker dashboard visible to leadership (accountability)
- Post-decision retrospectives (learn what slows decisions)

### Key Numbers
- **1,000 partners** in Germany MVP (500 USC + 500 Wellhub)
- **18 months** total timeline (H1 2026 → H1 2027)
- **99.9%** payout accuracy target
- **95%** automated migration success

---

## 🔑 Top 3 Dependencies

### 1. Data Schema Unification
**Priority Score:** 0.75 (Criticality: 10, Complexity: 9, Time: 120 days)
**Challenge:** Different data models for partners, check-ins, contracts
**Mitigation:** Translation layer + dual-write validation + Germany MVP

### 2. Payment Infrastructure & Reconciliation
**Priority Score:** 0.89 (Criticality: 10, Complexity: 8, Time: 90 days)
**Challenge:** Two payment models, multi-currency, different providers
**Mitigation:** Unified payout engine + automated reconciliation + 100% validation

### 3. Partner Communication & Change Management
**Priority Score:** 0.70 (Criticality: 7, Complexity: 6, Time: 60 days)
**Challenge:** Large partner network, two teams, 10+ languages
**Mitigation:** Product Trio + domain working groups + weekly communication

---

## 🎯 Organizational Structure

### Product Trio (Strategic Decisions)
- **Staff PM** (facilitator + tiebreaker)
- **USC Partner Lead** (USC context + relationships)
- **Wellhub Partner Lead** (Wellhub context + technical knowledge)

### Domain Working Groups (Execution)
- **Payouts WG:** Finance + Ops from both orgs
- **Partner UX WG:** Product + Design from both orgs
- **Data WG:** Engineering + Data from both orgs

**Forcing functions:**
- Unified success metrics
- Weekly demos
- <5 day decision SLA

---

## 💡 Key Strategic Decisions

### Decision 1: Why Start with Payouts (Phase 1)?
**Risk-First Phasing:** Tackle highest-stakes dependency first
- **Highest operational risk:** Payment failures = immediate partner churn
- **Lowest visibility:** Backend changes invisible to partners
- **Foundation for everything:** Unified data schema enables all subsequent phases

### Decision 2: Why Translation Layer vs Big Bang Migration?
**Three Options Considered:**
| Option | Decision |
|--------|----------|
| Big Bang Migration | ❌ Too risky, no rollback |
| Translation Layer (6-month bridge) | ✅ Zero disruption, validates approach, forcing function |
| Dual-Write Forever | ❌ Technical debt compounds |

### Decision 3: Why Accept Dual Platform Overhead?
**Risk-Based Prioritization:**
We accept 9-12 months of running dual platforms because:
- **De-risks migration:** Germany MVP validates approach before full rollout
- **Prevents partner churn:** Big bang failures could lose significant portion of partner network
- **Provides rollback path:** Translation layer enables safe recovery if issues arise
- **Cost of failure >> cost of caution:** Partner trust takes years to rebuild

<!-- ---

## 🎓 Competencies Demonstrated

| Competency | How Demonstrated |
|------------|------------------|
| **Strategic Vision** | Risk-first phasing, 3-phase roadmap aligned to business goals |
| **Analytical Rigor** | Dependency scoring methodology, cost-benefit analysis |
| **Product Thinking** | MVP/MLP definition, translation layer workaround |
| **Stakeholder Collaboration** | Product Trio model, unified success metrics |
| **Planning Capabilities** | 31 dependencies mapped, detailed mitigation plans |
| **Data-Driven Decisions** | Real-time KR tracking, automated validation | -->

---

## 📞 Contact

**Cristiano Menezes dos Santos**<br>
cristianosantosde@gmail.com<br>
https://www.linkedin.com/in/cristianos

Thank you for reviewing my case study. I look forward to presenting this plan and diving deeper into any areas that interest you during our session.

---

**Repository:** https://github.com/cristiano-san/pmi <br>
**Created:** December 2025 <br>
**Last Updated:** December 15, 2025 <br>
