# Rollout Strategy: Phased Launch by City

## Phase 0: Internal Testing (Week 0)
- **Traffic:** 0.1% (Swiggy employees only)
- **Goal:** Catch bugs before real users
- **Success:** 95% of flows work

---

## Phase 1: Bangalore Pilot (Week 1)
- **Traffic:** 2% of Bangalore orders
- **Duration:** 7 days
- **Cities:** Bangalore only

**Success Criteria (Go/No-Go for Phase 2):**
- [ ] On-time rate >90% (was 88%)
- [ ] Support tickets ↓20%
- [ ] Rider reassign rate <8%
- [ ] No critical bugs (P0/P1)

**Monitoring:**
- Real-time dashboard (refreshes every 5 min)
- On-call engineer 24/7
- Daily 10 AM sync

---

## Phase 2: Bangalore Full (Week 2)
- **Traffic:** 100% of Bangalore
- **Duration:** 7 days

**Success Criteria (Go/No-Go for Phase 3):**
- [ ] On-time rate >92%
- [ ] Customer cancellation rate <3%
- [ ] Rider churn <10%
- [ ] Restaurant rejection rate <5%

---

## Phase 3: Top 5 Cities (Week 3-4)
- **Cities:** Delhi, Mumbai, Pune, Hyderabad, Chennai
- **Traffic:** 10% → 50% → 100% (ramp over 10 days)

**Order:**
1. Delhi (Day 1, 10%)
2. Mumbai (Day 2, 10%)
3. Pune + Hyderabad (Day 4, 25%)
4. Chennai (Day 6, 50%)
5. All at 100% (Day 10)

---

## Phase 4: Nationwide (Week 5+)
- **Cities:** All 50+ cities
- **Traffic:** 10% for 2 days → 100%

**Holdouts (control cities):**
- Keep 2 cities on old system for 30 days
- Compare: on-time rate, support tickets, retention

---

## Feature Flags Configuration

| City | Phase | Flag Status |
|------|-------|-------------|
| Bangalore | Phase 2 | `swiggy.delay_features = ON` |
| Delhi | Phase 3 | `swiggy.delay_features = 0.5` (50%) |
| Mumbai | Phase 3 | `swiggy.delay_features = 0.1` (10%) |
| Others | Phase 4 | `swiggy.delay_features = OFF` |

---

## Communication Plan

| Audience | When | Channel |
|----------|------|---------|
| Customers | Before launch | Email + Push (opt-out available) |
| Riders | Before launch | In-app notification + ₹15 incentive highlight |
| Restaurants | At launch | Email + Dashboard banner |
| Support team | Week 0 | Training session + updated playbook |
