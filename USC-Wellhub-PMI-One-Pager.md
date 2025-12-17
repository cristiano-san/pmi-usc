# USC-Wellhub Partner Platform Integration
## One-Page Strategy Overview

---

## Executive Summary

**The Opportunity:**
The USC-Wellhub partnership creates Europe's largest, highest-quality partner network. However, two platforms create operational inefficiency, duplicate costs, and fragmented partner experience.

**The Challenge:**
Integrate two complex partner platforms with different data models, payment systems, and partner experiences—while maintaining zero disruption to service, partner relationships, and business growth.

**The Solution:**
18-month risk-first integration strategy across three 6-month phases, starting with backend payout reconciliation (highest risk, lowest visibility) and ending with a unified partner portal. Germany MVP (1,000 partners) validates our approach in Month 6 before full rollout.

**Business Impact:**
- **Unified partner network** - Single experience across Europe's largest fitness/wellness network
- **Operational efficiency** - Eliminate dual platform overhead by Month 18
- **Revenue protection** - Zero disruption maintains partner trust and prevents churn
- **Growth enabler** - Cross-network access unlocks new partner value (Phase 3)

**Timeline:** H1 2026 → H1 2027 (three 6-month cycles aligned with USC planning)

---

## The Problem

### Current State: Two Separate Platforms

**For Partners:**
- Manage two separate portals with duplicate data entry
- Unclear which platform has authoritative data
- Difficult to reconcile payments across both networks
- Inconsistent support experience (two teams, different processes)

**For USC:**
- Significant operational overhead running dual platforms
- Significant engineering capacity on "keeping lights on" vs innovation
- 2× incident surface area (double the monitoring, support, compliance)
- Missed opportunities for partner value (can't offer cross-network access)
- Data synchronization issues create partner trust problems

### Why Now?

1. **Strategic priority:** USC-Wellhub merger makes platform unification a strategic imperative
2. **Partner feedback:** Payment and platform issues drive partner churn
3. **Operational costs:** Dual platforms consume significant resources
4. **Growth constraint:** Can't launch cross-network features until unified
5. **Technical debt:** Integration delays compound complexity over time

---

## The Solution: Risk-First Phased Integration

### Strategic Approach

**Core Principle:** Tackle highest-risk, lowest-visibility dependencies first

We prioritized all dependencies using: **Priority Score = (Criticality × Complexity) / Time to Resolve**

**Result:** Three phases addressing risks in order of operational impact

---

## Phase 1 (H1 2026): Backend Unification
**Focus:** Payouts & Data Foundation

### Why Payouts First?
- **Highest operational risk:** Payment failures = immediate partner churn
- **Lowest visibility:** Backend changes invisible to partners (safe to validate approach)
- **Foundation for everything:** Unified data schema enables all subsequent phases

### Key Deliverables

**Month 1: Discovery & Analysis**
- Map both payment systems (timing models, reconciliation logic, provider integrations)
- Identify edge cases (multi-currency, FX, regional tax regulations)
- Define unified data schema
- Payment provider assessment (Stripe, Adyen, local providers)

**Months 2-3: Translation Layer**
- Build unified API on top of legacy databases
- Zero disruption - both platforms continue working
- Enables parallel development (new features use unified API)
- 6-month bridge with hard sunset deadline (forcing function)

**Months 4-5: Unified Payout Engine**
- Single payout engine supporting both payment models
- Multi-currency support across all European markets
- Automated reconciliation and FX handling
- 100% payout calculation validation vs legacy systems

**Month 6: Germany MVP**
- **Scope:** 1,000 partners (500 USC + 500 Wellhub) - controlled subset
- **Goal:** Validate data mapping and payout accuracy before full rollout
- **Success criteria:** >95% automated migration, <10 support tickets, 100% payout match

### Decision Framework: Why Translation Layer?

**Three Options Considered:**

| Option | Pros | Cons | Decision |
|--------|------|------|----------|
| **Big Bang Migration** | Fast, clean final state | High risk, no rollback | ❌ Rejected |
| **Translation Layer (6-mo bridge)** | Zero disruption, validates approach | Temporary overhead | ✅ Selected |
| **Dual-Write Forever** | Permanent safety net | Technical debt compounds | ❌ Rejected |

**Why translation layer wins:**
- Proves data mapping works before committing to final migration
- Provides rollback path if Germany MVP fails
- Creates forcing function (6-month sunset) to prevent drift
- Enables learning without partner impact

---

## Phase 2 (H2 2026): Partner-Facing Unification
**Focus:** Unified Partner Portal

### Why Portal Second?
- **Depends on Phase 1:** Requires unified data foundation from payout reconciliation
- **High visibility:** Partner-facing changes require confidence from successful MVP
- **User adoption risk:** New UI = partner training, change management

### Key Deliverables

**Months 7-9: Payout System Rollout**
- Wave-based migration to all European markets
- Automated reconciliation dashboard for Finance team
- Partner communication (10+ languages across markets)
- 24/7 support coverage during migration windows

**Months 10-12: Build Unified Portal**
- Single login for all partner locations
- Real-time earnings visibility and payout tracking
- Unified schedule/content management (CMS integration)
- Mobile-responsive design (React/Next.js, TypeScript, Tailwind CSS)

---

## Phase 3 (H1 2027): Cross-Network Value
**Focus:** Revenue Growth Features

### Why Cross-Network Last?
- **Highest business value:** New revenue opportunities, competitive differentiation
- **Requires stable foundation:** Can't launch new features until platforms unified
- **Change management:** Partners and members require cross-network education

### Key Deliverables

**Months 13-15: Portal Rollout**
- Wave-based partner migration to new portal
- Training materials and live onboarding sessions
- Support agent tooling and escalation paths

**Months 16-18: Cross-Network Access**
- USC members can book Wellhub partners (and vice versa)
- Device authorization for Wellhub partners (if using check-in devices)
- Expanded partner value proposition
- Legacy platform sunset (final cutover)

**Branding Note:** Final strategy (USC retention vs. consolidation) determined by leadership. Platform supports any configuration.

---

## North Star Metric & Key Results

### North Star: Single Partner Experience Achieved
- **Current:** 0% (two separate platforms)
- **Target:** 90%+ partners on unified platform by June 2027
- **Phase 1 Milestone:** Germany MVP validated (1,000 partners migrated)

### Phase 1 (H1 2026) Key Results

#### **KR1: Platform Stability**
| Sub-Metric | Target | How Measured | Why It Matters |
|------------|--------|--------------|----------------|
| **Payout Accuracy** | 99.9% | (Correct payouts / Total payouts) × 100<br>*Correct = ±€0.01, correct account, correct date* | Max 30 errors/month for 30,000 transactions. Partners churn if paid incorrectly. |
| **Platform Uptime** | 99.9% | Portal + API + Payment processing availability | Max 43 min downtime/month. Critical during month-end payouts. |
| **Payment SLA** | 95% | Payments initiated within 24h of trigger | Allows 5% for bank holidays, verification holds. |

#### **KR2: Germany MVP Success**
| Sub-Metric | Target | How Measured | Why It Matters |
|------------|--------|--------------|----------------|
| **Partners Migrated** | 1,000 | 500 USC + 500 Wellhub using unified portal | 95% confidence, ±3% margin. Validates both payment models. |
| **Automated Success** | >95% | No manual intervention / Total × 100 | Max 50 manual fixes. Must scale to 8,000+ partners Europe-wide. |
| **Support Tickets** | <10 | Critical tickets in first 30 days | <1% complaint rate acceptable for new system. |

#### **KR3: Organizational Velocity**
| Sub-Metric | Target | How Measured | Why It Matters |
|------------|--------|--------------|----------------|
| **Decision Time** | <5 days | Proposal raised → Decision documented | Prevents engineering blockers, Phase 2 delays. |
| **Blocker Resolution** | <2 days | Blocker flagged → Resolved/workaround | Cross-functional coordination requirement. |
| **Team Happiness** | >80% | Quarterly pulse survey (both USC + Wellhub teams) | Leading indicator of organizational dysfunction. Low morale → high attrition → velocity drops. |

**Go/No-Go Criteria (Month 6):**
- If Germany MVP <95% automated success → Pause rollout, investigate root causes
- If >10 support complaints from 1,000 migrated partners → Reassess partner communication strategy
- If payout SLA missed → Extend Phase 1, do not proceed to Phase 2

---

## Top 3 Dependencies & Mitigation

### Dependency #1: Data Schema Unification
**Priority Score:** 0.75 (Criticality: 10, Complexity: 9, Time: 120 days)

**Challenge:** USC and Wellhub use different data models for partners, check-ins, contracts, and CMS content. Every downstream system depends on unified schema.

**Mitigation:**
- Translation layer provides abstraction during migration
- Automated data validation (100% accuracy checks)
- Dual-write to both schemas during Phase 1 (safety net)
- Germany MVP validates mapping before full rollout

**Early Warning Signal:** Reconciliation errors >0.1% trigger investigation

---

### Dependency #2: Payment Infrastructure & Reconciliation
**Priority Score:** 0.89 (Criticality: 10, Complexity: 8, Time: 90 days)

**Challenge:** USC and Wellhub likely use different payment systems, timing models, and reconciliation logic. Multiple currencies, different payment providers, and complex FX handling across European markets.

**Mitigation:**
- Month 1 discovery maps all payment edge cases and system differences
- Unified payout engine designed to support both systems
- Automated reconciliation dashboard (real-time)
- 100% payout calculation validation vs legacy systems
- Germany MVP tests both systems simultaneously

**Early Warning Signal:** Partner payment complaints >10/week

---

### Dependency #3: Partner Communication & Change Management
**Priority Score:** 0.70 (Criticality: 7, Complexity: 6, Time: 60 days)

**Challenge:** Large partner network expects zero disruption. Two separate teams with different processes. 10+ languages across European markets.

**Mitigation:**
- Unified Product Trio (Staff PM + USC Lead + Wellhub Lead)
- Domain Working Groups (Payouts WG, Partner UX WG, Data WG)
- Weekly partner communication (email, in-app, webinars)
- 24/7 support during migration windows
- Translated materials for all European languages

**Early Warning Signal:** Partner satisfaction score <80%

---

## Risk Management

### Risk #1: Running Dual Platforms for 9-12 Months
**Impact:** Operational overhead, significant engineering capacity on maintenance

**Mitigation:**
- Hard deadline June 2027 (no extensions)
- Stop onboarding to legacy after Phase 1
- Weekly cost tracking dashboard
- Feature freeze on legacy platforms

**Why We Accept This Risk:** Big bang failures could lose significant partner network portion. Dual platform overhead de-risks migration. Partner trust takes years to rebuild.

---

### Risk #2: Data Migration Errors Cause Payout Failures
**Impact:** Partner churn if paid incorrectly, legal liability, immediate trust loss

**Mitigation:**
- Translation layer provides rollback path
- Dual-write validation during Phase 1
- Automated reconciliation checks (hourly)
- 100% payout calculation validation
- Germany MVP catches issues before full rollout

**Early Warning Signal:** Daily reconciliation dashboard, automated alerts if >0.1% variance

---

### Risk #3: Partner Adoption of New Portal Slower Than Expected
**Impact:** Extended dual platform period = cost overruns, missed Phase 3 timeline

**Mitigation:**
- Portal design based on user research (both platforms)
- Gradual rollout with opt-in early access
- Training materials and live onboarding webinars
- Dedicated migration support team
- Incentives for early adopters (feature previews)

**Early Warning Signal:** <20% adoption in first month of availability

---

## Organizational Structure

### Product Trio (Strategic Decisions)
- **Staff PM** (facilitator + tiebreaker)
- **USC Partner Lead** (USC context + partner relationships)
- **Wellhub Partner Lead** (Wellhub context + technical knowledge)

**Decision protocol:** Data-driven consensus → A/B testing if no consensus → Staff PM final call

### Domain Working Groups (Execution)
- **Payouts WG:** Finance + Ops from both orgs
- **Partner UX WG:** Product + Design from both orgs
- **Data WG:** Engineering + Data from both orgs

**Forcing functions for alignment:**
- Unified success metrics (both teams measured on same KPIs)
- Weekly demos (share progress, identify blockers)
- Quarterly retrospectives (what's working, what's not)

---

## Success Definition

**Phase 1 is successful if:**
- ✅ Germany MVP: >95% automated migration success
- ✅ Platform stability: No degradation to current baselines
- ✅ Partner trust: <10 support tickets from 1,000 migrated partners
- ✅ Technical validation: Both payment models working in production
- ✅ Organizational velocity: <5 days average decision time

**This unlocks Phase 2 with confidence that:**
1. Data mapping works at scale
2. Payment models are accurate
3. Partner impact is minimal
4. Cross-functional teams are aligned

---

## Next Steps

1. **Leadership approval:** Review and approve 18-month roadmap
2. **Team formation:** Assemble Product Trio + Domain Working Groups
3. **Month 1 kickoff:** Begin payment model discovery and data schema mapping
4. **Stakeholder alignment:** Communicate strategy to Finance, Ops, Support, Engineering
5. **Metrics baseline:** Establish current state for all H1 2026 KRs

---

**Prepared by:** Cristiano Menezes dos Santos<br>
**For:** Urban Sports Club Staff Product Manager Case Study<br>
**Date:** December 2025<br>
**Timeline:** H1 2026 → H1 2027 (18 months)
