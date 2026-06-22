---
name: xhs-account-review
description: Analyze manually exported Xiaohongshu Creator Center post data and produce a plain-language, standalone HTML account review. Use when the user provides or plans to provide CSV, XLSX, XLS, or TSV data and asks about the account's current state, why recent image posts performed poorly, what each metric means, which posts worked, where the exposure-to-follow funnel is blocked, or what to do next. Produce evidence-backed conclusions without logging in, scraping Xiaohongshu, reading cookies, publishing, or operating the account.
---

# Xiaohongshu Account Review

Turn exported post data into a review that separates observed facts, supported interpretations, hypotheses, and next experiments. Diagnose the account against its own baseline; do not rely on generic industry benchmarks.

## Boundaries

- Use only files and screenshots the user supplies.
- Never request cookies, tokens, browser sessions, or account credentials.
- Never log in, scrape, publish, comment, like, or modify the account.
- Keep the source export unchanged. Perform calculations in a new table, sheet, or temporary structure.
- Do not claim shadow banning, account-weight changes, or algorithm punishment from ordinary performance data.

## Workflow

### 1. Inspect the export

Read [references/input-schema.md](references/input-schema.md) completely. Identify sheets, row count, date coverage, field mappings, missing values, duplicates, and immature posts.

If the input is a spreadsheet, use the Spreadsheets skill to inspect and calculate. Preserve numeric and date types. Do not overwrite the original workbook unless explicitly requested.

Proceed with partial data when possible:

- With exposure and views, diagnose distribution and cover entry.
- With views and interactions, diagnose content response and conversion.
- With only public likes, comments, and saves, limit conclusions to relative public engagement.
- If title, cover, topic, or format annotations are absent, locate the funnel bottleneck but label creative explanations as hypotheses.

Default to posts at least 3 full days old. If data contains posts with substantially different ages, compare a common observation window when available; otherwise flag cumulative-age bias.

### 2. Normalize and calculate

Read [references/metrics-and-diagnosis.md](references/metrics-and-diagnosis.md) completely.

Calculate only when the denominator is present and greater than zero. Leave unavailable rates blank rather than converting them to zero.

Use account-relative baselines:

- Median for the typical post.
- P25 and P75 for weak and strong bands.
- Top and bottom 20% for pattern comparison when at least 10 mature posts exist.
- Require at least 3 posts in a category before treating a format, topic, weekday, or time bucket as a pattern. Otherwise call it a hypothesis.

Do not collapse all metrics into an arbitrary composite score. Preserve the funnel stages so the user can see where performance breaks.

### 3. Diagnose the funnel

Analyze in this order:

1. Exposure: did the post receive distribution?
2. Entry: did the title and cover convert exposure into views?
3. Response: did the content earn likes, comments, saves, and shares?
4. Conversion: did the post convert viewers into followers?
5. Repeatability: do winning topics, formats, hooks, or structures recur?

Compare each weak post with a stronger post that is similar in topic, format, or posting period. Prefer matched comparisons over comparing unrelated extremes.

For every diagnosis, write:

- Evidence: the exact rows and metrics.
- Interpretation: what the data directly supports.
- Confidence: high, medium, or low.
- Alternative explanation: the strongest plausible competing cause.
- Test: the smallest next-post experiment that can distinguish them.

### 4. Produce the review

Follow [references/review-output.md](references/review-output.md). Lead with the main bottleneck, not a long metric dump.

Default to a standalone local HTML report as the primary reading experience. Make it responsive, dependency-free, and usable by opening the file directly. Treat any spreadsheet as an optional audit attachment, not the main explanation.

Always include:

- Data scope and quality limitations.
- Account baseline using medians.
- Funnel diagnosis with evidence.
- Two or three repeatable winner/loser patterns.
- The three highest-priority causes, ranked.
- A keep / stop / test decision list.
- A controlled plan for the next 5 posts, changing one main variable per test.
- Metrics and review timing for the next cycle.

Explain every displayed metric in ordinary language: what it represents, which stage it diagnoses, and how the current value should be interpreted. Translate rates into natural examples such as “about 12 views per 100 exposures” when that improves comprehension.

Write the report for sharing with third parties. Use neutral account-level language instead of addressing the reader as “you.” Open with the direct current-state judgment. Show the maturity formula and the `<48h / 48–72h / ≥72h` bands near the top. Integrate metric explanations into the relevant findings; do not add a standalone metric tutorial unless requested. Prefer explicit continue / adjust / pause decisions over comparison charts that require interpretation.

When evidence is insufficient, say what the data can establish and what additional field, screenshot, or annotation would resolve the uncertainty. Do not fill gaps with platform folklore.

## Quality checks

- Reconcile row counts before and after filtering.
- Scan formulas for division errors and percentage scaling mistakes.
- Distinguish raw counts from rates and official platform rates from derived rates.
- Check whether one outlier dominates the average; prefer the median.
- Do not infer timing effects from one post in a time bucket.
- Ensure every recommended action traces to evidence or is explicitly marked as a hypothesis.
