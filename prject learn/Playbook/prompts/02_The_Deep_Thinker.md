# 2. The Deep Thinker

## Purpose
Forces Claude into structured step-by-step reasoning using thinking tags. Produces 40% better accuracy on complex, multi-layered problems. Use this whenever you need Claude to really work through something — not just give a surface answer.

## The Prompt

```
I need you to think through this carefully before responding.

<context>
[PASTE YOUR SITUATION / PROBLEM / DATA HERE]
</context>

Before giving your final answer, work through these steps inside <thinking> tags:

<thinking>
1. What is actually being asked here? Restate the core question.
2. What are the key facts and constraints I'm working with?
3. What are 2-3 different angles I could approach this from?
4. What's the strongest approach, and why?
5. What could go wrong with my reasoning? Any blind spots?
6. What's my confidence level (high / medium / low) and why?
</thinking>

Then give me:
- A clear, direct answer
- The reasoning chain that led you there
- Any caveats or things I should double-check
```

## When to Use
- Comparing two candidates with different strengths
- Evaluating whether a role should be restructured
- Analyzing competing technology stacks
- Any decision where you need Claude to show its work

## Pro Tip
You can add `Think step by step.` to almost any other prompt in this playbook to boost quality. It's the simplest Claude upgrade there is.
