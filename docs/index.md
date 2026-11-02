# Best Time to Buy and Sell Stock: One Pattern for the Whole Family

The stock problems show up in almost every coding interview loop. They look like six different questions, but they share one idea: track the best state you can be in on each day.

## Version I: one transaction

Walk the prices once. Keep the lowest price seen so far and the best profit `price - minPrice`. O(n) time, O(1) space.

## Version II: unlimited transactions

Add every positive day-to-day difference. Any rising run can be split into one-day trades with the same total, so the greedy sum is optimal.

## Version III and IV: at most k transactions

Keep `buy[j]` and `sell[j]` for each transaction count j. On each day, `buy[j] = max(buy[j], sell[j-1] - price)` and `sell[j] = max(sell[j], buy[j] + price)`. With k = 2 that is four variables.

## Cooldown and fees

Add a state. With a cooldown you keep `hold`, `sold`, and `rest`; with a fee you subtract it when you sell. The loop stays the same.

## How to present it

Start with version I, name the state you are tracking, and then show how each variant only adds a state or a rule. Interviewers like hearing that you see the shared structure. I rehearse explaining state machines like this with [Linkjob AI copilot](https://www.linkjob.ai/).

*Disclosure: I work on Linkjob AI.*
