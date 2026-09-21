# Master Resumes

This folder holds the canonical, unedited source resume(s) for the candidate.

## Naming Convention

```
<name>_master_<YYYY-MM-DD>.txt   ← preferred (plain text, easy for agent to read)
<name>_master_<YYYY-MM-DD>.pdf   ← also accepted (agent runs extract_resume.py first)
```

Examples:

- `prateek_master_2026-04-17.txt`
- `prateek_master_2026-04-17.pdf`

## Rules

- **One master per person.** Archive old versions by appending `_v1`, `_v2` to the filename.
- **Never edit this file to match a specific JD.** That's what the agent does into a separate output.
- **Plain text preferred.** If you export from LinkedIn or a PDF, run it through `extract_resume.py` and save the `.txt` output here.

## How the Agent Uses This

The `resume-ats-agent` reads the latest file in this folder as the base resume before tailoring. It never modifies files in this folder — all output goes to the `output/` folder.
