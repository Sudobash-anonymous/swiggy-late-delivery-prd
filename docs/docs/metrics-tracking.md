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
