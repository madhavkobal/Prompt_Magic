# Promptos - AI Prompt Engineering Platform

**Version 2.0** | **Single-File Application** | **Dual LLM Support**

---

## 🚀 Quick Start

Promptos is an AI-powered prompt engineering platform that helps you create, evaluate, and improve prompts for Large Language Models.

### Features

✅ **Dual LLM Support** - Google Gemini (cloud) + Ollama (local)
✅ **Prompt Evaluation** - Get quality scores (0-100) with detailed feedback
✅ **Automatic Improvement** - AI-powered prompt enhancement
✅ **Template Library** - Save and reuse your best prompts
✅ **Complete History** - Track all evaluations with favorites
✅ **Event Logging** - Comprehensive system activity logs
✅ **Fully Responsive** - Works on all devices

---

## 📖 Documentation

**For complete setup and usage instructions, see [USER_GUIDE.md](USER_GUIDE.md)**

The user guide includes:
- LLM provider setup (Gemini & Ollama)
- Step-by-step feature walkthroughs
- Best practices for prompt engineering
- Troubleshooting guides
- FAQ and tips

---

## 🏃 Getting Started

### 1. Open the Application

Open `index.html` or `promptos-with-logging.html` in your web browser.

### 2. Configure Your LLM Provider

#### Option A: Google Gemini (Cloud)

1. Get API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Settings → Select "Google Gemini (Cloud)"
3. Enter API key → Choose model → Save

#### Option B: Ollama (Local)

1. Install [Ollama](https://ollama.ai)
2. Pull a model: `ollama pull llama3.3:70b`
3. Start Ollama: `ollama serve`
4. Settings → Select "Ollama (Local)" → Refresh models → Save

### 3. Evaluate Your First Prompt

1. Go to **Evaluate** section
2. Enter your prompt
3. Click **"Evaluate Prompt"**
4. Review score and feedback

---

## 🎯 Key Features Overview

### Evaluate Prompts
- Quality scoring (0-100)
- Detailed feedback with strengths and improvements
- Color-coded quality indicators
- Model-specific analysis

### Improve Prompts
- AI-powered automatic improvement
- Side-by-side comparison
- Detailed reasoning for changes
- One-click prompt replacement

### Templates
- Save reusable prompt patterns
- 5 categories: Creative, Business, Coding, Education, Data
- Variable placeholders
- Search and filter

### History
- Chronological evaluation tracking
- Favorites system (max 100)
- Re-run past evaluations
- Export as JSON, CSV, or PDF

### Event Logs
- 5 log levels: DEBUG, INFO, WARN, ERROR, CRITICAL
- 7 categories: USER_ACTION, API_CALL, SYSTEM, ERROR, PERFORMANCE, SECURITY, DATA
- Filter by level, category, date range
- Export logs for troubleshooting

---

## 🛠️ Supported Models

### Google Gemini
- Gemini 3 Flash (Preview) - Fastest
- Gemini 3 Pro (Preview) - Best quality, 1M context
- Gemini 2.5 Flash - Stable, fast
- Gemini 2.5 Pro - Stable, high quality
- Gemini 2.0 Flash - Legacy

### Ollama (Local Models)
- **Llama 3.x:** 70B, 90B, 8B variants
- **Qwen 2.5:** 72B, 32B, 14B, 7B
- **DeepSeek R1:** 70B, 32B, 14B, 8B, 7B
- **Mistral/Mixtral:** 7B, 8x7B
- **Gemma 2:** 27B, 9B
- **Phi 4:** 14B
- **Custom models** supported

---

## 💡 Why Promptos?

### For Google Gemini Users
✅ Access to latest cutting-edge models
✅ No local infrastructure needed
✅ Reliable cloud processing
✅ Easy API-based setup

### For Ollama Users
✅ 100% privacy - all processing local
✅ Zero API costs after setup
✅ Unlimited evaluations
✅ Offline capability
✅ Latest open-source models

---

## 📊 Usage Example

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

## 🔧 System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Internet connection (for Google Gemini)
- For Ollama: Local installation + sufficient RAM for chosen model

---

## 📝 Files in This Repository

| File | Description |
|------|-------------|
| `index.html` | Main application (single-file, complete) |
| `promptos-with-logging.html` | User-accessible copy |
| `USER_GUIDE.md` | Comprehensive documentation (90+ pages) |
| `README.md` | This file - quick overview |
| `UX_UI_EVALUATION.md` | UX/UI analysis and improvements |

---

## 🔐 Privacy & Data

- **All data stored locally** in browser localStorage
- **API keys obfuscated** before storage
- **Prompts sent only to selected LLM** (Gemini or Ollama)
- **No external tracking or analytics**
- **Export/Import** functionality for data portability
- **Ollama = 100% local processing** (prompts never leave your machine)

---

## ⚡ Quick Tips

1. **Start simple** - Evaluate basic prompts first
2. **Use Improve** - Let AI enhance your prompts automatically
3. **Save templates** - Reuse successful prompts
4. **Try both providers** - Compare Gemini vs Ollama results
5. **Check logs** - Use Event Logs for troubleshooting
6. **Export regularly** - Backup your data weekly

---

## 🐛 Troubleshooting

### "Invalid API Key" (Gemini)
→ Verify API key in Settings, regenerate at [Google AI Studio](https://makersuite.google.com/app/apikey)

### "Could Not Connect to Ollama"
→ Run `ollama serve` in terminal, verify `http://localhost:11434` is accessible

### "No Models Found" (Ollama)
→ Pull a model: `ollama pull llama3.3:70b`, click Refresh in Settings

**For detailed troubleshooting, see [USER_GUIDE.md](USER_GUIDE.md#troubleshooting)**

---

## 📚 Resources

- **Google Gemini API:** https://ai.google.dev/gemini-api/docs
- **Ollama:** https://ollama.ai
- **Gemini Models:** https://ai.google.dev/gemini-api/docs/models
- **Ollama Models:** https://ollama.ai/library

---

## 🎨 Themes

- **Sleek Dark** (default) - Modern dark theme
- **Midnight Blue** - Blue-accented dark
- **Professional Light** - Clean light theme
- **Solarized** - Easy on the eyes

Change in Settings → Theme

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl + Enter` | Evaluate prompt |
| `Esc` | Close modals |
| `Tab` | Navigate |

---

## 📦 Technology Stack

- **Pure HTML/CSS/JavaScript** - Single-file application
- **Bootstrap 5** - Responsive UI framework
- **Lucide Icons** - Beautiful icon set
- **Animate.css** - Smooth animations
- **jsPDF** - PDF export functionality
- **localStorage API** - Client-side data persistence

---

## 🚦 Version History

- **v2.0** (Current) - Added Ollama support, enhanced UI, comprehensive logging
- **v1.5** - Templates, favorites, improved UX/UI
- **v1.0** - Initial release with Google Gemini support

---

## 📄 License

This project is a proprietary single-file application.

---

## 🙏 Credits

- **UI Framework:** Bootstrap 5
- **Icons:** Lucide Icons
- **PDF Export:** jsPDF
- **Animations:** Animate.css

---

## 📞 Support

For detailed help and documentation, please refer to [USER_GUIDE.md](USER_GUIDE.md).

For issues:
1. Check Event Logs in the application
2. Review [Troubleshooting section](USER_GUIDE.md#troubleshooting)
3. Export logs for technical analysis

---

**Made with ❤️ for prompt engineers everywhere**

Last Updated: January 10, 2026
