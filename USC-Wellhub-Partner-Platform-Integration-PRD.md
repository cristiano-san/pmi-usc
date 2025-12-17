# Product Requirements Document
## USC-Wellhub Partner Platform Integration

**Document Owner:** Cristiano Menezes dos Santos<br>
**Last Updated:** December 2025<br>
**Status:** Draft for Case Study<br>
**Target Launch:** June 2027 (18-month integration)<br>

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Problem Statement](#problem-statement)
3. [Goals & Objectives](#goals--objectives)
4. [Success Metrics](#success-metrics)
5. [Solution Overview](#solution-overview)
6. [User Personas & Needs](#user-personas--needs)
7. [Phased Delivery Plan](#phased-delivery-plan)
8. [Functional Requirements](#functional-requirements)
9. [Technical Architecture](#technical-architecture)
10. [Dependencies & Constraints](#dependencies--constraints)
11. [Risks & Mitigation Strategies](#risks--mitigation-strategies)
12. [Organizational Requirements](#organizational-requirements)
13. [Success Criteria & KPIs](#success-criteria--kpis)
14. [Open Questions](#open-questions)
15. [Appendix](#appendix)

---

## Executive Summary

### Overview
Post-merger integration of Urban Sports Club (USC) and Wellhub Partner Platforms to create Europe's largest, highest-quality partner network with a single, unified partner experience.

### The Challenge
USC and Wellhub currently operate two separate Partner Platforms with different data models, payment systems, UX patterns, and operational processes. Partners are confused, data is not synchronized, and operational overhead is high.

### The Solution
Risk-first phased integration over 18 months (H1 2026 → H1 2027) that starts with backend systems (data sync and payouts) before touching partner-facing interfaces, validated through a Germany MVP before full rollout.

### Business Impact
- **Revenue Protection:** Avoid partner churn from integration failures
- **Cost Savings:** Operational efficiency from eliminating dual platforms
- **Competitive Advantage:** Europe's largest unified partner network
- **Partner Satisfaction:** Single login, unified experience, consistent data

### Timeline
- **Phase 1 (H1 2026):** Data Sync & Payouts
- **Phase 2 (H2 2026):** Unified Portal Build
- **Phase 3 (H1 2027):** Portal Rollout & Legacy Sunset

---

## Problem Statement

### Current State

**Two Separate Partner Platforms:**
- USC Partner Portal (legacy system with different tech stack)
- Wellhub Partner Portal (different architecture, features, UX)

**Key Pain Points:**
1. **Data Sync Issues:** Partner information, schedules, and content are out of sync between platforms
2. **Partner Parity Gaps:** Same partners not visible in both networks, creating inconsistent member experience
3. **CMS Integration Complexity:** Partners manage class schedules and content in different systems
4. **Partner Confusion:** Partners unsure which portal to use, receiving inconsistent communication
5. **High Support Overhead:** Dual support systems, inconsistent answers, partner frustration

### Impact on Stakeholders

**Partners:**
- Confusion about which portal to use
- Duplicate work maintaining information in two systems
- Payment inconsistencies and reconciliation issues
- Lack of visibility into unified network performance

**Members:**
- Inconsistent partner availability across USC vs Wellhub apps
- Can't access full network seamlessly
- Booking errors due to data sync issues

**Internal Teams:**
- Engineering: Maintaining two separate platforms (technical debt)
- Operations: Dual processes, higher support overhead
- Finance: Complex reconciliation across two payment systems
- Sales: Inconsistent onboarding and partner acquisition flows

### Why Now?
- **Strategic priority:** USC is now part of Wellhub - unifying platforms is a company-level strategic imperative post-merger
- Dual platforms prevent operational efficiency gains
- Competitive pressure to deliver unified network value
- Technical debt compounds with integration delays

---

## Goals & Objectives

### North Star Metric
**Single Partner Experience Achieved**
- Current: 0% (two separate platforms)
- Target: 90%+ partners on unified platform by June 2027
- Phase 1 Milestone: Germany MVP validated (1,000 partners migrated)

### Business Goals

**BG1: Revenue Protection**
- Maintain partner retention during migration (churn <2%)
- Protect €XXM annual partner revenue
- Enable cross-network revenue opportunities

**BG2: Operational Efficiency**
- Reduce operational costs by eliminating dual platform overhead
- Free up engineering capacity currently spent on "keeping lights on"
- Consolidate support systems (single ticketing, single knowledge base)

**BG3: Competitive Positioning**
- Deliver Europe's largest unified partner network
- Enable cross-network access (USC ↔ Wellhub)
- Improve partner satisfaction (NPS >50)

### User Goals

**Partners:**
- Single login, single portal, single source of truth
- Consistent payment experience across all markets
- Unified analytics and performance insights
- Seamless content management

**Internal Teams:**
- Unified tools and processes
- Clear decision-making framework
- Reduced context switching
- Single metrics dashboard

### Non-Goals (Out of Scope)

**Phase 1:**
- ❌ Partner-facing portal UI changes (Phase 2)
- ❌ Cross-network booking (Phase 3)
- ❌ Contract term harmonization (honor existing contracts)
- ❌ CRM/sales tool unification (Phase 3)

---

## Success Metrics

### North Star Metric
**Single Partner Experience Achieved:** % of partners on unified platform
- Baseline: 0%
- H1 2026 Target: 6% (Germany MVP)
- H2 2026 Target: 40%
- H1 2027 Target: 90%+

### Phase 1 (H1 2026) Key Results

#### KR1: Platform Stability (Non-Disruption)
Ensures the integration doesn't degrade existing service quality.

| Sub-Metric | Baseline | Target | Calculation Formula | Rationale | Tracking |
|------------|----------|--------|---------------------|-----------|----------|
| **Payout Accuracy** | 99.9% | 99.9% | (Correct payouts / Total payouts) × 100<br><br>*Correct = Amount matches calculation within €0.01 AND paid to correct account AND paid on correct date* | Partners churn immediately if paid incorrectly. 99.9% = max 1 error per 1,000 transactions. With 1,000 partners × avg 30 transactions/month = 30,000 transactions, allows max 30 errors/month. | Real-time dashboard, automated alerts |
| **Platform Uptime** | 99.9% | 99.9% | (Total minutes - Downtime minutes) / Total minutes × 100<br><br>*Measured: Portal availability + API availability + Payment processing availability* | 99.9% = max 43 minutes downtime per month. Downtime blocks partner access to earnings data, schedule management, and payment reconciliation. Critical during month-end payout periods. | Monitoring, incident tracking |
| **Payment SLA** | 95% | 95% | (Payments processed within SLA / Total payments) × 100<br><br>*SLA = Payment initiated within 24 hours of trigger event (month-end for monthly, check-in for per-visit)* | 95% allows 5% late payments due to legitimate issues (bank holidays, verification holds). Late payments trigger support tickets and partner complaints. | Payment processing metrics |

**Success Criteria:** No degradation in service quality during migration

**Early Warning Signals:**
- Payout accuracy <99.5% → Immediate investigation
- Uptime <99.5% for 3 consecutive days → Escalate to CTO
- Payment SLA <90% → Review payment provider integration

---

#### KR2: MVP Validation (Project Health)
Validates that our migration approach works at scale before full European rollout.

| Sub-Metric | Baseline | Target | Calculation Formula | Rationale | Tracking |
|------------|----------|--------|---------------------|-----------|----------|
| **Partners Migrated** | 0 | 1,000 | 500 USC + 500 Wellhub partners successfully using unified portal<br><br>*Success = Partner logged in AND reviewed earnings AND no rollback requested* | Germany represents 12% of European network. 1,000 partners is statistically significant sample (95% confidence, ±3% margin of error) to validate both payment models and data mapping. | Migration dashboard |
| **Automated Success Rate** | 0% | >95% | (Partners migrated without manual intervention / Total partners migrated) × 100<br><br>*Manual intervention = Data correction, custom script, support ticket resolution* | 95% automation = max 50 manual fixes per 1,000 partners. Manual fixes don't scale to 8,000+ partners Europe-wide. <95% = migration process needs improvement before Phase 2. | Automated validation scripts |
| **Support Tickets** | 0 | <10 | Critical tickets filed by migrated partners in first 30 days<br><br>*Critical = Cannot access portal, incorrect payout data, missing historical data* | <10 tickets from 1,000 partners = <1% complaint rate. Acceptable threshold for new system. >10 = systemic issues requiring fix before rollout. | Ticket tagging, sentiment analysis |

**Success Criteria:** Germany MVP proves approach is scalable

**Go/No-Go Criteria:**
- If automated success <95% → Pause rollout, investigate root causes
- If >10 critical tickets → Reassess partner communication and data validation
- If any payout accuracy issues → Extend Phase 1, do not proceed to Phase 2

---

#### KR3: Organizational Velocity (Team Alignment)
Ensures USC and Wellhub teams can make decisions quickly as one unified organization.

| Sub-Metric | Baseline | Target | Calculation Formula | Rationale | Tracking |
|------------|----------|--------|---------------------|-----------|----------|
| **Decision Velocity** | [baseline] | <5 days | Average days from proposal submitted to Product Trio to final decision logged<br><br>*Measured: Date proposal raised → Date decision documented + communicated* | 5-day SLA prevents decision bottlenecks. Longer delays = engineering blocked, missed deadlines, Phase 2 at risk. Product Trio must resolve via data, A/B test, or Staff PM tiebreaker within 5 days. | PM tool tracking |
| **Blocker Resolution** | [baseline] | <2 days | Average days from blocker flagged to resolution or workaround implemented<br><br>*Blocker = Issue preventing critical path work (API dependency, data access, approval required)* | 2-day SLA keeps critical path moving. Blockers typically cross-functional (needs both USC + Wellhub resources). Domain Working Groups must resolve within 2 days or escalate. | Sprint board, blocker age |
| **Cross-org Collaboration** | 0% | 100% | Percentage of working groups that include members from both USC and Wellhub<br><br>*Working groups = Payouts WG, Partner UX WG, Data WG* | Forces collaboration at execution level. Ensures decisions incorporate context from both organizations. | Team composition audit |
| **Team Happiness** | [baseline] | >80% | Quarterly team satisfaction survey across both organizations<br><br>*Survey includes: Collaboration quality, Decision clarity, Support from leadership* | High team morale = better execution. <80% indicates friction between organizations requiring intervention. | Quarterly surveys |

**Success Criteria:** Two organizations working as one unified team

**Forcing Functions:**
- Daily standups across both orgs (identify blockers early)
- Weekly Product Trio meetings (decision-making forum)
- Blocker dashboard visible to leadership (accountability)
- Post-decision retrospectives (learn what slows decisions)

### Phase 2 & 3 Metrics
*(To be defined based on Phase 1 learnings)*

---

## Solution Overview

### Strategic Approach: Risk-First Phased Integration

**Core Principle:** Start with highest-stakes, lowest-visibility dependencies first.

**Why This Approach:**
1. **Validates data foundation before touching UIs** - Backend payout reconciliation proves data model works
2. **Enables rollback** - Translation layer provides safety net if assumptions prove wrong
3. **Gradual learning** - Germany MVP (controlled subset) tests approach before full rollout
4. **Maintains optionality** - Can pause/pivot between phases based on results

### Three-Phase Plan (18 Months)

```
H1 2026 [6 months]    H2 2026 [6 months]    H1 2027 [6 months]
─────────────────     ─────────────────     ─────────────────
PHASE 1               PHASE 2               PHASE 3
Data Sync &           Unified Portal        Portal Rollout &
Payouts               Build                 Legacy Sunset
```

**Phase 1 (H1 2026): Data Sync & Payouts**
- Month 1: Discovery & data mapping
- Month 2-3: Translation layer (immediate data sync relief)
- Month 4-5: Unified payout engine build
- Month 6: Germany MVP validation

**Phase 2 (H2 2026): Unified Portal Build**
- Month 7-9: Payout rollout to all partners (wave-based)
- Month 10-12: Build unified portal (best of USC + Wellhub)

**Phase 3 (H1 2027): Portal Rollout & Legacy Sunset**
- Month 13-15: Portal rollout (90%+ adoption)
- Month 16-18: Cross-network access + legacy sunset

### MVP & MLP Definitions

#### Minimum Viable Product (MVP) - Month 6
**Scope:** Germany-only, 1,000 partners (500 USC + 500 Wellhub)

**What we're validating:**
- Can we map USC + Wellhub data models to unified schema?
- Do payout calculations match both legacy systems (100% accuracy)?
- Can we meet payment deadlines (critical SLA)?
- What edge cases break our assumptions?

**Success Criteria:**
- >95% automated migration success
- 100% payout calculation match with legacy
- <10 partner support tickets
- Both payment systems validated in production

**Why Germany:**
- Largest European market (22% of revenue)
- Well-regulated (good test for compliance)
- Single language (simpler communication)
- Large enough to validate, small enough to contain risk

#### Minimum Lovable Product (MLP) - Months 7-9
**Scope:** All European markets, all partners

**Added capabilities:**
- Multi-currency support (all European markets)
- All partner types (fitness, mindfulness, therapy, nutrition, sleep)
- Finance dashboard (real-time reconciliation status)
- Automated anomaly detection (flag outlier payments)
- Partner communication templates (10+ languages)

**Success Criteria:**
- All partners migrated to unified payouts
- €200K annual savings realized (reconciliation automation)
- Finance team trained and autonomous
- <5 support tickets per 1,000 partners

---

## User Personas & Needs

### Primary Personas

#### Persona 1: Partner Studio Owner
**Demographics:**
- Owns 1-3 fitness/wellness locations
- Age: 30-50
- Tech-savvy: Medium
- Primary concern: Getting paid accurately and on time

**Needs:**
- ✅ Single login to manage all locations
- ✅ Clear visibility into earnings and payouts
- ✅ Easy schedule/content management
- ✅ Minimal learning curve during transition

**Pain Points:**
- 😞 Currently managing two separate portals
- 😞 Unclear which portal has correct data
- 😞 Payment discrepancies hard to reconcile
- 😞 Support gives inconsistent answers

**Success Criteria:**
- Doesn't notice the migration (zero disruption)
- Payment accuracy maintained
- Single source of truth for data

---

#### Persona 2: Corporate Partner Chain (Multi-Location)
**Demographics:**
- Manages 10+ locations across multiple markets
- Age: 35-55
- Tech-savvy: High
- Primary concern: Operational efficiency at scale

**Needs:**
- ✅ Bulk operations (schedule updates, analytics across locations)
- ✅ Advanced analytics and reporting
- ✅ API access for third-party integrations
- ✅ Multi-user access with role-based permissions

**Pain Points:**
- 😞 Duplicate work managing data in two systems
- 😞 Can't compare performance across USC vs Wellhub networks
- 😞 Complex reconciliation for locations in different markets
- 😞 CMS integrations (ClubReady, Fitogram) work differently

**Success Criteria:**
- Improved analytics (unified view across all locations)
- API stability maintained
- Bulk operations work seamlessly

---

#### Persona 3: Partner Support Agent (Internal)
**Demographics:**
- USC or Wellhub Partner Success team member
- Age: 25-40
- Tech-savvy: Medium-High
- Primary concern: Helping partners quickly

**Needs:**
- ✅ Single support portal with unified knowledge base
- ✅ Visibility into partner data across both networks
- ✅ Clear escalation paths
- ✅ Consistent answers to partner questions

**Pain Points:**
- 😞 Switching between two support systems
- 😞 Inconsistent answers from USC vs Wellhub teams
- 😞 Can't see full partner history if they're on other platform
- 😞 Training on two different systems

**Success Criteria:**
- Single ticketing system
- Unified knowledge base
- Cross-org collaboration seamless

---

#### Persona 4: Finance Team Member (Internal)
**Demographics:**
- Finance/Accounting role
- Age: 30-50
- Tech-savvy: Medium
- Primary concern: Accurate reconciliation and audit compliance

**Needs:**
- ✅ Real-time reconciliation dashboard
- ✅ Automated error detection
- ✅ Single source of truth for payout data
- ✅ Audit trail preservation

**Pain Points:**
- 😞 Manual reconciliation across two accounting systems
- 😞 Different revenue recognition methods
- 😞 Payment provider discrepancies
- 😞 Audit failures due to data inconsistencies

**Success Criteria:**
- Automated reconciliation (save 40+ hours/month)
- 100% payout accuracy
- Clean audit trail

---

## Phased Delivery Plan

### Phase 1: Data Sync & Payouts (H1 2026)

#### Month 1: Discovery & Analysis
**Objectives:**
- Map data models (USC vs Wellhub schemas)
- Identify payment flow differences
- Document contract variations
- Assess technical architecture gaps

**Deliverables:**
- Unified data schema design
- Payment flow documentation
- Risk assessment report
- Technical architecture plan

**Key Activities:**
- Joint workshops (USC + Wellhub Partner teams)
- Data mapping sessions (Engineering + Data teams)
- Contract review (Legal + Finance)
- Payment provider API analysis

**Success Criteria:**
- 100% data fields mapped
- Payment flow documented for all 11+ European markets
- Risk register created with mitigation plans
- Go/no-go decision for Phase 1 execution

---

#### Month 2-3: Translation Layer Build
**Objectives:**
- Build unified API on top of legacy databases
- Achieve partner parity (same partners visible in both networks)
- Solve immediate data sync pain points

**Deliverables:**
- Translation layer API (REST endpoints)
- Data sync service (real-time or near-real-time)
- Partner parity validation dashboard
- API documentation

**Key Activities:**
- Build unified API layer
- Implement data transformation logic
- Set up monitoring and alerting
- Load testing and performance validation

**Success Criteria:**
- Partner parity achieved (>99% partners visible in both networks)
- Data sync latency <5 minutes
- API uptime >99.9%
- Zero disruption to existing systems

---

#### Month 4-5: Unified Payout Engine
**Objectives:**
- Build single payout calculation engine
- Integrate with all payment providers (11+ markets)
- Support both payment systems and timing models

**Deliverables:**
- Unified payout engine
- Payment provider integrations
- Automated reconciliation dashboard
- Finance team training materials

**Key Activities:**
- Build payout calculation logic
- Integrate payment providers (Stripe, Adyen, local providers)
- Implement dual-write validation
- Create reconciliation dashboard for Finance
- Train Finance team

**Success Criteria:**
- 100% payout calculation accuracy (matches legacy)
- All payment providers integrated
- Automated reconciliation reduces manual work by 80%
- Finance team signed off and trained

---

#### Month 6: Germany MVP
**Objectives:**
- Migrate 1,000 Germany partners (500 USC + 500 Wellhub)
- Validate entire end-to-end flow
- Catch edge cases before full rollout

**Deliverables:**
- 1,000 partners migrated to unified payouts
- Migration success report
- Edge case documentation
- Go/no-go recommendation for Phase 2

**Key Activities:**
- Execute Germany migration (wave 1: 200 partners pilot, then full 1,000)
- Monitor payout accuracy daily
- Track partner complaints/support tickets
- Conduct partner surveys (Germany cohort)
- Document edge cases and fixes

**Success Criteria:**
- >95% automated migration success
- <10 partner support tickets
- 100% payout accuracy
- Partner NPS maintained or improved
- Clear go decision for Phase 2 rollout

---

### Phase 2: Unified Portal Build (H2 2026)

#### Month 7-9: Payout Rollout to All Partners
**Objectives:**
- Migrate all European market partners to unified payouts
- Wave-based rollout (by country or partner segment)
- Realize cost savings from automation

**Deliverables:**
- All partners on unified payout system
- Legacy payout systems deprecated
- Cost savings report (€200K+ realized)

**Key Activities:**
- Country-by-country rollout (Germany → France → Spain → etc.)
- Monitor each wave for issues
- Partner communication and training
- Legacy system deprecation

**Success Criteria:**
- 100% partners migrated
- Payout accuracy maintained (99.9%)
- €200K+ annual savings realized
- Support ticket volume <baseline

---

#### Month 10-12: Build Unified Portal
**Objectives:**
- Design and build unified Partner Portal
- Combine best features of USC + Wellhub portals
- Integrate with unified CMS

**Deliverables:**
- Unified Partner Portal (beta)
- Design system
- CMS integration
- Beta testing report

**Key Activities:**
- Design sprint (combine best of both portals)
- Frontend development
- CMS integration (single source for schedules, content)
- Beta testing with select partner cohort (500 partners)
- Iteration based on feedback

**Success Criteria:**
- Portal feature parity achieved
- Beta NPS >60
- CMS integration validated
- Ready for Phase 3 rollout

---

### Phase 3: Portal Rollout & Legacy Sunset (H1 2027)

#### Month 13-15: Portal Rollout
**Objectives:**
- Migrate 90%+ partners to unified portal
- Country-by-country rollout with training
- Achieve high adoption

**Deliverables:**
- 90%+ partners on unified portal
- Training materials (10+ languages)
- Support playbook updated

**Key Activities:**
- Country-by-country portal rollout
- Partner training webinars
- Support team training
- Monitor adoption metrics

**Success Criteria:**
- 90%+ adoption
- Partner NPS >50
- Support ticket volume within acceptable range
- Portal uptime >99.9%

---

#### Month 16-18: Legacy Sunset
**Objectives:**
- Enable cross-network access (USC ↔ Wellhub)
- Shut down both legacy portals
- Complete integration

**Deliverables:**
- Cross-network booking enabled
- Both legacy portals decommissioned
- Data archival complete
- Integration complete

**Key Activities:**
- Enable cross-network access for members
- Migrate remaining 10% partners
- Shut down USC Partner Portal (legacy)
- Shut down Wellhub Partner Portal (legacy)
- Archive historical data
- Final reconciliation and audit

**Success Criteria:**
- 100% partners on unified platform
- Cross-network access live
- Both legacy systems shut down by June 30, 2027
- Zero data loss
- Audit compliance maintained

**Note on Branding Strategy:** Final branding approach (USC brand retention vs. full Wellhub consolidation) will be determined by leadership during Phase 3. The unified platform architecture supports either direction - partners can be served under any brand configuration (separate brands, co-branded, or single Wellhub brand). This decision does not impact the technical integration timeline.

---

## Functional Requirements

### FR1: Data Synchronization

**FR1.1: Real-Time Partner Data Sync**
- **Description:** Partner profile data (name, locations, contact info, contracts) synchronized between USC and Wellhub networks in real-time or near-real-time
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - Sync latency <5 minutes
  - Data integrity 100%
  - Conflict resolution logic defined and tested
  - Audit trail for all changes

**FR1.2: Partner Parity**
- **Description:** Same partners visible in both USC and Wellhub member apps (network parity)
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - >99% partners visible in both networks
  - Partner availability accurate (real-time schedule updates)
  - Location data consistent

**FR1.3: CMS Content Sync**
- **Description:** Class schedules, images, descriptions synchronized across platforms
- **Priority:** P1 (High)
- **Acceptance Criteria:**
  - Content updates propagate within 5 minutes
  - Image/media assets synchronized
  - Schedule conflicts auto-resolved or flagged

---

### FR2: Unified Payout System

**FR2.1: Payout Calculation Engine**
- **Description:** Single payout engine supporting both USC and Wellhub payment systems and timing models
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - 100% calculation accuracy vs legacy systems
  - Supports both payment systems
  - Multi-currency support (all European markets)
  - FX conversion accurate and auditable

**FR2.2: Payment Provider Integration**
- **Description:** Integrate with all payment providers (Stripe, Adyen, local providers)
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - All payment providers integrated
  - Payment SLA: 95% on schedule
  - Error handling and retry logic
  - Transaction-level audit trail

**FR2.3: Automated Reconciliation**
- **Description:** Real-time dashboard showing reconciliation status, automated error detection
- **Priority:** P1 (High)
- **Acceptance Criteria:**
  - Daily reconciliation automated
  - Automated alerts if variance >0.1%
  - Finance dashboard with drill-down capability
  - Historical reconciliation data preserved

---

### FR3: Unified Partner Portal

**FR3.1: Single Sign-On (SSO)**
- **Description:** Partners log in once to access unified portal
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - SSO supports both USC and Wellhub credentials (migration period)
  - Session management secure
  - Password reset flow
  - Multi-factor authentication optional

**FR3.2: Unified Dashboard**
- **Description:** Single homepage showing performance across entire network (USC + Wellhub)
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - Check-ins from both networks displayed
  - Earnings summary (all markets)
  - Notifications unified
  - Quick actions (update schedule, view payouts)

**FR3.3: Schedule Management**
- **Description:** Partners manage class schedules in one place
- **Priority:** P0 (Critical)
- **Acceptance Criteria:**
  - Bulk schedule updates
  - Recurring class support
  - Conflict detection
  - Integration with booking systems (ClubReady, Fitogram)

**FR3.4: Analytics & Reporting**
- **Description:** Unified analytics showing performance metrics
- **Priority:** P1 (High)
- **Acceptance Criteria:**
  - Check-in trends (daily/weekly/monthly)
  - Revenue breakdown by network
  - Peak hour analysis
  - Export to CSV/PDF

**FR3.5: Content Management**
- **Description:** Partners manage images, descriptions, amenities in one place
- **Priority:** P1 (High)
- **Acceptance Criteria:**
  - Image upload and cropping
  - Rich text description editor
  - Amenities checklist
  - Preview before publish

---

### FR4: Cross-Network Access (Phase 3)

**FR4.1: Member Booking Across Networks**
- **Description:** USC members can book Wellhub partners (and vice versa)
- **Priority:** P0 (Critical - Phase 3)
- **Acceptance Criteria:**
  - Booking flow seamless
  - Check-in validation works across networks
  - Revenue attribution accurate
  - Contract terms respected

**FR4.2: Unified Pricing Model**
- **Description:** Consistent pricing/revenue share for cross-network usage
- **Priority:** P0 (Critical - Phase 3)
- **Acceptance Criteria:**
  - Pricing model defined and approved (Finance + Legal)
  - Partners notified 60 days in advance
  - Revenue share calculation automated
  - Edge cases documented

---

### FR5: Partner Communication & Support

**FR5.1: Unified Communication Platform**
- **Description:** Single channel for partner communications (email, in-app notifications)
- **Priority:** P1 (High)
- **Acceptance Criteria:**
  - Email templates (10+ languages)
  - In-app notification center
  - SMS option (critical updates)
  - Communication history log

**FR5.2: Unified Support Portal**
- **Description:** Single support ticketing system for partners
- **Priority:** P1 (High)
- **Acceptance Criteria:**
  - Ticketing system supports both USC and Wellhub partners
  - Knowledge base unified
  - Live chat integration
  - SLA tracking (<24hr first response)

---

## Technical Architecture

### High-Level Architecture

```
┌─────────────────────────────────────────────────┐
│            Member Apps Layer                    │
│  (USC App, Wellhub App, Corporate Dashboards)   │
└────────────────┬────────────────────────────────┘
                 │
┌────────────────┴────────────────────────────────┐
│         Unified Partner Portal (Phase 2)        │
│  (React/Next.js, Single Page App, Responsive)   │
└────────────────┬────────────────────────────────┘
                 │
┌────────────────┴────────────────────────────────┐
│          Unified API Layer (Phase 1)            │
│   (REST/GraphQL, Translation Layer, Gateway)    │
└─────┬──────────────────────────────────┬────────┘
      │                                   │
┌─────┴─────────┐                 ┌───────┴────────┐
│  USC Legacy   │                 │ Wellhub Legacy │
│   Database    │                 │   Database     │
│  (PostgreSQL) │                 │   (MongoDB)    │
└───────────────┘                 └────────────────┘
```

### Technology Stack

**Frontend:**
- React/Next.js (unified portal)
- TypeScript
- Tailwind CSS (design system)
- Responsive (mobile-first)

**Backend:**
- Node.js/Express (API layer)
- Python (payout calculation engine)
- GraphQL (flexible querying for analytics)

**Data Storage:**
- PostgreSQL (transactional data)
- Redis (caching, session management)
- S3 (media/content storage)

**Infrastructure:**
- AWS (primary cloud provider)
- Docker/Kubernetes (containerization)
- CloudFront (CDN for static assets)

**Monitoring & Observability:**
- DataDog (APM, metrics, logs)
- Sentry (error tracking)
- PagerDuty (alerting)

**Payment Providers:**
- Stripe (primary, multi-market)
- Adyen (backup/secondary)
- Local providers (market-specific)

---

### Translation Layer Architecture (Phase 1)

**Purpose:** Enable unified API without migrating underlying databases immediately

**How It Works:**
1. Unified API receives request (e.g., "get partner profile")
2. Translation layer determines which legacy system(s) to query
3. Fetches data from USC DB and/or Wellhub DB
4. Transforms data to unified schema
5. Returns normalized response

**Benefits:**
- Zero disruption to legacy systems
- Enables parallel development (new features use unified API)
- Gradual migration (one cohort at a time)
- Rollback capability

**Trade-offs:**
- Performance overhead (~50-100ms latency)
- Short-term complexity (more systems to maintain)
- Mitigation: Hard 6-month sunset forcing function

---

## Dependencies & Constraints

### Critical Cross-Functional Dependencies

#### Dependency #1: Data Schema Unification
**Priority Score:** 1.00 (Critical)

**Problem:**
- USC and Wellhub have different data models for partners, check-ins, and contracts
- Different databases (PostgreSQL vs MongoDB)
- Different business logic and validation rules

**Teams Blocked:**
- Engineering (can't build unified API without schema)
- Data (can't consolidate analytics)
- Legal (different contract term representations)
- Product (can't design unified UX)
- Finance (different payout calculation models)

**Dependency Chain:**
No unified schema → Can't build unified payout engine → Can't sunset legacy platforms

**Mitigation Strategy:**
- **Phase 1 (Month 2-3):** Translation layer as interim solution
- **Phase 1 (Month 4-8):** Gradual schema migration in waves
- **Phase 1 (Month 6):** Validate with Germany MVP
- **Phase 2:** Complete migration, sunset translation layer

---

#### Dependency #2: Cross-Border Payment Infrastructure
**Priority Score:** 1.07 (Critical)

**Problem:**
- Multiple European markets with different payment rails, currencies, tax regulations
- Different payment providers (USC uses X, Wellhub uses Y)
- Different payout schedules (USC monthly, Wellhub weekly/bi-weekly)
- FX conversion timing and rate discrepancies

**Teams Blocked:**
- Engineering (payment provider integrations)
- Finance (reconciliation complexity)
- Legal (multi-jurisdiction compliance)
- Operations (payout schedule coordination)
- Sales (can't onboard partners in certain markets until integrated)

**Dependency Chain:**
No payment infrastructure → Partners don't get paid → Immediate churn → Revenue loss

**Mitigation Strategy:**
- **Phase 1 (Month 1):** Map all payment providers and regulations
- **Phase 1 (Month 4-5):** Integrate with all payment providers
- **Phase 1 (Month 6):** Validate multi-currency in Germany MVP
- **Phase 2 (Month 7-9):** Country-by-country rollout (can skip problematic markets)

---

#### Dependency #3: Partner Communication & Change Management
**Priority Score:** 0.70 (High)

**Problem:**
- Large partner network expecting zero disruption
- Two separate Partner teams (USC vs Wellhub) with different processes
- 10+ languages across European markets
- Partners have different contract terms (can't force migration)

**Teams Blocked:**
- Operations (need unified communication plan)
- Sales (inconsistent partner acquisition flows)
- Product (need partner feedback for portal design)
- Legal (contract migration strategy)

**Dependency Chain:**
No trust → Partners refuse migration → Stuck on dual platforms forever

**Mitigation Strategy:**
- **Phase 1 (Month 1):** Joint discovery workshops (build trust)
- **Phase 1 (Ongoing):** Product Trio model (USC + Wellhub Partner leads)
- **Phase 1 (Month 6):** Germany MVP proves value first
- **Phase 2:** Phased rollout (can pause if resistance detected)
- **Ongoing:** Partner training program (10+ languages)

---

### Technical Constraints

**TC1: Legacy System Maintenance**
- Must maintain both legacy systems operational through Phase 2
- Feature freeze on legacy (only critical bug fixes)
- Security patches must continue

**TC2: Data Residency & GDPR**
- Different data handling practices across European markets
- GDPR compliance required (legal review Month 1)
- Data residency requirements vary by country

**TC3: API Rate Limits**
- Different API architectures and rate limits
- Risk of performance degradation during high-volume sync
- Mitigation: Load testing during Germany MVP, gradual rollout

**TC4: Third-Party Integrations**
- Partners use different booking systems (ClubReady, Fitogram, etc.)
- Must maintain all existing integrations during transition
- API versioning strategy required

---

### Organizational Constraints

**OC1: Zero Disruption Requirement**
- Cannot have "maintenance windows" for migration
- Must maintain 99.9% uptime during integration
- No feature freeze for partner-facing systems (growth cannot stop)

**OC2: Two Organizations, Different Cultures**
- USC and Wellhub have different working styles, values, decision-making
- Potential "us vs them" mentality
- Mitigation: Product Trio model, unified metrics

**OC3: Resource Constraints**
- Significant engineering capacity tied up on "keep lights on" during dual platform period
- Finance team bandwidth limited for reconciliation work
- Support team context-switching overhead

---

## Risks & Mitigation Strategies

### Comprehensive Risk Register (Phase 1 Focus)

| Risk | Impact | Mitigation Strategy | Early Warning Signal |
|------|--------|---------------------|---------------------|
| **Running dual platforms for 6+ months** | Operational overhead, significant eng capacity on "keep lights on", 2× incident surface | Hard deadline June 2027 (no extensions), stop onboarding to legacy after Phase 1, weekly cost tracking, feature freeze on legacy | Monthly cost tracking dashboard, engineering velocity metrics |
| **Data schema migration errors cause payout failures** | Partner churn if paid incorrectly, immediate trust loss, potential legal liability | Translation layer provides rollback path, dual-write validation, automated reconciliation checks, 100% payout calculation validation | Daily reconciliation dashboard, automated alerts if >0.1% variance, partner complaint tickets |
| **Partners resist migration to unified platform** | Low adoption, stuck on dual systems, missed cost savings, extended timeline | Product Trio model (joint decision authority), Germany MVP proves value first, phased rollout (can pause if issues), partner training program | Weekly adoption tracking, NPS surveys, support ticket volume and sentiment |
| **Germany MVP doesn't validate assumptions** | Wrong approach chosen, wasted 6 months, need to pivot, timeline slips | Controlled blast radius (1,000 partners), 1-month pilot results (fast feedback), clear success criteria defined upfront, rollback plan ready | Month 6 KR dashboard: <95% success = pause and iterate, >10 complaints = investigate |
| **Cross-org decision bottlenecks slow progress** | Roadmap slips, miss H2 2026 targets, team frustration, competing priorities | Product Trio weekly sync, <5 day decision SLA, disagree-and-commit culture, escalation path to leadership | Decision velocity tracking, blocker age in PM tool, sprint velocity metrics |
| **Payment infrastructure integration fails in key markets** | Can't roll out to certain countries, partner dissatisfaction, revenue loss in those markets | Integrate with all payment providers in Phase 1, validate multi-currency in Germany MVP, country-by-country rollout (can skip problematic markets) | Payment provider API health checks, transaction success rates by country, FX conversion validation |

---

### Strategic Risk Acceptance

**The Risk We're Accepting:** Running dual platforms for 9-12 months

**Cost:**
- Duplicate operational overhead
- Significant engineering capacity on "keep the lights on"
- 2× incident surface area
- Short-term complexity

**Why It's Worth It:**

**Alternative: Big Bang Migration**
- Too risky: Entire network impacted if issues arise
- No learning period: Can't validate assumptions first
- No rollback path: Stuck if migration fails
- **Cost of failure:** Significant partner churn and revenue loss

**Our Approach: Gradual Rollout**
- Safety net: Rollback capability if needed
- Real-world validation: Learn from early cohorts (Germany)
- Gradual risk exposure: Not all-in on Day 1
- Time to iterate: Fix issues before full deployment

**ROI Rationale:**
- Dual platform overhead is the cost of de-risking migration
- Avoids high-cost failure scenario
- Maintains growth targets during integration
- Partner trust takes years to rebuild

**Forcing Functions (Mitigation):**
- Hard deadline: December 31, 2027 (no extensions)
- Stop onboarding new partners to legacy after Phase 1
- Weekly cost tracking (escalate if exceeds budget)
- Feature freeze on legacy platforms (only critical bug fixes)

**Rollout Timeline:**
- H1 2026: 6% (Germany MVP)
- H2 2026: 40% (Phase 2 rollout)
- H1 2027: 100% (Legacy sunset)

---

## Organizational Requirements

### Team Structure

#### Product Trio (Strategic Decisions)
**Composition:** Staff PM + USC Partner Lead + Wellhub Partner Lead

**Responsibilities:**
- Joint decision authority (no unilateral decisions)
- Weekly alignment meetings
- Disagree and commit (data breaks ties)
- Transparent communication
- Escalation to leadership when needed

**Success Criteria:**
- <5 days proposal → decision
- <2 days blocker resolution
- 100% working groups include both orgs

---

#### Domain Working Groups (Execution)

**Payouts Working Group**
- **Members:** Finance + Ops from both USC and Wellhub
- **Scope:** Payout calculation, payment providers, reconciliation
- **Cadence:** Bi-weekly syncs

**Partner UX Working Group**
- **Members:** Product + Design from both USC and Wellhub
- **Scope:** Portal design, user research, CMS integration
- **Cadence:** Weekly syncs + design sprints

**Data Working Group**
- **Members:** Engineering + Data from both USC and Wellhub
- **Scope:** Schema design, translation layer, data migration
- **Cadence:** Daily standups (Phase 1), weekly (Phase 2+)

---

### Joint Discovery Workshops (Weeks 1-2)

**Format:** 2-day offsite with both Partner teams

**Objectives:**
- Surface pain points (anonymous voting)
- Identify best practices (steal the best from both)
- Build shared vision (co-create North Star)
- Establish trust (break down silos)

**Output:** Cross-functional working groups formed (USC + Wellhub paired)

---

### Communication Plan

#### Leadership Communication

**Three Key Messages for Phase 1:**

**Message 1: "We're solving what matters most to partners first: getting paid correctly"**
- Payouts = significant driver of partner churn
- Backend change validates approach before partner-facing work
- Data foundation enables all future phases

**Message 2: "We're testing with Germany first (controlled subset) before rolling out to everyone"**
- Germany pilot (1,000 partners) gives results in 30 days
- Can iterate quickly without impacting entire partner network
- Controlled blast radius if assumptions are wrong

**Message 3: "Growth will NOT be compromised - here's our insurance policy"**
- Parallel operations, zero feature freeze, 24-hour rollback plan
- Real-time monitoring: 99.9% uptime, payout accuracy, partner onboarding
- Safety net: Can revert to legacy systems instantly

---

#### Partner Communication

**Cadence:**
- Month 1: Initial announcement (integration coming, timeline, benefits)
- Month 5: Germany MVP cohort notified (1 month advance notice)
- Month 6: Germany MVP launch
- Month 7: Germany success story shared with all partners
- Month 8-9: Phased rollout communication (country-by-country)

**Channels:**
- Email (primary, 10+ languages)
- In-app notifications
- Webinars (live Q&A)
- Help center articles
- Partner newsletter

**Key Messages:**
- Zero disruption: Your portal access won't change until Phase 2
- Payment continuity: You'll continue getting paid on schedule
- Benefits coming: Unified analytics, better insights, single login
- Support available: Dedicated migration support team

---

### Unified Success Metrics (All Teams)

**Why:** Same metrics → Collaboration replaces competition

**Metrics:**
- Platform adoption: 90% partners on unified platform (by June 2027)
- Partner NPS: >50 (single score, not separate USC vs Wellhub)
- Operational efficiency: <100 support tickets per 1K partners
- Payout accuracy: 99.9% maintained
- Platform uptime: 99.9% maintained

---

## Success Criteria & KPIs

### Phase 1 (H1 2026) - Go/No-Go Criteria

**Go Criteria (Must achieve ALL to proceed to Phase 2):**
- ✅ Germany MVP: >95% automated migration success
- ✅ Payout accuracy: 100% match with legacy calculations
- ✅ Partner complaints: <10 support tickets from 1,000 partners
- ✅ Platform stability: 99.9% uptime maintained throughout Phase 1
- ✅ Organizational velocity: <5 days decision time, Product Trio functional
- ✅ Budget: Phase 1 spend within 10% of budget

**No-Go Triggers (Any ONE triggers pause/pivot):**
- ❌ Germany MVP: <95% success rate OR >10 complaints
- ❌ Payout accuracy: Any variance >0.1% OR partner payment failures
- ❌ Platform degradation: Uptime drops below 99.5%
- ❌ Partner resistance: NPS drops >10 points
- ❌ Critical bug: Severity 1 incident with no resolution path

**If No-Go Triggered:**
- Pause rollout immediately
- Root cause analysis (48 hours)
- Mitigation plan developed
- Product Trio + Leadership decision on path forward
- Options: Iterate and retry, pivot approach, or extend Phase 1

---

### Phase 2 & 3 Success Criteria
*(To be defined based on Phase 1 learnings)*

**Placeholder Criteria:**
- Phase 2: Portal NPS >60, 90%+ feature parity, CMS integration validated
- Phase 3: 90%+ adoption, cross-network booking live, legacy sunset complete

---

## Open Questions

### Strategic Questions
1. **What happens to partners who refuse to migrate?**
   - Force migration with sufficient notice period (60 days?)
   - Maintain legacy portal indefinitely for holdouts?
   - **Decision needed by:** Month 12 (before Phase 3 starts)

2. **How do we handle contract term harmonization?**
   - Honor all existing contracts (don't force renegotiation)?
   - Standardize at renewal?
   - **Decision needed by:** Month 1 (Legal + Finance alignment)

3. **What's the pricing model for cross-network access?**
   - Revenue share %? Same as single-network or different?
   - Who pays: USC, Wellhub, or split?
   - **Decision needed by:** Month 10 (before Phase 3 planning)

### Technical Questions
1. **Translation layer performance: What's acceptable latency?**
   - Target: <100ms overhead
   - **Decision needed by:** Month 2 (Architecture review)

2. **Data archival strategy: How long do we preserve legacy system data?**
   - Legal retention requirements?
   - Hot vs cold storage?
   - **Decision needed by:** Month 15 (before legacy sunset)

### Organizational Questions
1. **Post-integration team structure: What happens to duplicate roles?**
   - Partner Success team consolidation plan?
   - Engineering team reorganization?
   - **Decision needed by:** Month 6 (HR + Leadership alignment)

---

## Appendix

### A. Glossary

**Partner:** Fitness/wellness venue (gym, yoga studio, spa) in USC/Wellhub network

**Check-in:** When a member visits a partner location (tracked for payout calculation)

**Payout:** Payment made to partner for member check-ins/usage

**Translation Layer:** Unified API built on top of legacy databases (interim solution)

**Partner Parity:** Same partners visible in both USC and Wellhub networks

**Cross-Network Access:** USC members can book Wellhub partners (and vice versa)

**Product Trio:** Staff PM + USC Partner Lead + Wellhub Partner Lead (decision-making body)

---

### B. Reference Documents

**Case Study Materials:**
- [Staff Product Manager - Domain Agnostic - Case Study.pdf](Staff%20Product%20Manager%20-%20Domain%20Agnostic%20-%20Case%20Study.pdf)
- [USC-Wellhub PMI Presentation (USC.pdf)](USC.pdf)
- [Comprehensive Dependency Mapping (CSV)](comprehensive-dependency-mapping-all-phases.csv)
- [PMI Integration Strategy](pmi-integration-strategy.md)

**GitHub Repository:**
- [https://github.com/cristiano-san/pmi](https://github.com/cristiano-san/pmi)

---

### C. Revision History

| Date | Version | Author | Changes |
|------|---------|--------|---------|
| Dec 2025 | 1.0 | Cristiano Menezes dos Santos | Initial PRD created from presentation |

---

### D. Approvals

| Role | Name | Approval Date | Signature |
|------|------|---------------|-----------|
| Product (Staff PM) | Cristiano Menezes dos Santos | Pending | |
| Engineering Lead | [TBD] | Pending | |
| Finance Lead | [TBD] | Pending | |
| Legal Lead | [TBD] | Pending | |
| Operations Lead | [TBD] | Pending | |

---

**END OF DOCUMENT**

---

## Document Metadata
- **Total Length:** ~15,000 words<br>
- **Estimated Reading Time:** 45-60 minutes<br>
- **Target Audience:** Product, Engineering, Finance, Operations, Legal, Leadership<br>
- **Document Type:** Product Requirements Document (PRD)<br>
- **Status:** Draft for Case Study Presentation<br>
- **Next Review:** After Phase 1 Discovery (Month 1)<br>
