---
name: copy
description: Direct response copywriting using proven frameworks. Brand-aware — reads ICP, voice, and tone from your brand config. Covers product descriptions, SEO meta, email, social, press angles.
argument-hint: "[what to write, e.g. 'landing page for new product' or 'email sequence']"
---

# Copy — Direct Response + CRO Framework

Write copy that converts. This skill combines proven direct response frameworks (Hopkins, Ogilvy, Caples, Sugarman) with a CRO-driven structure that reads your brand context automatically.

## Step 1 — Load Brand Context

Read the active brand config from `config/brands/`. Extract:
- **ICP**: who the customer is, their pain, their trigger
- **Voice & Tone**: how the brand sounds
- **Avoid**: words and styles to never use

If no brand config exists, ask:
1. "Who's the customer?" (one sentence)
2. "What's the brand voice?" (3-5 words)

## Step 2 — Identify Content Type

| Type | Job | Length |
|---|---|---|
| Landing page | Full persuasion flow: hook → problem → solution → proof → CTA | 500-1500 words |
| Product description | Make them feel it, want it | 2-4 sentences |
| SEO meta title | Own the keyword in search results | 50-60 chars |
| SEO meta description | Earn the click from search | 150-160 chars |
| Email | Move from aware to action — lead with one idea | Varies |
| Social | Spark curiosity or recognition | 1-3 lines |
| Headline variations | 10+ options using different frameworks | One-liners |
| Press angle | Hook a journalist in one sentence | One sentence |

## Step 3 — Apply Frameworks

### Headlines (80% of the work)
- **Transformation:** "From [bad state] to [good state]"
- **Specific result:** "[Number] + [unexpected detail]"
- **Direct challenge:** "You've been [doing X] wrong"
- **Story:** "They [doubted] when I [action]... But when I [result]..."
- **Question:** "Do you [common struggle]?"

### Copy Principles
- **Identity before product** — lead with who this is for, not what it is
- **Specificity over vague claims** — concrete sensory details, not "high quality"
- **Each element gets a moment** — don't list features, give each one a beat
- **Close with outcome, not features** — what the buyer gets, not what the product has
- **Show, don't sell** — describe the experience, let the product speak

### Opening Lines
- Direct challenge: "You've been using [X] wrong."
- Story: "Last [day], I [specific event] and saw [specific result]."
- Confession: "I'll be honest. I almost [gave up / failed / quit]."
- Specific result: "In [timeframe], we [specific metric]."
- Question: "Have you ever [painful situation]?"

### What to Avoid
- "In today's fast-paced world..."
- "Are you ready to take X to the next level?"
- Generic superlatives ("amazing", "incredible", "game-changing")
- Discount, urgency, or scarcity language (unless the brand config explicitly allows it)
- Exclamation marks in headlines

## Step 4 — Apply Brand Rules

Re-read the brand config's **Avoid** section. Check every line of copy against it. Common brand-specific rules:
- Certain words or phrases that are off-limits
- Tone guardrails (e.g., "never desperate", "always confident")
- Product naming conventions

## Output Format

Deliver in labelled blocks for easy copy-paste:

```
**Brand:** [brand name]
**ICP target:** [which persona]

**[Content type]**
[copy]

**[Content type]**
[copy]
```

$ARGUMENTS
