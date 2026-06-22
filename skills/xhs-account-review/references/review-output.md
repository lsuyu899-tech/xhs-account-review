# Review output

Use this structure. Create a standalone HTML report by default. Keep it readable without external fonts, scripts, CDNs, or a web server. Attach an analysis workbook only when the user requests one or when it materially improves auditability.

Design the HTML for a non-analyst reader:

- Start with a direct, neutral statement of the account's current state in one or two sentences. Avoid second-person language so the report can be shared externally.
- Show the account signal chain visually, but label account-level data that is not a strict same-user funnel.
- Explain metrics beside the values and conclusions where they are used. Do not create a standalone “how to read metrics” tutorial unless the user requests one.
- Use plain-language status labels such as “能吸引点击”, “点进来后没动作”, and “还没形成关注理由”.
- Put evidence immediately under each conclusion.
- Make the next actions sequential, specific, and testable.
- Keep technical formulas in a collapsible or secondary section.
- Include the maturity formula near the top: `export timestamp - publish timestamp`. Define `<48h` as too early, `48–72h` as observing, and `≥72h` as mature. State that maturity measures review readiness, not content quality.
- Replace unclear multi-metric charts with direct content decisions such as continue, adjust, pause, and retest. Use a chart only when its takeaway is immediately obvious without teaching the reader how to decode it.

## 1. One-sentence conclusion

State the primary bottleneck and the strongest evidence.

Example shape: “The main problem is entry rather than content depth: exposure is typical, but median cover CTR sits in the account's bottom band, while save rate after viewing is normal.”

## 2. Data scope

- Source file and sheet.
- Export or snapshot date if known.
- Raw rows, excluded rows, analyzed rows.
- Date range and post-age rule.
- Missing fields and their effect on confidence.

## 3. Account baseline and metric meaning

For every displayed metric, explain what user behavior it represents and what the current value says in this account before showing technical formulas or percentile bands.

Report medians and P25–P75 bands for available funnel metrics. Do not use the mean alone.

| Stage | Metric | Median | P25–P75 | Judgment |
|---|---|---:|---:|---|
| Distribution | Exposure | | | |
| Entry | Cover CTR or view rate | | | |
| Response | Save, comment, share, deep engagement rates | | | |
| Conversion | Follows per 1,000 views | | | |

## 4. Funnel diagnosis

For each stage, state whether it is the main bottleneck, a secondary issue, healthy, or unknown. Cite exact post rows or titles.

## 5. Winner and loser comparison

Use two or three matched comparisons where possible.

| Comparison | Evidence | Supported interpretation | Confidence |
|---|---|---|---|
| Winner A vs similar weak post B | | | |

Avoid comparing unrelated topics and calling every difference causal.

## 6. Ranked causes

For each of the top three causes:

1. Cause or hypothesis.
2. Evidence.
3. Alternative explanation.
4. Confidence.
5. Test that would resolve uncertainty.

## 7. Decisions

- Keep: verified elements worth continuing.
- Stop: patterns with repeated weak evidence or practices that obscure learning.
- Test: uncertain but promising variables.

## 8. Next five-post experiment

Change one main variable per experiment. Keep topic, format, or posting conditions as comparable as practical.

| Post | Hypothesis | Variable changed | Control held stable | Success metric | Review time |
|---|---|---|---|---|---|
| 1 | | | | | 3 or 7 days |

Do not promise a viral outcome. Define success relative to the account baseline, such as exceeding the current median or moving from below P25 into the typical band.

## 9. Next review

Specify:

- When to export again.
- Which fields must be retained.
- Which annotations to add.
- What would confirm or reject each major hypothesis.
