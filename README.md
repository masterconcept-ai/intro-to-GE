# Intro to Gemini Enterprise lab (GSP1320) — one-command setup for Task 2 + 3

Zero-input setup for the **three Task 3 data stores** in the "Introduction to
Gemini Enterprise" (Cymbal Foods) lab. Verified end-to-end (2026-07): both
Task 2 and Task 3 "Check my progress" pass.

📖 Participant workshop guide (full walkthrough, Steps 0–5): [mcai.dev/intro-to-ge](https://mcai.dev/intro-to-ge/) (or [`lab_guide/intro-to-GE.html`](lab_guide/intro-to-GE.html) in this repo).

## Steps

### 1. Task 2 — do this by hand in the Console
1. Search **Gemini Enterprise** → **Start 30 Day Free Trial** (activate the API if prompted).
2. Create the app: App name = **`Cymbal Foods - Gemini Enterprise`**, Location = **global** → **Create**.
3. **Set up identity → Use Google Identity → Confirm Workforce Identity**.

> The IdP step is graded and must be clicked by hand — without it, connectors can't be created (`IdP must be selected`).

### 2. Task 3 — open Cloud Shell and run one command
```bash
git clone https://github.com/masterconcept-ai/intro-to-GE.git
cd intro-to-GE && ./setup.sh
```
`setup.sh` auto-installs Terraform, authenticates with your lab account's token, imports the Task 2 app, then creates and attaches the Google Drive, Google Calendar, and Cloud Storage data stores (and enables Agent Designer, Canvas, etc.).

### 3. Wait 1–2 minutes, then click "Check my progress"
Give the connectors time to become ACTIVE and the Cloud Storage import to run, then check **Task 2** and **Task 3** in the lab.

## Troubleshooting

| Symptom | Cause / fix |
|---|---|
| `app "Cymbal Foods - Gemini Enterprise" not found` | Task 2 isn't complete (app not created / wrong name). Finish it in the Console first. |
| `IdP must be selected` | Task 2 step 3 (Google Identity) wasn't clicked. Do it, then re-run `./setup.sh`. |
| `DataStore ... is being deleted` | A same-named data store was just deleted; GCP locks the id for a few hours. Re-running uses a fresh random suffix; a fresh lab won't hit this. |
| Check my progress doesn't pass | Wait another 1–2 minutes (connectors / import not ready yet) and click again. |

## Notes
- Covers only **Task 2 (app part) + Task 3**; Task 1 / 4 / 6 are done by hand following the lab.
- Does not touch billing (Qwiklabs owns the lab billing).
