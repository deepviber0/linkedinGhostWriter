# 🧠 LinkedIn Ghostwriter AI-Agent

Create personalized, tone-matching LinkedIn posts using your own writing samples.  
This project features a multi-step UI with `manual` and `featured` input modes and integrates with an AI agent via an `n8n` webhook to generate authentic, styled posts.

---

## 📌 Features

- ✨ **Two Analysis Modes**:
  - **Manual Mode**: Submit 2–4 of your previous LinkedIn posts for tone/style learning.
  - **Featured Mode**: Use a LinkedIn profile URL (with featured posts), or manually paste 2 posts.

- 🧠 **AI-Generated Content**:
  - Mimics your writing tone, structure, emoji use, and voice.
  - Outputs high-quality, professional LinkedIn posts based on your topic.

- 💻 **Web UI**:
  - Interactive multi-step form
  - Smart validations
  - Live loading indicators
  - LinkedIn-style result preview
  - Copy and Regenerate options

---

## 🛠️ Tech Stack

| Frontend | Backend (Workflow) | AI Engine | Scraping |
|----------|--------------------|-----------|----------|
| HTML, CSS, JavaScript | [n8n.io](https://n8n.io/) | Groq model as LLM | [Apify Web Scraper](https://apify.com/)

✅ The **Apify Web Scraper** is used in **Featured Mode** to fetch public data (headline, about section, featured posts) from LinkedIn based on the profile URL.

---

## ⚙️ How It Works

1. **User selects a mode**: Manual or Featured.
2. **Inputs post samples** and new topic details.
3. **Frontend sends a POST request** to the n8n webhook.
4. **n8n processes and forwards prompt** to an AI model (e.g., groq model).
5. **AI returns a personalized LinkedIn post**, matching tone and context.
6. **Frontend displays the post** in a styled preview with copy & regenerate buttons.

---

## 📂 Sample Payloads

### Manual Mode Payload
```json
{
  "mode": "manual",
  "topic": "Overcoming Imposter Syndrome in Tech",
  "perspective": "• Felt like I didn’t belong\n• Asked questions and grew\n• Supporting juniors now",
  "category": "career",
  "postsArray": ["Post 1 content...", "Post 2 content..."]
}
