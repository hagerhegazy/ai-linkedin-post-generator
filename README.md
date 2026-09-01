#  AI LinkedIn Post Generator

An AI-powered pipeline that turns raw notes into a polished, ready-to-publish LinkedIn post — using two open-source LLMs working together as a **Writer** and an **Editor**, wrapped in a colorful Gradio UI.

![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Transformers](https://img.shields.io/badge/🤗-Transformers-yellow)
![Gradio](https://img.shields.io/badge/UI-Gradio-purple)

---

##  How it works

1. **Writer Model** (`Qwen/Qwen3-1.7B`) takes your raw info (bullet points, achievements, project notes) and writes a natural, human-sounding first draft.
2. **Editor Model** (`Qwen/Qwen2.5-3B`) reviews the draft for grammar, tone, structure, and engagement — and returns the final, publish-ready post.
3. A **Gradio UI** lets you paste your notes, generate both versions side-by-side, and copy the final post in one click.

```
Your notes  →  🖊️ Writer Model  →  Draft  →  🔎 Editor Model  →  Final Post
```

##  Features

- Two-stage **writer → reviewer** pipeline for higher-quality, human-sounding output
- No invented achievements — the model is strictly instructed to use only what you provide
- Colorful, custom-themed **Gradio** interface with live progress and copy-to-clipboard
- Fully open-source models via Hugging Face `transformers` (no paid API required)
- Ready to run on **Google Colab** with a free T4 GPU

##  Tech Stack

| Component | Tool |
|---|---|
| Models | Qwen3-1.7B (writer), Qwen2.5-3B (editor) |
| Framework | Transformers |
| UI | Gradio |
| Runtime | Google Colab (T4 GPU) |

##  Getting Started

### Run on Google Colab (recommended)
1. Open `hugface_30_8_with_UI.ipynb` in Google Colab.
2. Set the runtime to **T4 GPU**: `Runtime → Change runtime type → T4 GPU`.
3. Run all cells from top to bottom.
4. The last cell launches the Gradio app and gives you a public link.

### Run locally
```bash
git clone https://github.com/<your-username>/ai-linkedin-post-generator.git
cd ai-linkedin-post-generator
pip install -r requirements.txt
jupyter notebook hugface_30_8_with_UI.ipynb
```

> ⚠️ Requires a CUDA-capable GPU with enough VRAM to load both models (works comfortably on a T4).

##  Preview

<img width="900" alt="UI preview" src="assets/ui-preview.png">

*(add a screenshot of the Gradio app here after your first run)*

##  Project Structure

```
.
├── hugface_30_8_with_UI.ipynb   # Main notebook: models + pipeline + Gradio UI
├── requirements.txt             # Python dependencies
├── README.md
└── assets/                      # Screenshots / demo images
```

##  Roadmap

- [ ] Add support for other post formats (Twitter/X, Instagram captions)
- [ ] Let the user pick tone (formal / casual / storytelling)
- [ ] Add a "history" tab to keep previously generated posts
- [ ] Swap in larger/smaller models via a dropdown

##  Contributing

Issues and PRs are welcome! If you have ideas for prompt improvements or UI features, feel free to open an issue.

