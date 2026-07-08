# Research Question Framing

**Project Lane:** Customer Churn Prediction (Core Lane)

## Research Question
Can we use a company's past customer data to figure out which customers are likely to cancel their subscription soon, so the company can try to keep them before they actually leave?

## Why This Question Matters
It's usually cheaper for a company to keep a customer than to find a new one. So if we can spot the customers who might leave *before* they actually cancel, the company has a chance to step in and try to change their mind — maybe with a discount, a phone call, or better support. That's basically the whole point of this project: catch the warning signs early enough that something can actually be done about it.

## Unit of Analysis
Each row in the dataset is one customer. It includes things like their basic info (demographics), what plan/contract they're on, how much they use the service, their billing/payment history, and any support tickets or interactions they've had. Each customer also has a label saying whether they churned (left) or not.

## Expected Output
The model will give us:
- A **probability** for each customer (like "this customer has a 72% chance of churning").
- A simple **yes/no prediction** — Likely to Churn or Not Likely to Churn.
- Ideally, a **ranked list**, so the company can start with the riskiest customers first if they don't have time/budget to reach out to everyone.

This is meant to help the team make a decision, not make the decision for them. The model isn't always right, so it's more like a heads-up than a guarantee.

## Decision Supported
This helps the customer support/marketing team figure out **who to focus on first** when trying to retain customers, since they probably don't have time or budget to reach out to every single customer.

## Possible Actions
Depending on what the model predicts, the company could:
- Reach out to high-risk customers directly.
- Offer a discount or a better plan.
- Give them more personalized/priority support.
- Look at why people are churning and try to fix that issue for everyone.

At the end of the day, a real person still decides what to actually do — the model is just pointing out who might need attention.

## Cost of Wrong Recommendations
No model is perfect, so it helps to think about what happens when it gets things wrong:

**False Positive** — the model says a customer will churn, but they were actually going to stay.
- Ends up wasting money on discounts/offers they didn't need.
- Wastes the support team's time and effort.

**False Negative** — the model says a customer is fine, but they actually leave.
- The company loses that customer's revenue.
- No chance to try and save them because nobody knew to reach out.

Honestly, a false negative is probably worse for the business than a false positive, since losing a customer completely is a bigger loss than accidentally giving someone an unnecessary discount. That's something to keep in mind when picking how the model makes its final yes/no decision.

## Why Data and Machine Learning Can Help
There are a lot of things that might make someone churn — how much they use the service, what kind of contract they have, past support problems, how long they've been a customer, etc. It's hard to write simple "if this, then that" rules for something this complicated, but a machine learning model can look at a lot of past examples and learn the patterns on its own. It won't be perfect, but it can help narrow down who to focus on instead of guessing.

## How I'll Know If the Model Is Actually Useful
Just checking "accuracy" isn't really enough here, since it's not that useful to know if the model is right overall — what matters more is whether it's actually catching the right people. So I'll also look at:
- **Precision and recall** — since missing an actual churner (false negative) seems worse than a false alarm, recall probably matters a bit more here.
- **How good the ranking is** — if I sort customers by risk score, are the "high risk" ones actually leaving more often than the rest? That matters more than the exact cutoff point.

## Limitations
- The model is just giving probabilities, so it will be wrong sometimes in both directions.
- Past data might not represent future customers well — things change (pricing, competitors, customer expectations).
- If the company already gave discounts to certain customers in the past, that could bias the data in ways that are hard to catch.
- This should be used along with human judgement, not instead of it. The model doesn't know things that aren't in the data.

## Provisional Lane
This project is proposed under the Customer Churn Prediction core lane. This might change a bit depending on feedback in the first few weeks of the capstone.
