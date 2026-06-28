# Mamabora -- Pediatric AI Assistant

A [Grok Build](https://github.com/xai-org/plugin-marketplace) plugin that helps parents and caregivers with age-appropriate pediatric health education, symptom triage, developmental milestones, and vaccination schedules -- with strict safety guardrails.

> **Medical disclaimer:** Mamabora provides general educational information only. It is not a substitute for professional medical advice, diagnosis, or treatment. Always consult your pediatrician or emergency services for medical decisions.

---

## Plugin Structure

```
mamabora/
+-- plugin.json                        # Plugin manifest
+-- agents/
|   +-- pediatric-advisor.md           # Main assistant behaviour
+-- commands/
|   +-- triage.md                      # /triage -- symptom assessment
|   +-- milestones.md                  # /milestones -- developmental check
|   +-- vaccine-schedule.md            # /vaccine-schedule -- immunization reference
+-- skills/
    +-- pediatric-safety/
    |   +-- skill.md                   # Emergency red flags, disclaimers, scope limits
    +-- symptom-assessment/
    |   +-- skill.md                   # Age-appropriate symptom triage frameworks
    +-- child-development/
        +-- skill.md                   # Milestones, sleep, feeding, behaviour
```

---

## Components

### Skills

| Skill                 | Purpose                                                      |
|-----------------------|--------------------------------------------------------------|
| `pediatric-safety`    | Emergency red flags, mandatory disclaimers, scope boundaries |
| `symptom-assessment`  | Structured triage for common pediatric presentations         |
| `child-development`   | Milestone ranges, sleep, feeding, behaviour guidance         |

### Commands

| Command             | Description                                              |
|---------------------|----------------------------------------------------------|
| `/triage`           | Assess symptoms and recommend care level                 |
| `/milestones`       | Check developmental norms for a child's age              |
| `/vaccine-schedule` | Show routine immunization schedule by age and country    |

### Agents

| Agent                | Description                                                  |
|----------------------|--------------------------------------------------------------|
| `pediatric-advisor`  | General pediatric Q&A with safety-first conversation flow    |

---

## Local Development

Install in Grok Build by pointing at this directory, or publish to GitHub and add a catalog entry to the [xAI plugin marketplace](https://github.com/xai-org/plugin-marketplace):

```json
{
  "name": "mamabora",
  "description": "Pediatric AI assistant for parents -- symptom triage, milestones, and vaccination guidance.",
  "category": "healthcare",
  "source": {
    "source": "url",
    "url": "https://github.com/YOUR_ORG/mamabora-plugin.git",
    "sha": "YOUR_COMMIT_SHA"
  },
  "keywords": ["pediatrics", "children", "parenting", "mamabora"]
}
```

Pin the full 40-character commit SHA before publishing:

```bash
git ls-remote https://github.com/YOUR_ORG/mamabora-plugin.git HEAD
```

---

## Notes on Encoding

All files in this repository use **UTF-8 encoding**. If you open any file and see sequences like `â€"`, `â†'`, or `â‰¥`, your editor or terminal is reading UTF-8 bytes as Latin-1 (ISO-8859-1). Fix by:

- **VS Code**: bottom-right corner > click encoding label > "Reopen with Encoding" > UTF-8
- **vim**: `:e ++enc=utf-8`
- **cat / terminal**: ensure `LANG=en_US.UTF-8` or equivalent is set

Do not save files from a Latin-1 context -- this re-introduces mojibake.

---

## Emergency Contacts (Kenya)

The plugin includes Kenya-localised emergency references:

| Service                      | Number     |
|------------------------------|------------|
| Emergency (Police/Ambulance) | 999 or 112 |
| Child Protection Hotline     | 116        |
| Befrienders Kenya (crisis)   | 0800 723 253 |

Adjust `skills/pediatric-safety/skill.md` to add or update local numbers for other regions.

---

## License

MIT -- see LICENSE if present. Healthcare content is educational; users assume responsibility for medical decisions. This plugin does not constitute the practice of medicine.
