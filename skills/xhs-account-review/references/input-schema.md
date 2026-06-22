# Input schema

## Minimum viable fields

At least one reach field and one response field are needed for useful analysis.

| Canonical field | Common export labels | Use |
|---|---|---|
| `title` | 标题, 笔记标题, 内容标题 | Identify the post |
| `publish_time` | 发布时间, 发布日期, 时间 | Age and timing checks |
| `exposure` | 曝光, 展现, 曝光量, impressions | Distribution stage |
| `views` | 观看, 阅读, 播放, 观看量, read_count | Entry denominator |
| `cover_ctr` | 封面点击率, 点击率, CTR | Title and cover entry |
| `likes` | 点赞, 点赞数 | Lightweight response |
| `comments` | 评论, 评论数 | Discussion response |
| `saves` | 收藏, 收藏数 | Reuse and utility signal |
| `shares` | 分享, 转发, 分享数 | Spread signal |
| `followers_gained` | 涨粉, 新增关注, 新增粉丝 | Viewer-to-follower conversion |

## Useful optional fields

- `post_id` or `url`
- `content_type`: image, video, long-form
- `topic` or `content_pillar`
- `title_hook`: question, number, result, conflict, warning, story, other
- `cover_style`: text-heavy, result, person, product, scene, comparison, other
- `image_count`
- `avg_view_time`
- traffic-source shares: discovery, search, following, profile, other
- current follower count at publishing time
- observation window or data snapshot time

## Data-quality rules

1. Preserve the raw export unchanged.
2. Trim whitespace from headers and titles; do not rewrite titles.
3. Parse `-`, blank, `--`, and `N/A` as missing, not zero.
4. Normalize percentage values carefully: both `0.075` and `7.5%` may mean 7.5%.
5. Deduplicate by post ID; if absent, use title plus publish time and flag collisions.
6. Record the raw row count, excluded row count, and analyzed row count.
7. Default to excluding posts younger than 3 full days from comparative ranking.
8. If metrics are cumulative and post ages differ greatly, flag age bias or restrict to a comparable period.

## Capability by available data

| Available fields | Supported conclusion | Unsupported conclusion |
|---|---|---|
| Exposure + views + interactions + follows | Full funnel diagnosis | Exact creative cause without annotations |
| Views + interactions + follows | Response and conversion diagnosis | Distribution and cover CTR |
| Public likes/comments/saves only | Relative public response | Reach, CTR, follow conversion |
| Metrics + topic/title/cover annotations | Pattern and hypothesis testing | Causal certainty from a small sample |

If creative annotations are missing, offer to add them from user-provided covers or screenshots. Do not require account access.
