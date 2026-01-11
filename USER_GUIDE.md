# PromptMagic User Guide

**Version:** 2.0
**Last Updated:** January 2026

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
5. [Advanced Features](#advanced-features)
6. [Keyboard Shortcuts](#keyboard-shortcuts)
7. [Tips & Best Practices](#tips--best-practices)
8. [Troubleshooting](#troubleshooting)
9. [Data Management](#data-management)

---

## Introduction

### What is PromptMagic?

PromptMagic is an AI-powered prompt engineering platform designed to help you create, evaluate, and improve prompts for Large Language Models (LLMs). Whether you're crafting prompts for Google Gemini or running local models with Ollama, PromptMagic provides intelligent analysis and actionable feedback to enhance prompt quality.

### Key Features

- ✅ **Dual LLM Support** - Works with both Google Gemini (cloud) and Ollama (local)
- ✅ **Prompt Evaluation** - Get detailed quality scores and feedback
- ✅ **Automatic Improvement** - AI-powered prompt enhancement suggestions
- ✅ **Template Library** - Save and reuse your best prompts
- ✅ **History Tracking** - Keep track of all evaluations
- ✅ **Event Logging** - Comprehensive system activity logs
- ✅ **Favorites** - Bookmark your best prompts
- ✅ **Responsive Design** - Works on desktop, tablet, and mobile

### Who Should Use PromptMagic?

- **AI Engineers** - Optimize prompts for production systems
- **Content Creators** - Craft better prompts for AI writing tools
- **Developers** - Test and refine prompts for AI integrations
- **Researchers** - Analyze prompt effectiveness systematically
- **Students** - Learn best practices in prompt engineering

---

## Getting Started

### System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for Google Gemini)
- For Ollama: Local installation of Ollama

### Opening the Application

1. Open your web browser
2. Navigate to the application file:
   - File path: `file:///home/user/promptmagic-with-logging.html`
   - Or open the `index.html` file from your installation directory

### First-Time Setup

1. Click the **Settings** icon in the top navigation bar
2. Choose your preferred LLM provider
3. Configure provider-specific settings (see [LLM Provider Setup](#llm-provider-setup))
4. Select your preferred theme
5. Click **Save Settings**

---

## LLM Provider Setup

PromptMagic supports two LLM providers: **Google Gemini** (cloud-based) and **Ollama** (local).

### Google Gemini Setup

#### Step 1: Get an API Key

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click **"Create API Key"**
4. Copy the generated API key

#### Step 2: Configure PromptMagic

1. Open **Settings** in PromptMagic
2. Select **"Google Gemini (Cloud)"** as LLM Provider
3. Paste your API key in the **"Google Gemini API Key"** field
4. Choose a Gemini model:
   - **Gemini 3 Flash (Preview)** - Fastest, good for quick evaluations
   - **Gemini 3 Pro (Preview)** - Best quality, adaptive thinking
   - **Gemini 2.5 Flash** - Stable, fast responses
   - **Gemini 2.5 Pro** - Stable, high quality
   - **Gemini 2.0 Flash** - Legacy, fast responses
5. Click **Save Settings**

#### Model Recommendations

| Use Case | Recommended Model |
|----------|-------------------|
| Quick testing | Gemini 3 Flash |
| Production use | Gemini 3 Pro |
| Cost optimization | Gemini 2.5 Flash |
| Best quality | Gemini 3 Pro |

### Ollama Local LLM Setup

#### Step 1: Install Ollama

1. Visit [ollama.ai](https://ollama.ai)
2. Download and install Ollama for your operating system
3. Open a terminal and verify installation:
   ```bash
   ollama --version
   ```

#### Step 2: Pull a Model

Choose and download a model:

```bash
# Recommended: Llama 3.3 70B (best quality)
ollama pull llama3.3:70b

# Alternative: Qwen 2.5 72B (excellent performance)
ollama pull qwen2.5:72b

# Smaller models for lower-spec systems:
ollama pull llama3.1:8b
ollama pull qwen2.5:7b
```

#### Step 3: Start Ollama Service

Ollama typically starts automatically. To manually start:

```bash
ollama serve
```

You should see: `Listening on http://localhost:11434`

#### Step 4: Configure PromptMagic

1. Open **Settings** in PromptMagic
2. Select **"Ollama (Local)"** as LLM Provider
3. Verify **Ollama Endpoint URL**: `http://localhost:11434`
4. Click the **Refresh** button to fetch installed models
5. Select your model from the dropdown
6. Click **Save Settings**

#### Supported Ollama Models

PromptMagic includes presets for popular models:

| Model Family | Sizes | Best For |
|--------------|-------|----------|
| Llama 3.x | 70B, 90B, 8B | General purpose, coding |
| Qwen 2.5 | 72B, 32B, 14B, 7B | Multilingual, reasoning |
| DeepSeek R1 | 70B, 32B, 14B, 8B, 7B | Advanced reasoning |
| Mistral | 7B | Fast, efficient |
| Mixtral | 8x7B | High quality, MoE |
| Gemma 2 | 27B, 9B | Google model, efficient |
| Phi 4 | 14B | Microsoft model, compact |

#### Using Custom Models

If your model isn't listed:

1. Select **"Custom Model..."** from the dropdown
2. Enter the exact model name from `ollama list`
3. Click **Save Settings**

#### Benefits of Ollama

✅ **Privacy** - All processing happens locally
✅ **No API costs** - Free after installation
✅ **No rate limits** - Unlimited evaluations
✅ **Offline capability** - Works without internet
✅ **Latest models** - Access to cutting-edge open models

---

## Main Features

### Evaluate Prompts

The Evaluate feature analyzes your prompts and provides:
- **Quality Score** (0-100)
- **Detailed Feedback** - Specific improvement points
- **Strengths** - What's working well
- **Areas for Improvement** - What to enhance

#### How to Evaluate a Prompt

1. **Navigate** to the **Evaluate** section (should be default)
2. **Enter your prompt** in the "Your Prompt" text box
3. Click the **"Evaluate Prompt"** button
4. **Wait** for the analysis (typically 3-10 seconds)
5. **Review** the results in the Evaluation Results section

#### Understanding the Score

| Score Range | Quality Level | Meaning |
|-------------|---------------|---------|
| 80-100 | Excellent ✅ | Production-ready, well-crafted |
| 60-79 | Good 👍 | Solid quality, minor improvements possible |
| 40-59 | Needs Improvement ⚠️ | Requires significant refinement |
| 0-39 | Critical ❌ | Major issues, immediate action required |

#### Score Display Features

- **Color-coded** indicators (green, cyan, yellow, red)
- **Visual pulse animation** for critical scores
- **Status badges** with descriptive text
- **Accessibility** support with screen reader labels

#### Example Evaluation

**Before:**
```
Write a blog post about AI
```

**Evaluation Results:**
- **Score:** 35/100 (Critical)
- **Feedback:**
  - Too vague - no specific topic within AI
  - Missing target audience
  - No tone or style specification
  - No length or format requirements

**After Evaluation, You Know:**
- Add specificity (e.g., "AI in healthcare")
- Define audience (e.g., "for non-technical readers")
- Specify tone (e.g., "informative and accessible")
- Set constraints (e.g., "800 words, 3 sections")

### Improve Prompts

The Improve feature automatically rewrites your prompt to be more effective.

#### How to Improve a Prompt

1. **Enter your prompt** in the "Your Prompt" text box
2. Click the **"Improve Prompt"** button
3. **Wait** for the AI to generate an improved version
4. **Review** the improved prompt and reasoning
5. **Compare** original vs. improved side-by-side
6. Click **"Use Improved Prompt"** to replace your original

#### What Gets Improved?

- **Clarity** - Makes instructions more specific
- **Structure** - Organizes information logically
- **Context** - Adds necessary background information
- **Constraints** - Includes format, length, and style requirements
- **Examples** - Adds examples when helpful

#### Example Improvement

**Original Prompt:**
```
Write a blog post about AI
```

**Improved Prompt:**
```
Write an 800-word blog post about practical applications
of AI in healthcare for a non-technical audience.

Structure:
- Introduction: Current state of AI in medicine
- Body: 3 specific use cases (diagnosis, treatment planning,
  drug discovery) with real-world examples
- Conclusion: Future implications and ethical considerations

Tone: Informative, accessible, optimistic but balanced
Style: Use simple language, avoid jargon, include 1-2 statistics
```

**Reasoning:**
The improved version adds:
- Specific topic focus (AI in healthcare)
- Clear audience definition
- Structured outline
- Length requirement
- Tone and style guidelines
- Concrete deliverables

### Templates

Templates let you save and reuse effective prompts.

#### Creating a Template

1. Navigate to the **Templates** section
2. Click **"Create Template"**
3. Fill in the form:
   - **Name:** Descriptive title (e.g., "Blog Post Generator")
   - **Category:** Choose from predefined categories
   - **Description:** Brief explanation of use case
   - **Content:** Your prompt template
4. Click **"Create Template"**

#### Template Variables

Use placeholders in your templates:

- `[Variable]` - Basic placeholder
- `[Tone:Professional]` - Option with default value
- `{{Variable}}` - Alternative syntax

**Example Template:**
```
Write a [Tone:Professional] email to [Recipient] about
[Topic]. The email should be [Length:2-3 paragraphs]
and include [KeyPoints].
```

#### Using Templates

1. **Browse** templates in the Templates section
2. **Click** on a template card to view details
3. **Fill in** the variable fields in the preview
4. Click **"Use This Prompt"** to load into Evaluate section

#### Template Categories

- **Creative** - Writing, storytelling, content creation
- **Business** - Emails, reports, presentations
- **Coding** - Code generation, debugging, documentation
- **Education** - Lesson plans, explanations, quizzes
- **Data** - Analysis, visualization, insights

#### Managing Templates

- **Edit:** Click template → Modify → Save
- **Delete:** Click "Delete" button in template details
- **Search:** Use the search box to filter by keywords
- **Filter:** Filter by category using dropdown

### History

History tracks all your prompt evaluations.

#### Viewing History

1. Navigate to the **History** section
2. Browse chronological list of evaluations
3. View summary info: timestamp, score, model used

#### History Features

- **Chronological order** - Newest first
- **Score visualization** - Color-coded indicators
- **Model tracking** - See which LLM was used
- **Favorites** - Star your best prompts
- **Search** - Find specific evaluations
- **Filters** - Filter by date range, score, or model

#### Re-running Evaluations

1. Click **"Re-run"** on any history item
2. Prompt loads into the Evaluate section
3. Run evaluation again to compare results

#### Favorites System

- **Add to Favorites:** Click the star icon on any history item
- **View Favorites:** Enable "Show Favorites Only" filter
- **Limit:** Maximum 100 favorites
- **Use Case:** Bookmark your best-performing prompts

#### Exporting History

**Export as JSON:**
```json
{
  "timestamp": "2026-01-10T15:30:00Z",
  "prompt": "Your prompt text...",
  "score": 85,
  "targetModel": "Gemini 3 Pro",
  "evaluation": {...}
}
```

**Export as CSV:**
Spreadsheet-compatible format with all fields

**Export as PDF:**
Formatted document with all evaluations

### Event Logs

Event Logs provide detailed system activity tracking.

#### Accessing Logs

1. Navigate to the **Logs** section
2. View chronological log entries
3. Use filters to find specific events

#### Log Levels

| Level | Icon | Usage |
|-------|------|-------|
| DEBUG 🔍 | Gray | Development information |
| INFO ℹ️ | Blue | Normal operations |
| WARN ⚠️ | Yellow | Potential issues |
| ERROR ❌ | Red | Operation failures |
| CRITICAL 🚨 | Dark Red | System-critical issues |

#### Log Categories

- **USER_ACTION** - Button clicks, navigation, inputs
- **API_CALL** - LLM API requests and responses
- **SYSTEM** - App lifecycle, initialization
- **ERROR** - Exceptions and failures
- **PERFORMANCE** - Response times, slow operations
- **SECURITY** - API key management, authentication
- **DATA** - Storage operations, exports

#### Filtering Logs

1. **By Level:** Select from dropdown (DEBUG, INFO, WARN, ERROR, CRITICAL)
2. **By Category:** Filter by event type
3. **By Date Range:** Set start and end dates
4. **By Search:** Enter keywords to find specific logs

#### Exporting Logs

**JSON Format:**
```json
{
  "exportDate": "2026-01-10T15:30:00Z",
  "logCount": 150,
  "logs": [
    {
      "id": "uuid-here",
      "timestamp": "2026-01-10T14:25:30Z",
      "level": 1,
      "levelName": "INFO",
      "category": "API_CALL",
      "message": "Gemini API call successful",
      "metadata": {
        "model": "gemini-3-flash-preview",
        "responseTime": "2345.67ms"
      }
    }
  ]
}
```

**CSV Format:** Spreadsheet with all log fields
**TXT Format:** Human-readable plain text

#### Log Management

- **Clean Old Logs:** Remove entries older than 7 days
- **Clear All Logs:** Delete all log entries (with confirmation)
- **Auto-rotation:** Keeps maximum 1000 entries
- **Retention:** 7-day automatic cleanup

#### Using Logs for Troubleshooting

1. **Reproduce the issue**
2. **Open Logs section**
3. **Filter by ERROR or CRITICAL level**
4. **Look for error messages** around the time of the issue
5. **Check metadata** for detailed error information
6. **Export logs** if needed for support

---

## Advanced Features

### Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Enter` | Evaluate prompt |
| `Ctrl + S` | Save settings |
| `Ctrl + /` | Focus search |
| `Esc` | Close modals |

### Textarea Resizing

The prompt input box supports dynamic resizing:

1. **Hover** over the bottom-right corner of the textarea
2. **Drag** the resize handle to adjust both width and height
3. **Minimum width:** 200px
4. **Maximum height:** 1200px

### Caching System

PromptMagic caches API responses for performance:

- **Cache duration:** 1 hour
- **Cache size:** 20 entries
- **Benefits:** Faster repeated evaluations, reduced API calls
- **When used:** Identical prompt + system instruction + model

### Retry Logic

Automatic retry on failures:

- **Attempts:** 3 retries
- **Delay:** Exponential backoff (2s, 4s, 8s)
- **Triggers:** Network errors, timeouts
- **Skip retry:** Authentication errors, invalid input

### Theme Customization

Available themes:

1. **Sleek Dark** (Default) - Modern dark theme
2. **Midnight Blue** - Blue-accented dark theme
3. **Professional Light** - Clean light theme
4. **Solarized** - Easy on the eyes

**Change theme:** Settings → Theme → Select → Save

### Accessibility Features

- **WCAG 2.1 Level AA** compliant
- **Keyboard navigation** - Full app accessible via keyboard
- **Focus indicators** - Clear visual focus states
- **Screen reader support** - ARIA labels and live regions
- **Skip to content** link for keyboard users
- **Touch targets** - Minimum 44px for all interactive elements

---

## Keyboard Shortcuts

### Global Shortcuts

| Keys | Action |
|------|--------|
| `Ctrl + Enter` | Evaluate the current prompt |
| `Ctrl + S` | Save settings (when settings modal is open) |
| `Esc` | Close any open modal |
| `Tab` | Navigate to next interactive element |
| `Shift + Tab` | Navigate to previous interactive element |

### Navigation Shortcuts

Click navigation links or use mouse to switch sections:
- Evaluate
- Templates
- History
- Logs

---

## Tips & Best Practices

### Writing Better Prompts

1. **Be Specific**
   - ❌ "Write about technology"
   - ✅ "Write a 500-word article about blockchain technology for beginners"

2. **Provide Context**
   - Include relevant background information
   - Define your audience
   - Specify the use case

3. **Set Constraints**
   - Length requirements
   - Format specifications
   - Tone and style guidelines

4. **Use Examples**
   - Show the desired output format
   - Include sample inputs
   - Reference similar successful prompts

5. **Iterate**
   - Start with evaluation
   - Use improvement suggestions
   - Re-evaluate the improved version
   - Save successful prompts as templates

### Choosing the Right LLM Provider

**Use Google Gemini when:**
- You need the latest cutting-edge models
- You don't want to manage local infrastructure
- You're okay with cloud processing
- You need reliable uptime

**Use Ollama when:**
- Privacy is a top priority
- You want zero API costs
- You need unlimited evaluations
- You want to work offline
- You have sufficient local compute resources

### Template Best Practices

1. **Use descriptive names** - "Blog Post Generator - Tech Topics"
2. **Add clear descriptions** - Explain when to use the template
3. **Include variables** - Make templates flexible and reusable
4. **Categorize properly** - Choose the most relevant category
5. **Test before saving** - Evaluate the template to ensure quality

### Performance Optimization

1. **Use caching** - Re-evaluate identical prompts uses cached results
2. **Choose appropriate models** - Use Flash models for quick tests
3. **Batch evaluations** - Evaluate multiple prompts in one session
4. **Clean old data** - Remove old history and logs periodically

---

## Troubleshooting

### Google Gemini Issues

#### "Invalid API Key" Error

**Cause:** API key is incorrect or expired

**Solution:**
1. Go to Settings
2. Verify API key is correctly copied (no extra spaces)
3. Generate new API key at [Google AI Studio](https://makersuite.google.com/app/apikey)
4. Update in Settings

#### "API Quota Exceeded" Error

**Cause:** You've hit Google's rate limits

**Solution:**
1. Wait for quota to reset (typically daily)
2. Check your usage at [Google Cloud Console](https://console.cloud.google.com)
3. Consider upgrading your quota
4. Switch to Ollama for unlimited local processing

#### "Model Not Found" Error

**Cause:** Model name is incorrect or deprecated

**Solution:**
1. Check [official Gemini models documentation](https://ai.google.dev/gemini-api/docs/models)
2. Update to a supported model in Settings
3. Use default: "gemini-3-flash-preview"

#### Slow Response Times

**Causes:**
- Network latency
- Model complexity
- High load on Google's servers

**Solutions:**
1. Try a Flash model (faster than Pro)
2. Check your internet connection
3. Retry during off-peak hours
4. Switch to Ollama for local processing

### Ollama Issues

#### "Could Not Connect to Ollama" Error

**Cause:** Ollama service is not running

**Solution:**
1. Open terminal
2. Run: `ollama serve`
3. Verify output shows: "Listening on http://localhost:11434"
4. Retry in PromptMagic

#### "No Models Found" When Refreshing

**Cause:** No models are installed

**Solution:**
1. Open terminal
2. Pull a model: `ollama pull llama3.3:70b`
3. Wait for download to complete
4. Click "Refresh" in PromptMagic Settings

#### Ollama Endpoint Not Accessible

**Cause:** Wrong endpoint URL or firewall blocking

**Solution:**
1. Verify Ollama is running: `curl http://localhost:11434`
2. Check endpoint in Settings (should be `http://localhost:11434`)
3. Try `http://127.0.0.1:11434` instead
4. Check firewall settings

#### Model Not Responding

**Causes:**
- Model too large for available RAM
- Ollama process crashed

**Solutions:**
1. Check Ollama logs in terminal
2. Restart Ollama: Stop and run `ollama serve` again
3. Try a smaller model (e.g., 7B instead of 70B)
4. Close other memory-intensive applications

### General Issues

#### "Failed to Parse Evaluation Results"

**Cause:** LLM returned non-JSON response

**Solution:**
1. Retry the evaluation
2. Try a different model
3. Simplify your prompt
4. Check logs for detailed error

#### Browser Console Errors

**Cause:** JavaScript errors in the application

**Solution:**
1. Refresh the page (`Ctrl + R` or `F5`)
2. Clear browser cache
3. Try a different browser
4. Check for browser updates

#### Data Not Saving

**Cause:** localStorage quota exceeded or disabled

**Solution:**
1. Enable cookies/localStorage in browser settings
2. Clear old history and logs
3. Export data and import to fresh instance
4. Check available storage space

#### Application Running Slowly

**Causes:**
- Too many logs/history items
- Memory leaks
- Browser extensions interfering

**Solutions:**
1. Clean old logs (Logs → Clean Old)
2. Clear history items
3. Refresh the browser page
4. Disable browser extensions temporarily
5. Close unused browser tabs

---

## Data Management

### Exporting All Data

1. Go to **Settings**
2. Click **"Export All Data"**
3. Choose save location
4. File saved as: `promptmagic-data-[timestamp].json`

### Importing Data

1. Go to **Settings**
2. Click **"Import Data"**
3. Select your exported JSON file
4. Data merges with existing data

### Backing Up Data

**Recommended schedule:** Weekly

**What gets backed up:**
- All templates
- Complete history
- All event logs
- Settings (excluding API keys for security)

**How to backup:**
1. Export All Data
2. Save to cloud storage (Google Drive, Dropbox, etc.)
3. Keep multiple versions

### Resetting the Application

**To reset all data:**

1. Open browser developer tools (`F12`)
2. Go to Console tab
3. Run: `localStorage.clear()`
4. Refresh the page
5. Reconfigure settings

**Warning:** This deletes all templates, history, and logs permanently!

### Data Storage

All data is stored locally in your browser using localStorage:

- **Location:** Browser's local storage
- **Size limit:** ~5-10MB (varies by browser)
- **Persistence:** Data remains until manually cleared
- **Privacy:** Data never leaves your device (except for API calls)

---

## Frequently Asked Questions

### Is my data private?

**Yes.** All data is stored locally in your browser. The only data sent externally is:
- Your prompts to Google Gemini (if using Gemini)
- Your prompts to Ollama (if using Ollama locally - stays on your machine)

API keys are obfuscated before storage and never logged.

### Can I use PromptMagic offline?

**Partially:**
- **With Gemini:** No - requires internet for API calls
- **With Ollama:** Yes - fully offline after initial setup
- **UI access:** Yes - the application works offline for viewing history, templates, etc.

### How much does PromptMagic cost?

**PromptMagic is free.** However:
- **Google Gemini:** May have API costs after free tier (check Google's pricing)
- **Ollama:** Completely free, but requires local compute resources

### Which LLM provider is better?

It depends on your needs:

| Factor | Google Gemini | Ollama |
|--------|---------------|--------|
| Privacy | Cloud-based | 100% local |
| Cost | Pay per use | Free (after setup) |
| Performance | Excellent | Depends on hardware |
| Ease of setup | Very easy | Moderate |
| Model quality | Cutting-edge | Excellent open models |
| Offline use | No | Yes |

### Can I use both Gemini and Ollama?

**Yes!** You can switch between providers anytime in Settings. Your history will track which provider was used for each evaluation.

### What happens to my API key?

- Stored in browser's localStorage with basic obfuscation
- Never transmitted except to Google's API
- Not included in data exports for security
- Can be deleted anytime in Settings

### How accurate are the scores?

Scores are AI-generated assessments based on prompt engineering best practices. They should be used as guidelines, not absolute measures. Factors evaluated include:
- Clarity and specificity
- Appropriate context
- Clear constraints
- Structure and organization
- Model-specific optimization

### Can I contribute to PromptMagic?

This is a single-file application. You can:
- Suggest features
- Report bugs
- Share templates with the community
- Provide feedback on evaluations

---

## Support & Resources

### Getting Help

If you encounter issues:

1. **Check this guide** - Most questions are answered here
2. **Review Troubleshooting section** - Common issues and solutions
3. **Check Event Logs** - Detailed error information
4. **Export logs** - For technical support

### Official Documentation

- **Google Gemini API:** https://ai.google.dev/gemini-api/docs
- **Ollama Documentation:** https://github.com/ollama/ollama
- **Bootstrap 5:** https://getbootstrap.com/docs/5.3

### Model Information

- **Gemini Models:** https://ai.google.dev/gemini-api/docs/models
- **Ollama Models:** https://ollama.ai/library

---

## Appendix

### Glossary

- **LLM** - Large Language Model
- **API** - Application Programming Interface
- **Prompt** - Instructions given to an AI model
- **Template** - Reusable prompt pattern
- **Token** - Unit of text processing in AI models
- **Context** - Background information provided to the AI
- **Evaluation** - Quality assessment of a prompt
- **localStorage** - Browser storage mechanism

### Version History

- **v2.0** - Added Ollama support, enhanced UI, comprehensive logging
- **v1.5** - Added templates, favorites, improved UX
- **v1.0** - Initial release with Gemini support

### Credits

- **UI Framework:** Bootstrap 5
- **Icons:** Lucide Icons
- **PDF Export:** jsPDF
- **Animations:** Animate.css

---

**Last Updated:** January 10, 2026
**Application Version:** 2.0

For the latest updates and information, check the application's changelog and release notes.
