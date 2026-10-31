# Plain Claude vs /think, same question

Both answers are real runs on the same model, in clean sessions with no personal context.
Only Claude Code's own session-end notes were removed.

> We spent 6 months building a feature our biggest customer asked for, and they just churned. It's 80% done. Should we finish it?

## Plain

**Ignore the 6 months.** You've spent them whether you finish or not, so they shouldn't count. The only question that matters: *if someone offered you this half-built feature for free today, would you spend the remaining effort to ship it?*

Here's how I'd answer that.

## 1. Get an honest estimate of the remaining 20%
"80% done" usually means the demo works. Edge cases, migrations, permissions, docs, QA and support readiness often take as long as everything before them. Ask the team for a real number, then double it. If the answer is another 3+ months, that changes things.

## 2. Check whether anyone else actually wants it
This question decides it. Look for evidence, not guesses:
- How many other customers or prospects have asked for this, unprompted?
- Does it show up in lost-deal notes or support tickets?
- Show the current build to 5–10 customers this week. Do they lean in, or just nod politely?

If the feature only fit that one customer's workflow, finishing it means taking on maintenance cost for no buyer.

## 3. Find out why they churned
- **They left because it was late:** the need is probably real. Others may share it, and you've learned your delivery speed is a problem.
- **They left for unrelated reasons** (budget, acquisition, new leadership): the feature might still be good, or it might always have been a custom request. Go back to step 2.
- **They left because the feature wasn't what they wanted:** that's a strong sign to stop.

## 4. Look for options between finishing and abandoning
- **Ship a smaller slice:** release the most broadly useful part and cut the custom parts.
- **Pause it properly:** document the work, keep the branch, and pick it up when a second customer asks.
- **Salvage the pieces:** infrastructure built for it (APIs, data models) may help other parts of the roadmap even if the feature dies.

## My default
**Pause unless you can name 3+ other customers who want it.** If you can, finish it, probably in a smaller form. If you can't, pausing it costs you nothing more, while finishing it costs months that could go to things customers are asking for now.

The bigger lesson is upstream: spending 6 months on one customer's request without checking demand elsewhere, or getting a contract commitment, is the habit to fix. Before your next big custom build, ask for a signed commitment or pre-payment.

If you share how many other customers have asked for this, the honest remaining estimate and what you know about the churn, I can help you make the call.

## /think

**Call:** Don't finish it by default. Freeze it, and spend 2–3 weeks finding out whether any other customer wants it. Only finish it if at least one of them commits to it.

**Why:**
- **Sunk cost:** Ask whether you'd start this feature today if you had built none of it. With the customer who asked for it gone, the answer is probably no. That means "80% done" is the only argument left, and how far you've come says nothing about what the feature is worth now. The remaining 20% also tends to be the slowest part: polish, edge cases, docs. After that you'd be maintaining it for good.
- **Opportunity cost:** It's not a choice between finishing and wasting the work. Engineers are the scarce thing here, and the weeks spent finishing this are weeks not spent on whatever might have kept your biggest customer from leaving. That's worth understanding before you build anything else. There are also options besides finish or scrap: ship a cut-down version, offer it to one design partner, or mothball the branch.
- **Sampling:** All the demand evidence came from one customer, and it was a request, not a commitment to pay. That customer has now left, which counts against the feature, not for it.
- **The Mom Test:** Don't ask other customers "would you use X?" Ask them how they handle this problem today and what their workaround costs them.
- **Tension:** Sunk cost says scrap it, and opportunity cost says move the team elsewhere. Sampling and the Mom Test say neither until you've checked. Checking costs a few weeks and the 80% loses nothing while frozen, so check first.

**Next:** This week, do Mom Test interviews with your top 5–8 accounts, and ask the churned customer directly why they left.

**Change course if:** Two or more customers make a real commitment (a pilot, a contract term, or a renewal tied to the feature). Then finish the smallest version that serves them. If you also learn the churn happened because this feature was late, its value goes up, but only for customers who actually have the same problem.

## What changed

- **It catches the trap.** All the evidence for the feature came from one customer, who has now left. Plain treats the churn as a branch to investigate; `/think` (via *sampling*) counts it as evidence against.
- **It commits.** Plain ends by asking for more information. `/think` gives a call, a next step this week, and the signal that would reverse it.
- **It says what counts.** "Would you use X?" answers don't count; a pilot, a contract term or a renewal does (*the Mom Test*).
- **It's shorter.** About 360 words against 440.

On some questions the two answers converge (a raise-vs-equity question produced the same break-even math both ways). The gap is widest when the question hides a bad assumption.
