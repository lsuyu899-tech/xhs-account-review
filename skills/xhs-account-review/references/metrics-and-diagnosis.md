# Metrics and diagnosis

## Derived metrics

Use the platform-provided value when it clearly represents the same metric. Otherwise derive:

| Metric | Formula | Funnel meaning |
|---|---|---|
| View rate | `views / exposure` | Exposure-to-entry conversion |
| Like rate | `likes / views` | Lightweight approval |
| Comment rate | `comments / views` | Discussion activation |
| Save rate | `saves / views` | Utility or future-use value |
| Share rate | `shares / views` | Social spread value |
| Total engagement rate | `(likes + comments + saves + shares) / views` | Overall response |
| Deep engagement rate | `(comments + saves + shares) / views` | Higher-intent response |
| Follow conversion | `followers_gained / views` | Content-to-account conversion |
| Follows per 1,000 views | `followers_gained / views * 1000` | Readable conversion comparison |

Keep likes, saves, comments, and shares separate even when reporting total engagement. A high total can hide the difference between approval, utility, discussion, and spread.

## Account-relative bands

For each metric, calculate the median, P25, and P75 across mature comparable posts.

- Low: below P25.
- Typical: P25 through P75.
- High: above P75.

Use these as descriptive bands, not universal quality grades. Do not import fixed industry benchmarks unless the user provides a trustworthy benchmark source and explicitly wants external comparison.

## Funnel diagnosis matrix

| Observed pattern | Supported interpretation | Common hypotheses to test |
|---|---|---|
| Low exposure; entry and response rates typical or high | Downstream content response is not the first bottleneck | Topic demand, initial audience match, searchability, publishing consistency |
| Exposure typical/high; view rate or official cover CTR low | Entry is the main bottleneck | Cover information hierarchy, title promise, audience targeting |
| Entry high; likes typical but saves/comments/shares low | The post wins curiosity but not depth | Promise-content mismatch, weak specificity, low utility, little discussion space |
| Save rate high; follow conversion low | The post is useful but does not sell the account's ongoing value | Isolated topic, weak positioning, no series bridge, profile mismatch |
| Comments high; saves/shares low | The post triggers discussion more than durable value | Debate prompt, controversy, unresolved question |
| Exposure and entry low; response high | A potentially good post did not get enough qualified traffic | Retest the same value proposition with a different cover/title before discarding it |
| Exposure high; all downstream rates low | Broad or mismatched distribution exposed weak audience fit | Topic too broad, misleading packaging, weak content delivery |
| All stages high | A candidate repeatable pattern | Replicate topic, promise, structure, and account bridge while changing only one variable |

These are diagnostic directions, not proof. Validate creative explanations using title, cover, topic, structure, and comment evidence.

## Pattern comparison

Compare top and bottom posts on:

- Content pillar and user problem.
- Topic specificity and audience segment.
- Title hook and promised result.
- Cover style and information density.
- Image count and narrative structure.
- Publishing day and time.
- Search-oriented versus recommendation-oriented wording.
- Series continuity and follow reason.

Require at least 3 posts in a category before calling a category difference a pattern. With fewer observations, design an experiment instead.

## Confidence rules

- High: the bottleneck appears in the direct funnel metric and recurs across several comparable posts.
- Medium: the metric pattern is clear, but the creative cause depends on annotations or a small subgroup.
- Low: the claim depends on one post, a missing denominator, an unmatched comparison, or an unobserved platform mechanism.

Treat small differences as noise when counts are low. Avoid precise causal language such as “because” unless the experiment or repeated matched comparison supports it; prefer “consistent with” or “most likely.”

## Method sources and adaptations

This framework was synthesized from the useful analytical portions of:

- https://github.com/Xiangyu-CAS/xiaohongshu-ops-skill — recent-post sampling and action-oriented account review.
- https://github.com/vivy-yi/xiaohongshu-skills/tree/main/skills/03-%E6%95%B0%E6%8D%AE%E5%88%86%E6%9E%90/content-performance-analysis — per-post rate calculation and top/bottom pattern comparison.
- https://github.com/white0dew/XiaohongshuSkills — Creator Center export field coverage.

The local skill intentionally removes account automation, credential access, publishing, unsupported universal benchmarks, and arbitrary viral scores.
