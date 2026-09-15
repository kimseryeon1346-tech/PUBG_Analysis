# Detailed findings

## Scope and validation

The analysis uses English Steam reviews for PUBG: BATTLEGROUNDS (appid 578080) in two UTC windows around Update 42.1's `scheduled_maintenance_end_proxy` of 2026-06-17 08:30.

- PRE: 2026-06-03 08:30 to 2026-06-17 08:30 (667 reviews)
- POST: 2026-06-17 08:30 to 2026-07-01 08:30 (850 reviews)

The original review-level analysis had zero duplicate recommendation IDs. PRE contained no null or blank review text; POST contained three null reviews and four blank-or-null reviews. Blank text was retained in basic metrics and excluded from text calculations.

## Overall response

Recommendation rate changed by -0.21 percentage points, from 78.56% (524/667) in PRE to 78.35% (666/850) in POST. This is a very small descriptive difference.

Median playtime at the time of review was 50.37 hours in PRE and 89.23 hours in POST. These windows do not track the same people, so this describes a difference in reviewer composition and must not be interpreted as an effect of the update on playtime.

Median review length declined from 19 to 15 characters. The median helpful-vote count was zero in both periods.

## Negative-review issue comparison

The issue comparison uses all negative reviews as each period's denominator: 143 PRE and 184 POST. It is a multi-label rule-based classification, so issue counts do not sum to the number of reviews.

| Issue | PRE | POST | Change |
|---|---:|---:|---:|
| Ranked / RP | 6.29% (9/143) | 3.80% (7/184) | -2.49pp |
| Matchmaking | 4.90% (7/143) | 2.17% (4/184) | -2.72pp |
| Cheating / fairness | 20.98% (30/143) | 17.93% (33/184) | -3.04pp |
| Performance / technical | 6.99% (10/143) | 7.61% (14/184) | +0.62pp |
| Gameplay / balance | 6.99% (10/143) | 5.43% (10/184) | -1.56pp |

Cheating/fairness remained the largest tagged issue in each period, although its share fell because the negative-review denominator grew. Performance/technical mentions were the only listed issue share to increase.

## Ranked/RP context check

The initial Ranked/RP tag deliberately has broad candidate terms: `rank`, `ranked`, `rp`, `rating`, `tier`, `point`, and `points`. This captures relevant possibilities but also false positives: for example, a review saying "no point in playing" is not necessarily about RP.

The completed review-context check examined all 16 Ranked/RP candidates (9 PRE; 7 POST). None directly discussed the Update 42.1 RP calculation change closely enough to validate it as RP-calculation feedback. Therefore, the observed keyword-share decrease is reported as a descriptive change only. It is not evidence that the Ranked RP calculation update reduced Ranked-related dissatisfaction.

## Interpretation boundary

The review windows are different cross-sectional samples. No control group, same-user follow-up, or adjustment for concurrent changes such as server conditions, seasonal activity, or other content was used. The results show associations in Steam review writing, not causal patch effects.
