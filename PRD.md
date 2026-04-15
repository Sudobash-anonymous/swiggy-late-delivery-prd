# PRODUCT REQUIREMENT DOCUMENT (PRD)
## Improve Swiggy Late Deliveries

| **Document Owner** | [Your Name] |
| **Version** | 2.0 |
| **Last Updated** | [Current Date] |
| **Status** | Draft → Review |

---

## 1. EXECUTIVE SUMMARY

Swiggy currently delivers **88% of orders on time** (within ±5 min of ETA). The remaining 12% (≈1.2M orders/month) are late, causing:

- **₹48 Cr annual refund/payout impact**
- **15% lower repeat rate** after 2+ late deliveries
- **32% of support tickets** → delivery complaints

This PRD proposes **3 P0 features** to reduce late deliveries to **94%** in 3 months.

---

## 2. PROBLEM DEEP DIVE

### Root Cause Analysis

| Root Cause | % of Late Orders | Fix Complexity |
|------------|------------------|----------------|
| Restaurant prep delay | 42% | Medium |
| Rider assignment gap | 23% | High |
| Multi-order batching | 18% | High |
| Traffic / weather | 12% | Low |
| Rider cancellation | 5% | Low |

### User Personas Affected

| Persona | Pain Point |
|---------|------------|
| **Rahul (IT pro, 28)** | Orders lunch for team → late = awkward silence in meeting |
| **Priya (working mom, 35)** | Dinner for kids → late = cranky children |
| **College student** | 2 AM order → late = hostel gate closes |

---

## 3. SUCCESS METRICS

### Primary Metric (North Star)

| Metric | Current | Target (Q1) | Target (Q2) |
|--------|---------|-------------|-------------|
| On-time delivery rate | 88% | 92% | 94% |

### Secondary Metrics

| Metric | Current | Target |
|--------|---------|--------|
| Customer wait time (avg) | 42 min | 35 min |
| Late order refund rate | 8% | 4% |
| Rider earnings (₹/hour) | ₹180 | ₹210 |
| Support tickets (delivery) | 32% | 18% |

### Counter-Metrics (Guardrails)

| Metric | Warning Threshold |
|--------|-------------------|
| Restaurant rejection rate | >5% increase |
| Rider churn (weekly) | >10% increase |
| Customer cancellation rate | >3% increase |

---

## 4. SOLUTION ROADMAP

### P0 (MVP — Ship in 2 weeks)

#### Feature 4.1: Proactive Delay Communication

**What it does:**
- Restaurant delay ≥5 min → auto-push notification
- Customer gets: ₹25 coupon + new ETA

**User Flow:**
