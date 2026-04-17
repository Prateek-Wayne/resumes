---
name: resume-ats-agent
description: 'Tailor resumes for job applications with ATS optimization and LaTeX generation.'
argument-hint: 'Paste the job description to tailor your resume against'
---

# Resume ATS Agent

## Procedure

**Execute immediately. Do not narrate steps or describe what you are about to do. Just do it.**

1. Read `master-resumes/candidate_profile.md`
2. Read instruction files: `instructions/system_prompt.md`, `instructions/ats_rules.md`, `instructions/resume_rules.md`, `instructions/latex_rules.md`
3. Extract required and preferred keywords from the JD; map against candidate profile
4. Score the resume (required keywords 40%, preferred 20%, section completeness 15%, bullet quality 10%, quantification 10%, title alignment 5%)
5. Tailor content: inject missing keywords, rewrite weak bullets using `resources/action_verbs.txt`, prioritize JD skills — never fabricate
6. Generate the `.tex` file by using `templates/sample-resume.tex` as the structural skeleton — copy its preamble and macros verbatim, only swap in tailored content. Follow `instructions/latex_rules.md` strictly. Write final file to `tailored-resumes/Prateek_${CompanyName}.tex`
7. Output in chat (in this order): ATS score card → keywords injected → gaps with severity

## Reference Files

- [System Prompt](./instructions/system_prompt.md)
- [ATS Rules](./instructions/ats_rules.md)
- [Resume Rules](./instructions/resume_rules.md)
- [Action Verbs](./resources/action_verbs.txt)
