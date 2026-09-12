# Design & PM Case Study Examples

Moved out of the main SKILL.md so the staff-SWE and AI/ML worked examples live inline there. Structure and anti-fabrication rules from the parent skill apply to these too.

## Design Example (condensed from the original skill)

**Overview header:**
```
# Redesigning the Checkout Flow
Company: E-Commerce Inc. | Role: Lead Product Designer
Timeline: 6 weeks | Team: 2 designers, 3 engineers, 1 PM
Summary: Cut cart abandonment from 68% to 44% (a 24-percentage-point,
~35% relative reduction) via a 3-step checkout.
```

**Problem:** abandonment at 68% vs. industry ~55%; exit surveys + funnel data showed drop-offs concentrated at forced account creation (73% of exits), hidden shipping costs (first shown at step 5), 7 screens, mobile-unfriendly forms. Goal: below 50% in 3 months. Constraints: no payment-integration changes, PCI compliance, pre-holiday deadline.

**Process:** Mixpanel funnel analysis; 10 interviews with recent abandoners; heatmap review; benchmarked 5 competitor flows. Options: guest-only checkout, social login, progressive profiling, one-page checkout. Chose hybrid: guest checkout first + transparent pricing + mobile-first + step indicator.

**Solution:** 3 screens with optional guest checkout; pricing widget showing total/shipping/tax from step 1; single-column mobile forms with autocomplete; trust signals throughout.

**Results (label changes correctly):**
| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Cart abandonment | 68% | 44% | −24 pp (≈35% relative) |
| Checkout completion | 32% | 56% | +24 pp (≈75% relative) |
| Mobile conversion | 18% | 41% | +23 pp (≈128% relative) |

Business impact lines ($2M recovered revenue, support-ticket drop) must come from the user's real measurements — do not carry illustrative numbers into a real case study.

**Learnings:** research prevented wrong solution; would A/B test individual changes instead of one launch; would start mobile-first.

## PM Case Study Skeleton

- **Overview:** product area, role, timeline, one-line outcome
- **Problem:** business context, user pain, metrics baseline, constraints
- **Process:** discovery, prioritization framework used, stakeholder map, hypotheses
- **Solution:** the shipped scope and what was explicitly cut, with rationale
- **Results:** metric movements against goals (labeled relative/absolute), adoption
- **Learnings:** what you'd descope differently, stakeholder lessons

Apply the same NDA gate and anti-fabrication rules as engineering examples: anonymize the company if needed, use only measured outcomes, describe scope when unmeasured.
