# Rollback Plan: Swiggy Late Delivery Features

## When to Rollback (Triggers)

### Automatic Rollback (System detects)

| Metric | Threshold | Action |
|--------|-----------|--------|
| On-time delivery rate | Drops >3% in any 15 min | Auto-rollback entire feature |
| Error rate (API) | >5% for 2 min | Auto-rollback affected service |
| Order volume | Drops >10% in 5 min | Auto-rollback + page on-call |
| Customer cancellation rate | >5% in 1 hour | Disable auto-coupons only |

### Manual Rollback (PM/Engineer decides)

| Metric | Threshold | Decision Time |
|--------|-----------|---------------|
| Rider churn | >15% in 24 hours | 10 minutes |
| Restaurant rejection rate | >8% in 6 hours | 30 minutes |
| Support tickets | >50% increase in 1 hour | 15 minutes |
| Negative social media sentiment | 10+ complaints/minute | 5 minutes |
| Customer complaint (VIP) | CEO tweet or email | Immediate |

---

## Rollback Procedures

### Level 1: Feature Flag Rollback (1 minute)

**What:** Turn off individual features  
**When:** Single feature causing issues  
**Who:** On-call engineer

```bash
# LaunchDarkly command
feature_flag: swiggy.delay_features.auto_reassign = OFF
feature_flag: swiggy.delay_features.proactive_comms = OFF
feature_flag: swiggy.delay_features.restaurant_scoring = OFF
