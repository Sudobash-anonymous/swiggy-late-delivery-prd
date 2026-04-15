# Root Cause Analysis: Late Deliveries on Swiggy

## Methodology
- Analyzed 50,000 orders from Bangalore (Dec 2024)
- 15 user interviews (customers)
- 10 rider interviews
- 8 restaurant partner interviews

## Data Breakdown

| Root Cause | % | Explanation |
|------------|---|-------------|
| Restaurant prep delay | 42% | Restaurant marks "ready" but takes 8-15 min extra |
| No rider nearby | 23% | Peak hours (1-2 PM, 8-9 PM) |
| Multi-order batching | 18% | Rider takes 2-3 orders → last customer waits |
| Traffic | 12% | ETA model underestimates by 5-8 min |
| Rider cancellation | 5% | Rider cancels after reaching restaurant |

## Customer Quotes

> *"I stopped ordering from Swiggy for dinner. It's always 20 min late and cold."* — Priya, 35

> *"I don't mind waiting if you just tell me honestly. Don't say 8:15 when you know it's 8:30."* — Rahul, 28

## Rider Quotes

> *"Why should I get penalized when Burger King takes 15 min to make the biryani?"* — Rider, Bangalore

> *"I'd take more orders if you paid ₹10 extra for every delayed pickup."* — Rider, Delhi

## Restaurant Quotes

> *"We can't control Zomato/Swiggy during rush hour. Every order takes longer."* — Restaurant owner, Koramangala

## Key Insights
1. **Trust gap:** Customers don't trust ETA
2. **Incentive misalignment:** No downside for restaurants to be late
3. **Rider friction:** Penalized for things outside their control
