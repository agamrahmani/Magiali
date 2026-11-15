# Magiali

**A Hebrew consumer-rights assistant: from a free-text story to a verdict under Israel's Consumer Protection Law.**

Course project, *LLMs and Agents*, Holon Institute of Technology (HIT).

**Team:** Agam Rahmani · Hila Paz Kaniar

## The problem

Consumers have clear, numeric rights (cancellation windows, fee caps, price rules), but they rarely know when those rights apply. A typical forum post never cites a law, and a single detail can flip the answer: website or store, day 14 or day 15, a standard product or a made-to-order one.

## The task

- **Input:** a consumer story in free Hebrew, with no legal terms.
- **Output:** a structured JSON with the situation (one of 29 classes), the decisive facts, a verdict (*the business broke the law* · *you're entitled* · *no right* · *missing info*), the missing facts, and the legal basis (rule ID and exact section).

## Approach (planned)

We compare two fine-tuned approaches on the same data:

- **A: Direct verdict.** One fine-tuned model reads the story and returns everything, including the verdict.
- **B: Extract + rules.** A classifier routes the story, a fine-tuned model extracts the facts, and a rule engine written from the law decides.
- **C: Off-the-shelf reference.** A commercial LLM with no training.

Training data is generated synthetically, label-first: rule table → sampled scenario → computed label → LLM-written story → quality control. Evaluation uses a standard test set, a contrast set (pairs that differ in one fact), and a small set of real public questions.

## Status

Week 5: project proposal. No code or data yet.

## Repository structure

```
slides/
  week5-proposal/   Proposal slides (PPTX and PDF)
```

More folders (`data/`, `src/`, `prompts/`, `results/`) will be added as the project progresses.
