# xAI Plugin Marketplace Submission

Steps to publish Mamabora to the [xAI plugin marketplace](https://github.com/xai-org/plugin-marketplace).

## 1. Push this repo to GitHub

Create a public repository (e.g. `YOUR_ORG/mamabora-plugin`) and push:

```bash
git remote add origin https://github.com/YOUR_ORG/mamabora-plugin.git
git push -u origin main
```

## 2. Pin the commit SHA

Every remote marketplace entry requires a full 40-character lowercase SHA:

```bash
git rev-parse HEAD
```

Or from any machine:

```bash
git ls-remote https://github.com/YOUR_ORG/mamabora-plugin.git HEAD
```

## 3. Fork and edit the marketplace catalog

1. Fork [xai-org/plugin-marketplace](https://github.com/xai-org/plugin-marketplace)
2. Append this entry to `.grok-plugin/marketplace.json` inside the `plugins` array
3. Replace `YOUR_ORG` and `YOUR_COMMIT_SHA` with real values

```json
{
  "name": "mamabora",
  "description": "Pediatric AI assistant for parents and caregivers. Symptom triage with emergency escalation, developmental milestone guidance, vaccination schedules (including KEPI), and Kenya-localised emergency contacts — with strict safety guardrails.",
  "category": "healthcare",
  "source": {
    "source": "url",
    "url": "https://github.com/YOUR_ORG/mamabora-plugin.git",
    "sha": "YOUR_COMMIT_SHA"
  },
  "homepage": "https://github.com/YOUR_ORG/mamabora-plugin",
  "keywords": [
    "mamabora",
    "pediatrics",
    "pediatric",
    "children",
    "parenting",
    "symptom triage",
    "milestones",
    "vaccines",
    "kenya",
    "kepi"
  ],
  "version": "1.0.0",
  "author": "Mamabora"
}
```

## 4. Validate locally

Clone the marketplace fork and run the catalog validator:

```bash
python3 scripts/validate-catalog.py
```

## 5. Open a pull request

- PR title: `Add mamabora pediatric assistant plugin`
- Note that this is a third-party healthcare education plugin with explicit disclaimers
- CI runs the validator; code-owner review is required

## Updating the plugin

When you release a new version:

1. Push changes to your plugin repo
2. Update the `sha` field in your marketplace PR (or a follow-up PR)
3. Optionally bump `version` in both `plugin.json` and the catalog entry

## Local install (before marketplace approval)

Point Grok Build at this directory:

```
e:\iammcqwory\Bora\Mamabora\Mamabora - Pediatric AI Assistant
```

Or install from your GitHub URL once pushed.
