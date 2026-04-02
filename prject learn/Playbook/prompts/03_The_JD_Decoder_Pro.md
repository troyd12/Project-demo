# 3. The JD Decoder Pro

## Purpose
Advanced job description analysis prompt that extracts every hidden signal from a posting — must-haves vs nice-to-haves, disqualifiers, sourcing keywords, and ready-made phone screen questions. Built for technical recruiting.

## The Prompt

```
You are an expert technical recruiter with 15 years of experience decoding job descriptions for Fortune 500 companies. You specialize in separating signal from noise.

<job_description>
[PASTE FULL JD HERE]
</job_description>

Analyze this job description and produce a structured breakdown:

<section name="Role Summary">
- Job title and level (IC vs manager, seniority)
- Team/org placement and reporting structure
- Remote/hybrid/onsite status
- Compensation signals (if any)
</section>

<section name="Must-Have Requirements">
List ONLY the non-negotiable qualifications. For each:
- The skill/qualification
- Why it's likely a hard requirement (evidence from the JD)
- Years of experience implied
</section>

<section name="Nice-to-Have Skills">
List preferred but not required qualifications. Flag any that could become must-haves in screening.
</section>

<section name="Hidden Disqualifiers">
Identify phrases that signal automatic rejection (e.g., "must have active clearance," "requires relocation," specific certifications).
</section>

<section name="Tech Stack Decoded">
For each technology, framework, or tool mentioned:
- Name
- What it does (plain English, 1-2 sentences)
- How it fits in the stack (frontend/backend/infra/data)
- US companies known for using it
- Confidence score (1-5) on how critical it is to this role
</section>

<section name="Boolean Search Strings">
Generate 3 LinkedIn/Indeed boolean search strings to find candidates for this role.
</section>

<section name="Phone Screen Questions">
Write 8-10 phone screen questions:
- 3 culture/motivation fit
- 3 technical competency
- 2 situational/behavioral
- 2 role-specific deep dives
</section>

<section name="Red Flags for Candidates">
What should a candidate watch out for in this JD? (unrealistic expectations, vague scope, etc.)
</section>

Format the output as a clean, scannable document I can use immediately.
```

## When to Use
- Any new req that hits your desk
- When a hiring manager gives you a JD and says "find me someone"
- Stretch assignment roles where you need to learn the domain fast
- Pair with The Systems Architect (Prompt 01) for technical architecture roles

## Pro Tip
After running this, say "TechVibe this" to get the tech stack exported to Excel with company research.
