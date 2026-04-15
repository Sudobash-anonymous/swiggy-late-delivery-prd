# Assumptions & Risks: Swiggy Late Delivery Project

## Critical Assumptions (If wrong, project fails)

| # | Assumption | Validation Method | Confidence |
|---|------------|-------------------|------------|
| 1 | 10% of late deliveries are unavoidable | Historical data analysis | High |
| 2 | Restaurants will respond to commission incentives (95+ = -2%) | Survey 50 restaurants | Medium |
| 3 | Riders will accept rescue orders with +₹15 incentive | A/B test incentive amount | High |
| 4 | Customers want proactive notifications (not spam) | User interviews (n=15) | High |
| 5 | Support tickets will drop 40% with auto-coupons | Bangalore pilot | Medium |

---

## Product Assumptions

### Customer Behavior
| Assumption | Risk Level | Mitigation |
|------------|------------|-------------|
| Customers will read delay notifications | Medium | A/B test notification copy |
| ₹25 coupon is sufficient to reduce anger | Medium | A/B test ₹20 vs ₹30 vs ₹40 |
| Customers won't abuse cancel-on-delay | Low | Limit 3x/month |
| Customers trust new ETA confidence indicator | Medium | Show accuracy rate (e.g., "95% confident") |

### Rider Behavior
| Assumption | Risk Level | Mitigation |
|------------|------------|-------------|
| Riders won't game "traffic" report | High | Flag riders with >50% traffic reports |
| +₹15 rescue fee is enough incentive | Low | Test +₹10, +₹15, +₹20 |
| Riders won't intentionally delay for rescue fee | Medium | Limit rescue orders to 2/day per rider |
| Auto-reassign won't increase rider churn | Medium | Monitor churn daily in pilot |

### Restaurant Behavior
| Assumption | Risk Level | Mitigation |
|------------|------------|-------------|
| Restaurants will report accurate prep time | High | Cross-check vs historical + mystery shopping |
| Commission penalty (3%) is meaningful | Medium | Survey restaurants on sensitivity |
| Restaurants won't reject more orders | Low | Monitor rejection rate as counter-metric |
| Small restaurants (<100 orders/month) will care | Medium | Segment by order volume |

---

## Technical Assumptions

| Assumption | Risk | Mitigation |
|------------|------|-------------|
| Real-time traffic data is accurate within 2 min | Medium | Use 2 data sources (Google + in-house) |
| ML model can predict prep time per dish | High | Start simple (historical avg per restaurant) |
| Database can handle 2x write volume | Low | Load test before launch |
| Feature flags work across 50 cities | Medium | Test in staging with 100 cities |

---

## Business Assumptions

| Assumption | Risk | Mitigation |
|------------|------|-------------|
| ₹48Cr annual impact is accurate | Medium | Recalculate with pilot data |
| 94% on-time target is achievable | Medium | Phased targets: 92% → 94% |
| Competitors (Zomato) won't copy instantly | Low | Patent? (unlikely) — move fast |
| No regulatory issues with auto-coupons | Low | Legal review before launch |

---

## Risks & Mitigation

### High Probability / High Impact (Critical)

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Riders fake "traffic" to avoid penalty | High | High | ML model to detect fake reports + manual audit |
| Restaurants inflate prep time to improve score | Medium | High | Compare vs historical + random audits |
| Customers cancel more (free cancellation) | Medium | Medium | Limit 3 free cancels/month |

### Medium Probability / High Impact

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Auto-reassign increases rider churn | Medium | High | Pilot in 1 city first, monitor daily |
| Commission penalty drives restaurants off platform | Low | High | Start with 1% penalty, not 3% |
| Notification spam → customers mute all Swiggy | Low | Medium | Allow opt-out per notification type |

### Low Probability / High Impact

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| System outage during peak hour | Low | Very High | Canary deployment + auto-rollback |
| Negative press ("Swiggy penalizes small restaurants") | Low | High | Proactive comms + PR plan |

---

## Validation Plan

### Week 0 (Before Building)
- [ ] Survey 50 restaurants on commission sensitivity
- [ ] Interview 20 riders on rescue fee amount
- [ ] A/B test notification copy with 10,000 users
- [ ] Analyze 6 months of historical late delivery data

### Week 1-2 (During Build)
- [ ] Load test API endpoints (10x expected traffic)
- [ ] Usability test wireframes with 5 customers
- [ ] Shadow 5 support agents to understand workflow

### Week 3-4 (Pilot)
- [ ] Measure all assumptions against real data
- [ ] Pause if any critical assumption fails

---

## Unknowns (To Be Discovered)

| Question | How to Answer |
|----------|---------------|
| What's the optimal coupon value? | A/B test ₹20, ₹30, ₹40 |
| Do customers prefer push or email for delay? | A/B test channel |
| Will riders accept rescue orders at night? | Pilot in Bangalore 10 PM - 2 AM |
| Do restaurants need human coaching to improve? | Test automated tips vs human call |
| What's the elasticity of commission penalty? | Test 1%, 2%, 3% |
