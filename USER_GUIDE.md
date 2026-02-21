# PromptMagic User Guide

**Version:** 3.0
**Last Updated:** February 2026

---

## Table of Contents

1. [Introduction](#introduction)
2. [Getting Started](#getting-started)
3. [LLM Provider Setup](#llm-provider-setup)
   - [Google Gemini Setup](#google-gemini-setup)
   - [Ollama Local LLM Setup](#ollama-local-llm-setup)
4. [Main Features](#main-features)
   - [Evaluate Prompts](#evaluate-prompts)
   - [Improve Prompts](#improve-prompts)
   - [Templates](#templates)
   - [History](#history)
   - [Event Logs](#event-logs)
5. [Productivity Features](#productivity-features)
   - [Auto-Save Draft](#auto-save-draft)
   - [Results Action Bar](#results-action-bar)
   - [Keyboard Shortcuts](#keyboard-shortcuts)
   - [Theme Quick Toggle](#theme-quick-toggle)
   - [Prompt Quick Tips](#prompt-quick-tips)
6. [Settings Reference](#settings-reference)
7. [Tips & Best Practices](#tips--best-practices)
8. [Troubleshooting](#troubleshooting)
9. [Data Management](#data-management)
10. [FAQ](#faq)

---

## Introduction

### What is PromptMagic?

PromptMagic is an AI-powered prompt engineering platform designed to help you create, evaluate, and improve prompts for Large Language Models (LLMs). Whether you're crafting prompts for Google Gemini or running local models with Ollama, PromptMagic provides intelligent analysis and actionable feedback to enhance prompt quality.

### Key Features

**Core evaluation and workflow**
- **Dual LLM Support** — Works with Google Gemini (cloud) and Ollama (local)
- **Prompt Evaluation** — Quality scores (0–100) with feedback, strengths, and improvement areas
- **Automatic Improvement** — AI rewrites your prompt with full reasoning
- **Template Library** — Save, categorize, and reuse prompts
- **History Tracking** — Every evaluation logged with favorites and re-run
- **Event Logging** — 5 levels, 7 categories, filterable and exportable

**UX enhancements (Batch 1)**
- First-run onboarding banner for new users
- Keyboard shortcut reference panel (`?`)
- History stats bar + score sparkline chart
- Ollama one-click connection test
- OS dark/light theme auto-detection
- localStorage usage indicator in Settings
- Collapsible prompt engineering tips panel
- Dynamic history model filter

**UX enhancements (Batch 2)**
- Auto-save draft — textarea content survives page reloads
- Navbar moon/sun toggle for instant theme switching
- History sort by date or score
- Save any evaluated prompt as a template in one click
- Copy evaluation result as formatted Markdown
- API duration badge on evaluation results
- History capacity progress bar with color warnings
- Configurable history limit (25 / 50 / 100 / 200)
- History date range filter (Today / 7 days / 30 days)
- "Use Improved Version" button on improvement results

### Who Should Use PromptMagic?

- **AI Engineers** — Optimize prompts for production systems
- **Content Creators** — Craft better prompts for AI writing tools
- **Developers** — Test and refine prompts for AI integrations
- **Researchers** — Analyze prompt effectiveness systematically
- **Students** — Learn best practices in prompt engineering

---

## Getting Started

### System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for Google Gemini)
- For Ollama: local Ollama installation + sufficient RAM for the chosen model

### Opening the Application

Open `index.html` in your web browser directly from the file system.

### First-Time Setup

On your first visit, PromptMagic shows an **onboarding banner** with setup instructions. It disappears automatically when you save valid settings.

1. Click **Settings** (or the gear icon) in the navbar
2. Choose your LLM provider (Gemini or Ollama)
3. Configure provider-specific settings (see below)
4. Optionally set your preferred theme
5. Click **Save Settings**

---

## LLM Provider Setup

### Google Gemini Setup

#### Step 1: Get an API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the generated key

#### Step 2: Configure PromptMagic

1. Open **Settings**
2. Select **"Google Gemini (Cloud)"** as LLM Provider
3. Paste your API key
4. Choose a model:

| Model | Speed | Quality | Use Case |
|---|---|---|---|
| Gemini 3 Flash (Preview) | Fastest | Good | Quick tests |
| Gemini 3 Pro (Preview) | Moderate | Best | Production |
| Gemini 2.5 Flash | Fast | Good | Cost-optimized |
| Gemini 2.5 Pro | Moderate | High | Stable high quality |
| Gemini 2.0 Flash | Fast | Good | Legacy workflows |

5. Click **Save Settings**

### Ollama Local LLM Setup

#### Step 1: Install Ollama

1. Visit [ollama.ai](https://ollama.ai) and install for your OS
2. Verify: `ollama --version`

#### Step 2: Pull a Model

```bash
# Best quality (requires ~40 GB RAM)
ollama pull llama3.3:70b

# Good balance (~20 GB RAM)
ollama pull qwen2.5:32b

# Light (~6 GB RAM)
ollama pull llama3.1:8b
ollama pull qwen2.5:7b
```

#### Step 3: Start Ollama

```bash
ollama serve
# Output: Listening on http://localhost:11434
```

#### Step 4: Configure PromptMagic

1. Open **Settings**
2. Select **"Ollama (Local)"**
3. Verify endpoint: `http://localhost:11434`
4. Click **"Test Connection"** — a green ✓ with model count confirms success
5. Click **Refresh** to load installed models
6. Select your model
7. Click **Save Settings**

#### Supported Ollama Models

| Model Family | Sizes | Strengths |
|---|---|---|
| Llama 3.x | 70B, 90B, 8B | General purpose, coding |
| Qwen 2.5 | 72B, 32B, 14B, 7B | Multilingual, reasoning |
| DeepSeek R1 | 70B, 32B, 14B, 8B, 7B | Advanced reasoning |
| Mistral | 7B | Fast, efficient |
| Mixtral | 8×7B | High quality, mixture-of-experts |
| Gemma 2 | 27B, 9B | Compact Google model |
| Phi 4 | 14B | Compact Microsoft model |

For a model not listed, choose **"Custom Model..."** and enter the exact name from `ollama list`.

---

## Main Features

### Evaluate Prompts

Evaluates your prompt and returns a quality score plus structured feedback.

#### How to Evaluate

1. Navigate to the **Evaluate** section
2. Type or paste your prompt in the editor
3. Click **"Evaluate Prompt"** (or press `Ctrl + Enter`)
4. Wait for the analysis (typically 2–10 seconds)
5. Review results — the **API duration badge** next to the score label shows how long it took

#### Understanding the Score

| Score | Level | Meaning |
|---|---|---|
| 80–100 | Excellent ✅ | Production-ready |
| 60–79 | Good 👍 | Solid, minor tweaks possible |
| 40–59 | Needs Improvement ⚠️ | Significant refinement required |
| 0–39 | Critical ❌ | Major issues, rewrite recommended |

Scores are clamped to 0–100; non-numeric LLM responses default to 0 with a warning toast.

#### Results Action Bar

After a successful evaluation, two buttons appear below the results:

- **Save as Template** (bookmark icon) — prompts for a name and saves the current prompt to your template library
- **Copy as Markdown** (copy icon) — copies the full result (score, model, date, feedback, strengths, improvements) as formatted Markdown to your clipboard

#### Example

**Input:**
```
Write a blog post about AI
```

**Evaluation:**
- Score: 35/100 (Critical)
- Feedback: too vague, no audience, no length, no structure specified

**Input (after improvement):**
```
Write an 800-word blog post about AI in healthcare for a
non-technical audience. Include 3 use cases and a conclusion
about future implications. Tone: informative, optimistic.
```

**Evaluation:**
- Score: 92/100 (Excellent)

### Improve Prompts

AI-rewrites your prompt to be more specific, structured, and effective.

#### How to Improve

1. Enter a prompt in the editor
2. Click **"Improve Prompt"**
3. Review the side-by-side comparison (Original | Improved) and the reasoning section
4. Click **"Use Improved Version"** — the improved text is loaded into the editor, auto-saved as a draft, and the improvement panel closes

#### What Gets Improved

- Clarity and specificity
- Structure and logical flow
- Audience definition
- Format and length constraints
- Model-specific optimisation

### Templates

Reusable prompt patterns with variable support.

#### Creating a Template

**From the Templates section:**
1. Navigate to **Templates**
2. Click **"Create Template"**
3. Fill in name, category, description, and content
4. Click **"Create Template"**

**From an evaluation result:**
1. Evaluate any prompt
2. Click **"Save as Template"** in the results action bar
3. Enter a name when prompted — saved instantly to your library

#### Template Variables

```
Write a [Tone:Professional] email to [Recipient] about [Topic].
Length: [Length:2-3 paragraphs].
```

Variables can have a default value after the colon.

#### Categories

- **Creative** — Writing, storytelling, content creation
- **Business** — Emails, reports, presentations
- **Coding** — Code generation, debugging, documentation
- **Education** — Lesson plans, explanations, quizzes
- **Data** — Analysis, visualization, insights
- **Custom** — Saved from evaluation results

#### Using a Template

1. Open **Templates**
2. Find the template (search or category filter)
3. Click on the card → fill variables → click **"Use This Prompt"**

### History

Every evaluation is automatically saved to History.

#### History Dashboard

At the top of the History section you'll see:

- **Stats bar** — Total evaluations | Avg score | Best score | Favorites count
- **Capacity bar** — Thin progress bar showing N / limit. Turns yellow at ≥ 70% full, red at ≥ 90% full
- **Score sparkline** — Last 10 evaluation scores as mini vertical bars, oldest left to newest right

#### Filters and Sort

| Control | Options |
|---|---|
| Search | Free-text search across prompt content |
| Model | Dynamically populated from actual history |
| Score | All Scores / Excellent (80–100) / Good (60–79) / Needs Work (0–59) |
| Show | All Items / ⭐ Favorites Only |
| Sort | Newest First / Oldest First / Score ↓ Best / Score ↑ Worst |
| Period | All Time / Today / Last 7 Days / Last 30 Days |

Click **Clear Filters** to reset all controls at once.

#### Actions on History Items

- **Re-run** — Loads prompt back into the Evaluate section
- **Favorite** — Star icon; favorited items show a ⭐ badge
- **Delete** — Removes the item permanently

#### Exporting History

- **Export MD** — Markdown document
- **Export PDF** — Formatted PDF via jsPDF
- **Clear History** — Deletes all items (with confirmation)

### Event Logs

Detailed system activity log for debugging and auditing.

#### Log Levels

| Level | Color | Usage |
|---|---|---|
| DEBUG 🔍 | Gray | Development detail |
| INFO ℹ️ | Blue | Normal operations |
| WARN ⚠️ | Yellow | Potential issues |
| ERROR ❌ | Red | Operation failures |
| CRITICAL 🚨 | Dark Red | System-critical events |

#### Log Categories

- **USER_ACTION** — Button clicks, navigation
- **API_CALL** — LLM requests and responses
- **SYSTEM** — App lifecycle, initialization
- **ERROR** — Exceptions and stack traces
- **PERFORMANCE** — Response times
- **SECURITY** — API key operations
- **DATA** — Storage reads/writes, exports

#### Log Management

- **Auto-rotation:** max 1,000 entries
- **Retention:** 7-day automatic cleanup
- **Clean Old Logs** — Remove entries older than 7 days
- **Clear All Logs** — Delete all entries (with confirmation)
- **Export** — JSON, CSV, or TXT

---

## Productivity Features

### Auto-Save Draft

The prompt editor auto-saves its content to localStorage every 2 seconds (debounced).

- **On reload:** A "Draft Restored" toast appears with a **Discard** link
- **Discard:** Removes the saved draft and clears the editor
- **Auto-clear:** Draft is deleted after a successful evaluation — no stale content on next session

No configuration needed; it works transparently in the background.

### Results Action Bar

After every successful evaluation, a thin action bar appears below the results with two buttons:

| Button | Icon | What it does |
|---|---|---|
| Save as Template | bookmark | Prompts for a name, saves prompt to Templates |
| Copy as Markdown | copy | Copies full evaluation as Markdown to clipboard |

The bar is hidden when you clear the input or load a new evaluation.

**Markdown output format:**
```markdown
# Prompt Evaluation

**Score:** 85/100
**Model:** Google Gemini (gemini-3-flash-preview)
**Date:** 2/21/2026, 14:35:02

## Feedback
...

## Strengths
- Clear objective stated
- Appropriate length constraints

## Areas for Improvement
- Missing target audience definition
```

### Keyboard Shortcuts

Press `?` in any section to open the shortcut reference panel.

#### Global Shortcuts

| Keys | Action |
|---|---|
| `Ctrl + Enter` | Evaluate the current prompt |
| `Ctrl + S` | Save settings (Settings modal must be open) |
| `Ctrl + /` | Focus the search field |
| `Esc` | Close any open modal or panel |
| `?` | Open / close keyboard shortcut reference |

#### Navigation

Use the top navbar links to switch between Evaluate, Templates, History, and Logs.

### Theme Quick Toggle

The **moon / sun icon** in the navbar (between `?` and Settings) switches themes without opening Settings:

- **Moon** (currently dark) → click → switches to Professional Light
- **Sun** (currently light) → click → switches to Sleek Dark

The Settings modal `#themeSelect` stays in sync; OS preference (`prefers-color-scheme`) is respected on first load.

**All available themes:**

| Theme | Description |
|---|---|
| Sleek Dark (default) | Modern dark with accent colors |
| Midnight Blue | Blue-accented dark |
| Professional Light | Clean white/gray |
| Solarized | Warm tones, easy on the eyes |

### Prompt Quick Tips

A collapsible **Quick Tips** panel sits below the character counter in the Evaluate section. Open/closed state persists between sessions (stored in localStorage).

Tips cover: role assignment, constraint setting, output format specification, context inclusion, few-shot examples, and chain-of-thought prompting.

---

## Settings Reference

Open Settings via the gear icon in the navbar or press `Ctrl + S` when the modal is open.

### LLM Provider

Switch between Google Gemini (cloud) and Ollama (local). Each provider shows its own configuration fields.

### Theme

Select from Sleek Dark, Midnight Blue, Professional Light, or Solarized. Changes apply immediately. The **moon/sun navbar button** toggles dark ↔ light without opening this modal.

### History Limit

Choose how many evaluation items to keep: **25**, **50** (default), **100**, or **200**.

If you lower the limit below the current item count, the oldest items are trimmed immediately and a warning toast reports how many were removed.

### Data Management

| Button | Description |
|---|---|
| Export All Data | Saves all templates, history, and logs as JSON |
| Import Data | Merges a previously exported JSON into current data |

### Developer Options

**Show Event Logs in navigation** — toggle the Logs nav link for a cleaner menu.

### Storage Indicator

The Settings footer shows real-time localStorage usage (`~142 KB / ~5 MB`) with color states:
- Default — within normal range
- Yellow — ≥ 70% full
- Red — ≥ 90% full

---

## Tips & Best Practices

### Writing Better Prompts

1. **Be specific**
   - ❌ `Write about technology`
   - ✅ `Write a 500-word article about blockchain for beginners`

2. **Define your audience** — Who will read or act on this output?

3. **Set constraints** — length, format (JSON, bullet points, markdown), tone, reading level

4. **Add examples** — show the desired output structure in your prompt

5. **Iterate** — evaluate → improve → re-evaluate → save as template

### Using the Workflow Efficiently

- **Keyboard-first:** `Ctrl + Enter` to evaluate; `?` to check shortcuts without leaving the editor
- **Draft safety:** Close the tab mid-prompt without worry — your work auto-saves
- **From improvement to template:** Click "Use Improved Version" → evaluate → "Save as Template" in three clicks
- **Share results:** "Copy as Markdown" puts the full evaluation on your clipboard, ready to paste into docs, Slack, or Notion

### Template Best Practices

- **Descriptive names:** `"Blog Post Generator — Tech Topics"` not `"Blog"`
- **Include variables:** Makes templates flexible for different inputs
- **Test before saving:** Run an evaluation to confirm quality
- **Use categories:** Easier to find later via filter

### History Hygiene

- Use **Sort: Score ↓ Best** to surface your best prompts quickly
- **Favorite** any prompt scoring 80+ so it's never buried
- Lower the **History Limit** to 25–50 if the app feels slow
- **Export history** weekly before clearing to avoid data loss

### Choosing a Provider

**Use Gemini when:**
- You need the latest cutting-edge model quality
- You don't want to manage local infrastructure
- Reliable uptime matters

**Use Ollama when:**
- Privacy is non-negotiable (prompts never leave your machine)
- You want zero per-call costs
- You work offline or on a metered connection

---

## Troubleshooting

### Google Gemini Issues

#### "Invalid API Key"
1. Go to Settings — verify the key has no extra spaces
2. Regenerate at [Google AI Studio](https://makersuite.google.com/app/apikey)
3. Paste the new key and Save

#### "API Quota Exceeded"
1. Wait for daily quota reset
2. Check usage at [Google Cloud Console](https://console.cloud.google.com)
3. Switch to Ollama for unlimited local evaluation

#### Slow Response Times
1. Try a Flash model (faster than Pro)
2. Check your internet connection
3. Retry during off-peak hours

### Ollama Issues

#### "Could Not Connect to Ollama"
1. Run `ollama serve` in a terminal
2. Confirm output: `Listening on http://localhost:11434`
3. Use **Test Connection** in Settings — look for the green ✓

#### "No Models Found"
1. `ollama pull llama3.3:70b` (or any model)
2. Wait for download to finish
3. Click **Refresh** in Settings

#### Endpoint Not Accessible
1. `curl http://localhost:11434` — expect `Ollama is running`
2. Try `http://127.0.0.1:11434` in the endpoint field
3. Check firewall / antivirus rules

#### Model Not Responding / Out of Memory
1. Check Ollama terminal for errors
2. Restart Ollama: stop and run `ollama serve` again
3. Switch to a smaller model (e.g., 7B or 8B)
4. Close other memory-intensive applications

### General Issues

#### "Failed to Parse Evaluation Results"
1. Retry — the LLM may have returned a non-JSON response
2. Try a different model
3. Check Event Logs (ERROR level) for details

#### Data Not Saving
1. Enable localStorage in browser settings (cookies / site data)
2. Clear old history and logs to free space
3. Check the Storage Indicator in Settings — if red, export and clear

#### Application Running Slowly
1. Reduce History Limit to 25–50 in Settings
2. Clean old logs: Logs → Clean Old
3. Refresh the page
4. Disable browser extensions temporarily

#### Draft Not Restoring
1. Check that localStorage is enabled in your browser
2. The draft key is `draft_prompt` — you can inspect it in DevTools → Application → Local Storage

---

## Data Management

### Exporting All Data

1. Settings → **Export All Data**
2. Choose a save location
3. File saved as: `promptmagic-data-[timestamp].json`

Includes: all templates, complete history, all event logs. API keys are excluded for security.

### Importing Data

1. Settings → **Import Data**
2. Select a previously exported `.json` file
3. Data merges with existing content (no duplicates by ID)

### History Limit & Trimming

Set your preferred limit in Settings → History Limit. Lowering it below the current count trims the oldest items immediately. Export first if you want to preserve them.

### Resetting the Application

```javascript
// In browser DevTools → Console:
localStorage.clear();
// Then refresh the page
```

**Warning:** This permanently deletes all templates, history, logs, and settings.

### Data Storage Details

| Key | Contents |
|---|---|
| `templates` | JSON array of template objects |
| `history` | JSON array of evaluation records |
| `logs` | JSON array of log entries |
| `gemini_api_key` | Obfuscated API key |
| `llm_provider` | `"gemini"` or `"ollama"` |
| `theme` | Active theme name |
| `max_history_items` | `"25"`, `"50"`, `"100"`, or `"200"` |
| `draft_prompt` | Auto-saved textarea content |
| `tips_open` | `"1"` or `"0"` for tips panel state |
| `max_history_items` | Configured history limit |

---

## FAQ

### Is my data private?

Yes. All data lives in your browser's localStorage. The only data sent externally is your prompt text — to Google Gemini (cloud) or Ollama (local, stays on your machine). API keys are obfuscated before storage and excluded from exports.

### Can I use PromptMagic offline?

- **Gemini:** No — requires internet
- **Ollama:** Yes — fully offline after initial model download
- **UI / History / Templates:** Always accessible offline

### How much does it cost?

PromptMagic is free. Google Gemini may incur API costs after the free tier. Ollama is free after setup.

### Which provider gives better scores?

Scores reflect how well your prompt follows prompt-engineering best practices, not which provider you chose. The same prompt will score similarly regardless of provider.

### Can I use both providers?

Yes. Switch in Settings anytime. History records which provider was used for each evaluation.

### What happens to my API key?

- Stored with basic obfuscation in localStorage
- Transmitted only to Google's API endpoint
- Never included in data exports
- Deleted when you clear localStorage or save a new key

### How accurate are the scores?

Scores are AI-generated assessments of prompt quality based on clarity, specificity, context, constraints, and model-specific best practices. Use them as directional guidance, not absolute truth.

### My history capacity bar is full — what should I do?

Increase the limit in Settings → History Limit, or export your history (Export MD / Export PDF) and then click Clear History.

---

## Appendix

### Glossary

- **LLM** — Large Language Model
- **Prompt** — Instructions given to an AI model
- **Template** — Reusable prompt pattern with variable slots
- **Draft** — Auto-saved, unsent prompt content
- **Token** — Unit of text processing in AI models
- **localStorage** — Browser-side persistent key-value storage
- **Sparkline** — Small inline chart showing a trend at a glance
- **Capacity bar** — Progress-bar showing history items vs. configured limit

### Version History

| Version | Date | Highlights |
|---|---|---|
| **3.0** | February 2026 | Batch 2: auto-save draft, theme quick toggle, history sort/date filter/capacity bar, configurable limit, results action bar, API duration badge, "Use Improved Version" |
| **2.0** | January 2026 | Batch 1: onboarding banner, shortcut panel, history stats + sparkline, Ollama connection test, OS theme detection, storage indicator, prompt tips, dynamic model filter, score clamping |
| **1.5** | — | Templates, favorites, improved UX |
| **1.0** | — | Initial release, Google Gemini support |

### Credits

- **UI Framework:** Bootstrap 5
- **Icons:** Lucide Icons
- **PDF Export:** jsPDF
- **Animations:** Animate.css

---

**Last Updated:** February 2026 | **Application Version:** 3.0
