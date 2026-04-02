# 6. The Chain Prompt Builder

## Purpose
Breaks any complex task into a multi-step prompt chain where each step feeds into the next. This is Claude's secret weapon — instead of one massive prompt, you build a pipeline. Output quality jumps dramatically.

## The Prompt

```
I have a complex task I need to accomplish. Instead of trying to do it all at once, I want you to break it into a prompt chain — a series of 3-5 sequential prompts where each one builds on the output of the previous step.

<task>
[DESCRIBE YOUR END GOAL HERE]
</task>

<context>
[ANY RELEVANT BACKGROUND, CONSTRAINTS, OR PREFERENCES]
</context>

For each step in the chain, give me:

1. **Step Name** — What this step accomplishes
2. **The Prompt** — The exact prompt I should use (ready to copy/paste)
3. **Expected Output** — What I should get back
4. **What Carries Forward** — What from this output feeds into the next step
5. **Quality Check** — How to verify this step worked before moving on

Also tell me:
- Where in the chain I should review/edit before continuing
- Which steps could run in parallel vs must be sequential
- Total estimated time to run the full chain

Design the chain so each individual prompt is focused and under 500 words.
```

## When to Use
- Building a presentation from scratch (research → outline → slides → speaker notes)
- Recruiting workflow (decode JD → source candidates → write outreach → prep interview guide)
- Website projects (spec → architecture → design → code → deploy)
- Any task where you've gotten mediocre results from a single prompt

## Example Chain: New Req Kickoff
1. **Decode the JD** → Extract requirements and tech stack
2. **Build Sourcing Strategy** → Target companies and boolean strings from Step 1
3. **Write Outreach Templates** → Personalized messages using selling points from Step 2
4. **Create Interview Guide** → Phone screen questions from the decoded requirements
5. **Build Scorecard** → Evaluation rubric aligned to must-haves from Step 1

## Pro Tip
Tell Claude: "I'm going to run this chain with you. After each step, I'll paste the output back. Ready for Step 1?" Then actually run it conversationally.
