<div align="center">

# 🧱 anti-slop

**Write like a person, not a model.**

An agent skill that stops text from reading as machine generated.

[![License: MIT](https://img.shields.io/badge/License-MIT-black.svg)](https://opensource.org/license/mit)
[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB.svg?logo=python&logoColor=white)](https://python.org)
[![Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](SKILL.md)
[![Agent Skill](https://img.shields.io/badge/agent%20skill-SKILL.md-8A2BE2.svg)](SKILL.md)
[![Works with](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Cursor%20%7C%20Codex-blueviolet.svg)](SKILL.md)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-orange.svg)](#-contributing)
[![Stars](https://img.shields.io/github/stars/eskayML/anti-slop?style=flat&color=yellow)](https://github.com/eskayML/anti-slop/stargazers)

[Why](#-why-this-exists) · [Install](#-install) · [Use](#-usage) · [Rules](#-the-rules) · [Contents](#-whats-in-here)

</div>

---

> [!IMPORTANT]
> **One file. Zero dependencies. Nothing to configure.**
> Drop `SKILL.md` into your agent's skills folder and it works. The validator is plain Python and runs anywhere Python runs.

## 🧠 Why this exists

A language model produces the most statistically likely completion. That is the whole mechanism.

Every tell is the model working correctly, not malfunctioning. Which is why a word blacklist never fixes it. Strip out "delve", strip out the em dashes, and the text is still obviously synthetic. The tell was never the vocabulary. It is the shape.

Shape gets set by two things. Who the writing is for, and what they sound like. So this skill ships a catalogue of known tells **and** a set of rules about voice and register. The second half does the work, and it is the part you will not find elsewhere.

> [!TIP]
> The single strongest fix in the whole skill is **register matching**. Read what you are replying to, place it on the temperature scale, and write at the same temperature. A reader skimming a hundred replies recognises their own register instantly. Anything else reads as a template.

## 📦 Install

```bash
git clone https://github.com/eskayML/anti-slop ~/.claude/skills/anti-slop
```

That is it. Or copy `SKILL.md` anywhere your agent looks for skills. It is the only required file.

> [!NOTE]
> Already have a skills folder? Just drop `SKILL.md` inside it as `anti-slop/SKILL.md`. Nothing else is needed.

## 🚀 Usage

Ask your agent to review or rewrite text and it applies the rules. For the mechanical checks, run the validator directly.

```bash
python3 slop_check.py draft.md          # check a file
cat draft.txt | python3 slop_check.py - # check a pipe
python3 slop_check.py --strict email.txt # adds length and evidence rules
```

It exits non zero on a hard failure. That means it drops into a commit hook, a CI step, or a send loop that refuses to send.

> [!WARNING]
> A gate that only checks for dashes and banned vocabulary will pass machine written prose cheerfully. The voice checks are the ones that matter.

## 📏 The rules

These are absolute. Breaking them is what makes writing read as generated.

| | Rule | The failure it prevents |
|:--|:--|:--|
| 1️⃣ | Never announce the shape of your own writing | "The short version." |
| 2️⃣ | No bravado | "I don't just prototype, I ship." |
| 3️⃣ | Never echo your own sentence | "The plan is the plan." |
| 4️⃣ | No colons in prose | "Two things stood out: speed and cost." |
| 5️⃣ | No em dashes or en dashes | The loudest single tell |
| 6️⃣ | One comma per sentence | Two thoughts welded together |
| 7️⃣ | Never volunteer a limitation | Handing over the reason to say no |
| 8️⃣ | Put the specific at the end | A buried number is a wasted number |
| 9️⃣ | Vary the rhythm | Uniform paragraphs, the loudest fingerprint |
| 🔟 | Match the register | Reading as a template |
| 1️⃣1️⃣ | Never describe their text back to them | "I saw your post" |

Plus a ten point self check to run before anything goes out.

## 🔍 What it catches

Seven groups of tells, with before and after examples for each.

- 🎈 **Puffed up importance.** Ordinary events written as history.
- 📚 **A borrowed vocabulary.** Delve, crucial, pivotal, showcase, tapestry.
- 🌀 **Grammar that dodges.** "Serves as" for "is". "Not just X, but Y."
- 🎨 **Formatting that performs.** Em dashes, mechanical bold, Title Case.
- 🤖 **Assistant residue.** "I hope this helps." Cutoff disclaimers.
- 💧 **Filler and hedging.** "In order to." "It is important to note."
- 🥁 **Rhythm that never breaks.** A kicker ending every paragraph.

## 📂 What's in here

| Path | What it is |
|:--|:--|
| `SKILL.md` | The skill. Rules, register scale, tells, self check, and the validator. |
| `README.md` | This file. |

That is the whole repo by design. One file to install, one file to read.

## 🤝 Contributing

Found a tell this misses? Caught the validator flagging perfectly good prose? Open an issue or a PR.

The one rule for contributions. **Everything must pass the validator it ships.** Run it on your own changes first.

## 📄 License

MIT. Use it, fork it, ship it inside your own product.

<div align="center">

**If this saved you an edit, give it a ⭐**

</div>
