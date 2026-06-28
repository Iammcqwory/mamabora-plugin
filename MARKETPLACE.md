# xAI Plugin Marketplace Submission

Steps to publish Mamabora to the [xAI plugin marketplace](https://github.com/xai-org/plugin-marketplace).

## 1. GitHub repo

This plugin is published at:

```text
https://github.com/Iammcqwory/mamabora-plugin
```

Remote and push commands for this workspace:

```bash
git remote add origin https://github.com/Iammcqwory/mamabora-plugin.git
git push -u origin master
```

## 2. Pin the commit SHA

Current pinned commit:

```text
f0fa2154c17ea801400ab008e2b17801e26107ec
```

Refresh it after any new plugin commit:

```bash
git rev-parse HEAD
```

Or from any machine:

```bash
git ls-remote https://github.com/Iammcqwory/mamabora-plugin.git HEAD
```

## 3. Fork and edit the marketplace catalog

1. Fork [xai-org/plugin-marketplace](https://github.com/xai-org/plugin-marketplace)
2. Append this entry to `.grok-plugin/marketplace.json` inside the `plugins` array
3. Run the catalog validator before opening the PR

```json
{
  "name": "mamabora",
  "description": "Pediatric AI assistant for parents and caregivers. Symptom triage with emergency escalation, developmental milestone guidance, vaccination schedules (including KEPI), and Kenya-localised emergency contacts - with strict safety guardrails.",
  "category": "healthcare",
  "source": {
    "source": "url",
    "url": "https://github.com/Iammcqwory/mamabora-plugin.git",
    "sha": "f0fa2154c17ea801400ab008e2b17801e26107ec"
  },
  "homepage": "https://github.com/Iammcqwory/mamabora-plugin",
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

Clone your marketplace fork and run:

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
2. Update the `sha` field in your marketplace PR or follow-up PR
3. Optionally bump `version` in both `plugin.json` and the catalog entry

## Local install before marketplace approval

Point Grok Build at this directory:

```text
E:\iammcqwory\Bora\Mamabora\mamabora-plugin
```

Or install from your GitHub URL:

```text
https://github.com/Iammcqwory/mamabora-plugin.git
```