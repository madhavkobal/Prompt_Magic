# PromptMagic - AI Prompt Engineering Platform

**Version 3.0** | **Single-File Application** | **Dual LLM Support**

---

## Quick Start

PromptMagic is an AI-powered prompt engineering platform that helps you create, evaluate, and improve prompts for Large Language Models.

### Features

**Core**
- **Dual LLM Support** — Google Gemini (cloud) + Ollama (local)
- **Prompt Evaluation** — Quality scores (0–100) with detailed feedback, strengths, and improvement areas
- **Automatic Improvement** — AI rewrites your prompt; apply with one click
- **Template Library** — Save, categorize, and reuse prompt patterns
- **Complete History** — Every evaluation tracked with favorites and re-run support
- **Event Logging** — Comprehensive system activity logs (5 levels, 7 categories)

**UX & Productivity (Batch 1)**
- **First-Run Onboarding** — Dismissible setup banner guides new users
- **Keyboard Shortcut Panel** — Press `?` to view all shortcuts
- **History Stats Bar** — Total evaluations, avg score, best score, favorites count
- **Score Trend Sparkline** — Last-10 scores visualized as a mini bar chart
- **Ollama Connection Test** — One-click ping with inline pass/fail feedback
- **OS Theme Detection** — Respects `prefers-color-scheme` on first load
- **Storage Indicator** — Real-time localStorage usage in Settings footer
- **Prompt Quick Tips** — Collapsible best-practices panel below the editor
- **Dynamic Model Filter** — History model dropdown populated from actual data

**UX & Productivity (Batch 2)**
- **Auto-Save Draft** — Textarea content saved every 2 s; restored after accidental reload
- **Navbar Theme Toggle** — Moon/sun icon button for instant dark ↔ light switch
- **History Sort** — Sort by newest, oldest, best score, or worst score
- **Save Prompt as Template** — One-click template creation from any evaluation result
- **Copy Result as Markdown** — Export full evaluation (score + feedback + strengths) to clipboard
- **API Duration Badge** — Shows how long each evaluation took (~2.3 s) next to the score
- **History Capacity Bar** — Progress bar showing N/limit with yellow/red warnings
- **Configurable History Limit** — Choose 25, 50, 100, or 200 items in Settings
- **History Date Range Filter** — Filter by Today, Last 7 Days, or Last 30 Days
- **"Use Improved Version" Button** — Apply the AI-improved prompt to the editor in one click

---

## Getting Started

### 1. Open the Application

Open `index.html` in any modern web browser (Chrome, Firefox, Safari, Edge).

### 2. Configure Your LLM Provider

#### Option A: Google Gemini (Cloud)

1. Get an API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Settings → Select **"Google Gemini (Cloud)"**
3. Enter API key → Choose model → Save

#### Option B: Ollama (Local)

1. Install [Ollama](https://ollama.ai)
2. Pull a model: `ollama pull llama3.3:70b`
3. Start Ollama: `ollama serve`
4. Settings → Select **"Ollama (Local)"** → click **Test Connection** → Refresh models → Save

### 3. Evaluate Your First Prompt

1. Go to the **Evaluate** section
2. Enter your prompt in the editor
3. Click **"Evaluate Prompt"**
4. Review score, feedback, strengths, and suggested improvements

---

## Key Features

### Evaluate Prompts
- Quality scoring (0–100) with animated circle
- Detailed feedback: strengths, improvement areas, specific advice
- Color-coded quality indicators (green / cyan / yellow / red)
- **API duration badge** — see exactly how fast the evaluation ran
- **Save as Template** and **Copy as Markdown** buttons appear after every evaluation

### Improve Prompts
- AI-powered prompt rewriting
- Side-by-side original vs. improved comparison
- Detailed reasoning for every change made
- **"Use Improved Version"** button applies the improved text to the editor instantly, auto-saving it as a draft

### Auto-Save Draft
- Prompt text is silently auto-saved every 2 seconds
- On reload, a "Draft Restored" toast appears with a Discard option
- Draft is automatically cleared after a successful evaluation

### Templates
- Save prompts from the evaluation results bar or via the Templates section
- 5 built-in categories: Creative, Business, Coding, Education, Data
- Variable placeholders: `[Topic]`, `[Tone:Professional]`
- Search and filter by category

### History
- **Stats bar** — Evaluations count, avg score, best score, favorites
- **Score sparkline** — Last-10 evaluation trend at a glance
- **Capacity bar** — Visual fill showing N/limit (yellow ≥ 70%, red ≥ 90%)
- **Sort** — Newest, Oldest, Score ↓ Best, Score ↑ Worst
- **Filter by model** — Dynamic dropdown from actual history data
- **Filter by score range** — Excellent / Good / Needs Work
- **Filter by date** — Today / Last 7 Days / Last 30 Days
- **Favorites** — Star any item; filter to favorites only
- **Export** — Markdown, PDF, or JSON

### Settings
- **History limit** — 25 / 50 / 100 / 200 items (trimmed immediately if lowered)
- **Theme quick toggle** — Navbar moon/sun button for instant dark ↔ light switch
- **4 themes** — Sleek Dark, Midnight Blue, Professional Light, Solarized
- **Storage indicator** — Shows `~142 KB / ~5 MB` with color warnings
- **Ollama connection test** — Inline ✓/✗ feedback before saving

### Event Logs
- 5 levels: DEBUG, INFO, WARN, ERROR, CRITICAL
- 7 categories: USER_ACTION, API_CALL, SYSTEM, ERROR, PERFORMANCE, SECURITY, DATA
- Filter by level, category, date range, keyword
- Export as JSON, CSV, or TXT

---

## Supported Models

### Google Gemini
- Gemini 3 Flash (Preview) — Fastest
- Gemini 3 Pro (Preview) — Best quality, 1M context
- Gemini 2.5 Flash — Stable, fast
- Gemini 2.5 Pro — Stable, high quality
- Gemini 2.0 Flash — Legacy

### Ollama (Local Models)
- **Llama 3.x:** 70B, 90B, 8B variants
- **Qwen 2.5:** 72B, 32B, 14B, 7B
- **DeepSeek R1:** 70B, 32B, 14B, 8B, 7B
- **Mistral / Mixtral:** 7B, 8×7B
- **Gemma 2:** 27B, 9B
- **Phi 4:** 14B
- **Custom models** supported

---

## Usage Example

**Before:**
```
Write a blog post about AI
```
**Score:** 35/100 (Critical ❌)

**After Improvement:**
```
Write an 800-word blog post about practical applications of AI
in healthcare for a non-technical audience.

Structure:
- Introduction: Current state of AI in medicine
- Body: 3 specific use cases (diagnosis, treatment planning,
  drug discovery) with real-world examples
- Conclusion: Future implications and ethical considerations

Tone: Informative, accessible, optimistic but balanced
Style: Use simple language, avoid jargon, include 1-2 statistics
```
**Score:** 92/100 (Excellent ✅)

---

## Privacy & Data

- **All data stored locally** in browser localStorage
- **API keys obfuscated** before storage
- **Prompts sent only to the selected LLM** (Gemini or Ollama)
- **No external tracking or analytics**
- **Export / Import** for full data portability
- **Ollama = 100% local** — prompts never leave your machine

---

## Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + Enter` | Evaluate prompt |
| `Ctrl + S` | Save settings (when Settings is open) |
| `Ctrl + /` | Focus search |
| `Esc` | Close modals / panels |
| `?` | Open keyboard shortcut reference panel |

---

## Quick Tips

1. **Auto-save is always on** — type freely, your draft survives a reload
2. **Use the moon/sun button** in the navbar to switch themes without opening Settings
3. **After evaluating**, use "Save as Template" or "Copy as Markdown" from the results bar
4. **After improving**, click "Use Improved Version" to apply it in one step
5. **Sort history by Score ↓** to quickly find your best-performing prompts
6. **Export regularly** — backup your data weekly with Settings → Export All Data

---

## Troubleshooting

### "Invalid API Key" (Gemini)
→ Verify key in Settings; regenerate at [Google AI Studio](https://makersuite.google.com/app/apikey)

### "Could Not Connect to Ollama"
→ Run `ollama serve` in terminal; verify `http://localhost:11434` is accessible; use **Test Connection** button in Settings

### "No Models Found" (Ollama)
→ Pull a model: `ollama pull llama3.3:70b`; click **Refresh** in Settings

### Application running slowly
→ Lower history limit in Settings (25 or 50 items); clean old logs in the Logs section

**For detailed troubleshooting, see [USER_GUIDE.md](USER_GUIDE.md#troubleshooting)**

---

## System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for Google Gemini only)
- For Ollama: local installation + sufficient RAM for the chosen model

---

## Files in This Repository

| File | Description |
|---|---|
| `index.html` | Main application (single-file, complete) |
| `USER_GUIDE.md` | Comprehensive documentation |
| `README.md` | This file — quick overview |

---

## Technology Stack

- **Pure HTML / CSS / JavaScript** — single-file application
- **Bootstrap 5** — responsive UI framework
- **Lucide Icons** — icon set
- **Animate.css** — animations
- **jsPDF** — PDF export
- **localStorage API** — client-side data persistence

---

## Version History

- **v3.0** (Current, February 2026) — Batch 2: auto-save draft, theme quick toggle, history sort/date filter/capacity bar, configurable history limit, results action bar (save as template + copy as Markdown), API duration badge, "Use Improved Version" button
- **v2.0** (January 2026) — Batch 1: onboarding banner, keyboard shortcut panel, history stats bar + sparkline, Ollama connection test, OS theme detection, localStorage indicator, prompt quick tips, dynamic model filter, score validation
- **v1.5** — Templates, favorites, improved UX/UI
- **v1.0** — Initial release with Google Gemini support

---

## Support

For detailed help, see [USER_GUIDE.md](USER_GUIDE.md).

For issues:
1. Check Event Logs in the application
2. Review the [Troubleshooting section](USER_GUIDE.md#troubleshooting)
3. Export logs for technical analysis

---

**Made with care for prompt engineers everywhere**

Last Updated: February 2026
