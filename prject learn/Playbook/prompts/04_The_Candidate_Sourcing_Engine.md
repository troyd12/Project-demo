# 4. The Candidate Sourcing Engine

## Purpose
Generates targeted candidate profiles, boolean search strings, and a company target list for any technical role. Cuts sourcing research from hours to minutes.

## The Prompt

```
You are a senior technical sourcing specialist who builds talent pipelines for hard-to-fill roles. You have deep knowledge of the US tech landscape.

I need to source candidates for this role:

<role>
Title: [JOB TITLE]
Company: [COMPANY NAME]
Key skills: [LIST 3-5 CRITICAL SKILLS]
Level: [JUNIOR / MID / SENIOR / PRINCIPAL / DIRECTOR]
Location: [CITY/STATE or REMOTE]
</role>

Produce a complete sourcing strategy:

1. **Ideal Candidate Profile**
   - Background and career trajectory
   - Likely current titles (list 5-7 variations)
   - Education patterns (degrees, bootcamps, certifications)
   - Years of experience sweet spot

2. **Target Company List**
   - 20 US companies where these candidates currently work
   - Organized by tier: Tier 1 (direct competitors), Tier 2 (adjacent industry), Tier 3 (talent goldmines)
   - For each: company name, why they're a target, estimated team size for relevant function

3. **Boolean Search Strings**
   - 3 LinkedIn Recruiter strings (broad, focused, niche)
   - 2 GitHub/StackOverflow search strings (for engineering roles)
   - 2 Indeed/job board strings
   - Include title variations, skill synonyms, and exclusion terms

4. **Community & Event Sources**
   - Relevant Slack communities, Discord servers, subreddits
   - Conferences and meetups where these candidates speak or attend
   - Open source projects they likely contribute to

5. **Outreach Angle**
   - What would make a passive candidate respond?
   - 3 key selling points to lead with
   - What to avoid saying (turnoffs for this persona)

Format everything as a ready-to-use sourcing playbook.
```

## When to Use
- Opening a new requisition
- Hiring manager asks "where do we find these people?"
- Building a talent pipeline before roles are officially open
- GPS stretch assignment roles (Principal Architects, Supply Chain)

## Pro Tip
Follow up with: "Now write me 3 personalized outreach messages — one casual, one formal, one for a referral ask."
