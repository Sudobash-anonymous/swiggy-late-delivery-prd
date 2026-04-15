# Metrics Tracking Dashboard: Late Delivery Reduction

## North Star Metric
**On-time delivery rate** (delivered within ±5 min of ETA)

| Timeframe | Current | Target | Status |
|-----------|---------|--------|--------|
| Weekly | 88% | 94% | 🟡 Behind |
| Monthly | 87.5% | 94% | 🟡 Behind |
| Quarterly | 88.2% | 94% | 🟡 Behind |

---

## Secondary Metrics (Monitor Daily)

### Customer Metrics

| Metric | Current | Target | Alert Threshold |
|--------|---------|--------|-----------------|
| Avg customer wait time (min) | 42 | 35 | >45 min |
| Late order refund rate | 8% | 4% | >10% |
| Customer retention (after 1 late) | 68% | 78% | <65% |
| Customer retention (after 2+ late) | 52% | 65% | <48% |
| Support tickets (delivery-related) | 12k/day | 6k/day | >10k/day |
| Customer cancellation rate | 2.1% | <3% | >3.5% |
| CSAT score (delivery experience) | 4.1/5 | 4.5/5 | <3.8 |

### Rider Metrics

| Metric | Current | Target | Alert Threshold |
|--------|---------|--------|-----------------|
| Rider earnings (₹/hour) | ₹180 | ₹210 | <₹170 |
| Rider churn (weekly) | 8% | <10% | >12% |
| Avg pickup wait time (min) | 8 | 5 | >10 min |
| Rider reassign rate | N/A | <5% | >8% |
| Rider utilization (%) | 68% | 75% | <60% |
| Rider NPS | 32 | 50 | <25 |

### Restaurant Metrics

| Metric | Current | Target | Alert Threshold |
|--------|---------|--------|-----------------|
| Prep delay rate | 42% | 25% | >35% |
| Prep accuracy score (avg) | 71 | 85 | <65 |
| Restaurant rejection rate | 1.2% | <5% | >6% |
| Restaurant NPS | 28 | 45 | <20 |

---

## Counter-Metrics (Guardrails)

| Metric | Warning | Critical | Action |
|--------|---------|----------|--------|
| Rider churn | >10% | >15% | Pause auto-reassign |
| Restaurant rejection | >5% | >8% | Pause commission penalties |
| Customer cancellation | >3% | >5% | Disable auto-coupons |
| Order volume drop | >5% | >10% | Rollback entire feature |

---

## Dashboard Design (Mock)
┌─────────────────────────────────────────────────────────────────┐
│ SWIGGY DELIVERY OPS DASHBOARD Last 24h ▼ │
├─────────────────────────────────────────────────────────────────┤
│ │
│ ┌────────────┐ ┌────────────┐ ┌────────────┐ ┌────────────┐ │
│ │ 88% │ │ 42 min │ │ 12,847 │ │ ₹48Cr │ │
│ │ On-time │ │ Wait avg │ │ Late │ │ Annual │ │
│ │ ▲ +0.5% │ │ ▼ -2 min │ │ orders │ │ impact │ │
│ └────────────┘ └────────────┘ └────────────┘ └────────────┘ │
│ │
│ Late Orders by Root Cause (Last 7 days) │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ Restaurant ████████████████████ 42% ▲ +2% │ │
│ │ No rider ████████████ 23% ▼ -1% │ │
│ │ Batching █████████ 18% ▼ -3% │ │
│ │ Traffic ██████ 12% → 0% │ │
│ │ Rider ██ 5% ▼ -1% │ │
│ └─────────────────────────────────────────────────────────┘ │
│ │
│ Real-time Alerts │
│ ┌─────────────────────────────────────────────────────────┐ │
│ │ 🟡 Bangalore: Prep delay rate ↑ 45% (above 35% alert) │ │
│ │ 🟢 Delhi: On-time rate 91% (above target) │ │
│ │ 🔴 Mumbai: Rider churn 14% (critical) → Page engineer │ │
│ └─────────────────────────────────────────────────────────┘ │



---

## Alert Configuration

| Severity | Color | Response Time | Action |
|----------|-------|---------------|--------|
| Critical | 🔴 Red | 5 min | Page on-call engineer + PM |
| Warning | 🟡 Yellow | 30 min | Slack alert to team |
| Info | 🔵 Blue | 2 hours | Log for daily review |

---

## Weekly Business Review (WBR) Template

**Every Monday, 10 AM**

### Section 1: Last Week's Performance
- On-time rate: ___ (↑/↓ vs target)
- Top 3 root causes: ___, ___, ___
- Biggest win: ___
- Biggest miss: ___

### Section 2: Experiment Results
- A/B test name: ___
- Result: ___ (significant / not significant)
- Action: (ship / iterate / kill)

### Section 3: This Week's Focus
- Priority 1: ___
- Priority 2: ___
- Risk to watch: ___

### Section 4: Customer Feedback (Top 3 complaints)
1. ___
2. ___
3. ___
