# 🌌 Vocab Odyssey

> **The companion app for Word Smart I & II and IBA admission vocabulary**

**🔗 Live app:** [https://tanvir-taushif.github.io/The-Vocab-Odyssey/](https://tanvir-taushif.github.io/The-Vocab-Odyssey/)

**Vocab Odyssey** is a free vocabulary learning web app built to be used **alongside Word Smart I & II and IBA admission preparation**.

Reading the book is essential, but revising chapters, comparing similar words and practising active recall from paper is slow. Vocab Odyssey turns the book's word lists into an interactive study loop: **meaning-based word families (Vocab Gangs), flashcards with read-aloud, exam-style practice games and timed chapter quizzes**, all in one place and on any device.

---

# 👨‍💻 Developed By

**Tanvir Taushif**
*Data Scientist*
*B.Sc. in Information & Communication Engineering (ICE)*
**Bangladesh University of Professionals (BUP)**

### 💡 The Motivation Behind Vocab Odyssey

As a student preparing with **Word Smart** for competitive exams, I kept struggling to revise words quickly, compare similar vocabulary, and flip endlessly through pages while practising.

I built **Vocab Odyssey** to solve that bottleneck: to make revision faster, more organized and genuinely interactive, without replacing the book itself. It bridges reading the book and practising for the exam.

---

# 📚 What's Inside

| | |
|---|---|
| **Words** | 2,130, each with a clear definition |
| **Vocab Gangs** | 299 meaning-based word families |
| **Chapter quizzes** | 226 (Word Smart I: 86, Word Smart II: 84, IBA: 56), each with Set A and Set B |
| **Sources** | Word Smart I & II (Princeton Review) and IBA, University of Dhaka previous years' vocabulary questions |

---

# ✨ Features

### 🔍 Search Vocab Gangs
- Look up any word to see its **definition** and the **Vocab Gang** (family of related words) it belongs to.
- **Autocomplete** suggests words as you type, with a one-line preview of each meaning.
- **"Did you mean…?"** catches typos: searching *mendacous* suggests *mendacious*.
- Search for a meaning, like *praise*, to find the whole family of words that share it.
- Every Vocab Gang has a **Flashcards** button to study that family as a deck in one tap.

### 🃏 Flashcards
- Study **by quiz** (every Word Smart and IBA chapter) or **by meaning** (all 299 Vocab Gangs).
- Tap a card to flip it, swipe to move between cards, and shuffle or restart the deck.
- **Read aloud:** tap the speaker button to hear the word and its meaning.
- **Listening mode:** the app reads a whole deck hands-free, card by card, so you can revise on the go with earphones. Slow (0.75x) and normal speeds are available.
- **Word list PDF:** download any deck as a clean one-page sheet for paper revision.

### 🎯 Practice Games
Exam-style questions generated fresh every round from the Vocab Gangs:
- **Synonym challenge:** pick the word closest in meaning.
- **Odd one out:** find the word that doesn't belong with the other three.

Each round has 10 questions, drawn from all words or from a specific chapter. Every answer comes with an explanation (both meanings and the Vocab Gang they share), and the results screen lists the words to review. Wrong options are always taken from unrelated word families, so there is only ever one fair answer.

### 📝 Timed Chapter Quizzes
- **Contextual fill-in-the-blank sentences** for every chapter, in Set A and Set B.
- Answers are chosen from a **dropdown**, so no typing is needed on mobile.
- A **30-seconds-per-question timer** simulates exam pressure, turns amber and then red as time runs out, and submits automatically at zero.
- A **Word Bank** at the top of every quiz: tap any word to open it in Search.
- **Word list PDF** and **Self-test PDF** (meanings left blank to write from memory) for each chapter.

### 📱 Designed for Phones
- App-style bottom navigation on phones, top navigation on laptops.
- **Automatic dark mode** that follows your device setting.
- **No sign-up, no installation, nothing saved:** the app works the same on your phone and your laptop.

---

# 🎯 Recommended Study Workflow

1. **📖 Read the chapter** in Word Smart or your IBA list to learn the baseline meanings.
2. **🃏 Revise with Flashcards.** Open the chapter's deck, flip through the cards, or use Listening mode on the go.
3. **🔍 Explore the Vocab Gangs.** Search any confusing word to see its family of related words, and study that family as flashcards.
4. **🎯 Play a Practice round** with the chapter's words to test synonyms and word families.
5. **📝 Take the timed chapter quiz** (Set A, then Set B) to apply the words in context.
6. **📊 Review your mistakes.** Tap any word in the Word Bank or results to look it up instantly.

---

# 🛠️ Built With

- **HTML5, CSS3 and vanilla JavaScript**, with no frameworks and no build step
- [PapaParse](https://www.papaparse.com/) to read the word database
- [jsPDF](https://github.com/parallax/jsPDF) to generate the PDF word lists
- The browser's built-in **Web Speech API** for read-aloud
- **Google Fonts:** Literata for vocabulary words, Figtree for the interface

Hosted for free on **GitHub Pages**.

---

# 📁 Repository Structure

```text
├── index.html               # The whole app (layout, styles and logic)
├── gangs.csv                # 299 Vocab Gangs: every word with its definition
├── word_smart_quizzes.json  # 226 chapter quizzes (word banks, Set A and Set B)
├── landing-hero.png         # Home page image
└── README.md
```

---

# ✏️ Editing the Word Data

### `gangs.csv`
Three columns: `Group No`, `Group Meaning & Context` and `Words with Meanings`.

Each word is written as `Word: Definition.`, with entries separated by a space:

```text
117,"To Praise, Honor, or Applaud","Accolade: An award, honor, or expression of praise. Laud: To praise highly, especially in a public context."
```

- End every definition with a full stop, so the app knows where one word ends and the next begins.
- Don't use a colon (`:`) inside a definition.
- A word can appear in more than one gang if it genuinely fits both.

### `word_smart_quizzes.json`
Each quiz has a `quiz_title` (for example `WS1: Quick Quiz 01` or `IBA: Quick Quiz 01`), a `section`, a `display_word_bank`, and `sets` (A and B). Each set has `dropdown_options` and `questions`, where each question's `correct_answer` must be one of the dropdown options.

---

# 💻 Run It Locally

The app loads its data files with `fetch`, which browsers block when opening `index.html` directly from your computer. Start a small local server instead:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
python -m http.server 8000
```

Then open **http://localhost:8000** in your browser.

---

# ℹ️ Good to Know

- **Read-aloud voices** come from your device, so they sound different on Android, iPhone and Windows.
- **Listening mode** needs the screen to stay on: phone browsers stop speech when the screen locks. The app keeps the screen awake while listening on supported browsers.
- **PDF downloads** need an internet connection the first time. On iPhone, the PDF opens in a preview; tap Share to save it.

---

# ⚠️ Disclaimer

Vocab Odyssey is an independent, non-commercial study tool. It is **not affiliated with or endorsed by The Princeton Review** or the Institute of Business Administration (IBA), University of Dhaka. *Word Smart* is a trademark of its respective owner. Use this app alongside the original book, not as a replacement for it.

---

📚 **Learn from the book.** 🔍 **Revise with Vocab Odyssey.** 🎯 **Master vocabulary through practice.**
