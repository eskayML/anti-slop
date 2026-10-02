---
name: anti-slop
description: "Write and revise text so it does not read as machine generated. Use when drafting or reviewing any prose a human will read."
version: 1.0.0
license: MIT
---

# anti-slop

A skill for making text sound like a person wrote it.

Works with any agent that loads markdown skills. Requires nothing else.

## Why this exists

A language model produces the most statistically likely completion. That is the whole mechanism. Every tell below is the model working correctly, not malfunctioning. Which is why a word blacklist never fixes it. Strip out "delve" and strip out the em dashes and the text is still obviously synthetic. The tell was never the vocabulary. It is the shape.

Shape is set by two things. Who the writing is for, and what they sound like. So this skill has two halves. A catalogue of known tells, and a set of rules about voice and register. The second half does the real work.

## The rules

These are absolute. Breaking them is what makes writing read as generated.

### Never announce the shape of your own writing

A person says the thing. A model announces that it is about to summarise.

Bad. "The short version. We cut onboarding time in half."

Good. "Onboarding takes four minutes now, down from nine."

Banned. "The short version.", "In short", "To summarise", "Two things", "A few things", "In other words", "TL;DR" used as a heading.

### No bravado

A short punchy sentence performing toughness reads young rather than confident. It is the fastest way to sound junior to someone senior.

Bad. "I don't just prototype. I ship."

Bad. "Not just a tool, but a system."

Confidence is a fact stated flat. It is never a posture.

### Never echo your own sentence

Restating a clause you just wrote, for rhetorical effect, is a machine tic.

Bad. "The problem with this approach is that the approach is the problem."

Good. Delete the second half. The first half was enough.

### No colons in prose

A colon announces a list. A list is what a model produces when it has nothing specific to say. Permitted colons are in a URL, a time, or a heading.

Bad. "Two things stood out: speed and cost."

Good. "Speed was the surprise. Cost barely moved."

### No em dashes or en dashes

Use a comma, a full stop or brackets. Non negotiable, and trivially machine checkable, so check it with a search rather than by eye.

### One comma per sentence

Two or more commas in a sentence that is not a list means you have joined two thoughts. Break it. People stop and start again.

Bad. "The dashboard, which we rebuilt last quarter, now loads in under a second."

Good. "We rebuilt the dashboard last quarter. It loads in under a second now."

### Never volunteer a limitation

Do not open by conceding something. Do not flag what you lack, what is hard, or what might not work. It is not your job to disqualify yourself, and doing it in writing hands the reader the reason.

Bad. "This is a rough first attempt, but..."

Good. State what it does and let it stand.

This is a ban on self disqualification, not a licence to overstate. Never invent a fact, a number, a credential or a date. The two are different and the distinction matters.

### Put the specific at the end

Numbers, names and concrete details carry the weight. Weight lands at the end of a sentence, so a buried number is a wasted number.

Bad. "We grew to twelve thousand users, which took about a year."

Good. "It took about a year to reach twelve thousand users."

### Vary the rhythm

Every paragraph the same length and shape is the loudest tell there is, louder than any word choice. A four word sentence. Then one that takes its time and builds. Then short again.

Before you finish, count words per paragraph. If they all sit within a line of each other, rewrite.

### Match the register of the thing you are replying to

The strongest single fix, and the one most often skipped. A reader skimming a hundred replies recognises their own register instantly. Anything else reads as a template.

Read the original first. Place it on the scale. Write at the same temperature.

**Terse and casual.** Social posts, job boards, chat, short email. Often lowercase, often fragments.
> "looking for a backend engineer. send your resume to build@example.com"

Reply in kind. Lowercase if they are lowercase. Fragments are fine. Four or five short lines and stop.

**Formal and corporate.** Postings, proposals, reports, enterprise email.
> "We are seeking a Full Stack Engineer to work across application layers."

Reply in clean standard English. Correct and unfussy, still short.

**Regional professional.** Formal writing from outside the Western business default. This covers Indian, Nigerian, Gulf and East Asian professional English.
> "We are recruiting to fill the position below."

Reply in warm, correct professional English of that region. Do not code-switch into dialect for a formal document, and do not stiffen into American corporate speak. Meet them where they are.

Rules that follow. Never open with a greeting longer than "hi". Match the length of the original, so a three line post does not get a nine line reply. And if the original has a typo, do not become formal to compensate.

### Never describe their own text back to them

They wrote it. They know what is in it.

Banned. "I saw your post", "I came across your article", "What stood out to me", "I noticed you're looking for", "I'm reaching out because".

Open on the substance instead. Let them connect it themselves.

## The tell catalogue

The shapes to hunt for when reviewing. Full examples in the section below.

**Content.** Inflated significance, as in "a pivotal moment" or "a testament to". Manufactured notability. A superficial analysis clause bolted on with an -ing verb. Promotional adjectives. Vague attribution, as in "experts argue" or "industry reports". Formulaic challenges and future prospects sections at the end.

**Language.** The AI vocabulary set, delve, crucial, pivotal, showcase, landscape, tapestry, underscore, fostering, intricate. Copula avoidance, where "serves as" replaces "is". Negative parallelism, "not just X but Y". Rule of three. Synonym cycling, where the same thing is renamed each time to avoid repetition. False ranges, "from X to Y" where X and Y are not on one scale.

**Style.** Em dashes. Mechanical boldface. Bullet lists where every item opens with a bolded label. Title Case Headings. Decorative emoji. Curly quotes.

**Chatbot residue.** Assistant artefacts left in the text, "I hope this helps", "Certainly!", "You're absolutely right". Knowledge cutoff disclaimers. Sycophancy.

**Filler.** "In order to", "due to the fact that", "it is important to note". Excessive hedging. A generic positive conclusion. Over-hyphenated word pairs.

**Rhetoric and rhythm.** Forced metaphor. Dramatic fragmentation, where a quotable line ends every paragraph. A rhetorical question answered in the next sentence. Sentence opener tics, "So,", "Look,", "Interestingly,", "Ultimately,". Reassurance kickers, "And that's okay".

## Before and after

**Significance inflation.**
Bad. "The launch marked a pivotal moment in the company's ongoing evolution."
Good. "The launch was in March. Signups doubled by June."

**Copula avoidance.**
Bad. "The library serves as a wrapper around the API."
Good. "The library wraps the API."

**Negative parallelism.**
Bad. "It is not just a faster database, it is a rethink of how data moves."
Good. "Queries return in under ten milliseconds. That is roughly six times faster."

**Ing clause analysis.**
Bad. "The team shipped weekly, highlighting the value of tight feedback loops."
Good. "The team shipped weekly. Bugs were caught within days."

**Rule of three.**
Bad. "Fast, reliable and scalable."
Good. Name the one that matters and give the number.

**Vague attribution.**
Bad. "Experts agree the approach is sound."
Good. A named source, or drop the claim.

**Hedging.**
Bad. "It is important to note that results may vary considerably."
Good. "Results vary."

**Prompt leakage.**
Bad. "I hope this helps! Let me know if you need anything else."
Good. Delete it. Sign off, or stop.

## Self check

Run this on the finished text before it goes anywhere.

1. Any colon outside a URL or a heading? Rewrite as a sentence.
2. Any sentence announcing your own structure? Delete it.
3. Any sentence performing toughness? Flatten it to a fact.
4. Any sentence restating a clause you just wrote? Delete the second half.
5. Any sentence with two or more commas that is not a list? Break it.
6. Any volunteered limitation, hedge or self disqualification? State the capability instead.
7. Is every number and name at the end of its sentence?
8. Count words per paragraph. Are they varied, or all the same shape?
9. Is the register and length the same as the text you are replying to?
10. Read it aloud. Does it sound like a person, or a document?

## A validator you can paste into any environment

Optional. Save as `slop_check.py` if you want the mechanical checks to gate a send loop or a commit. No dependencies.

```python
#!/usr/bin/env python3
"""Mechanical slop checks. Exits non zero on a hard failure."""
import re, sys, unicodedata

DASHES = {"\u2014": "em dash", "\u2013": "en dash", "\u2015": "horizontal bar"}

META = ["the short version", "in short", "to summarise", "to summarize",
        "quick summary", "two things", "a few things", "in other words", "tl;dr"]

BRAG = ["i don't just", "i do not just", "not just a", "rather than just",
        "i build products and", "i own it end to end"]

GAPS = ["isn't my stack", "i haven't shipped", "i have not shipped",
        "i'd be learning", "i would be learning", "to be honest",
        "i lack", "i'm not familiar with", "if that rules me out",
        "no hard feelings", "be upfront"]

CHEAP = ["delve", "crucial", "pivotal", "showcase", "tapestry", "underscore",
         "fostering", "intricate", "leverage", "utilize", "utilise",
         "cutting edge", "game changer", "passionate about", "reach out",
         "circle back", "touch base", "testament to", "evolving landscape",
         "world class", "best in class"]

SKIP = re.compile(
    r"^\s*(#{1,6}\s|\||\s*$)"              # headings, tables, blanks
    r"|^\s*>\s"                             # blockquotes hold bad examples
    r"|^\s*(name|description|version|license):"
    r"|^\s*[-*+]\s*\**\s*(banned|bad|good|before|after|fix|instead)\b"
    r"|^\s*\**\s*(banned|bad|good|before|after|fix|instead|note)\s*[:\-.]\s"
    r"|^\s*\**(banned|bad|good|before|after)\**\s*$",
    re.IGNORECASE)

OFF = re.compile(r"<!--\s*slop-gate:\s*off\s*-->", re.I)
ON = re.compile(r"<!--\s*slop-gate:\s*on\s*-->", re.I)


def strip(text):
    """Drop code, blockquotes, headings and example lines. Keep the exemptions."""
    fence_mark = chr(96) * 3
    out, fence, exempt = [], False, False
    for line in text.splitlines():
        if OFF.search(line):
            exempt = True; continue
        if ON.search(line):
            exempt = False; continue
        if exempt:
            continue
        if line.strip().startswith(fence_mark):
            fence = not fence; continue
        if fence or SKIP.match(line):
            continue
        out.append(line)
    return "\n".join(out)


def check(text, strict=False):
    errs, warns = [], []
    body = strip(text)
    low = body.lower()

    for ch, name in DASHES.items():
        if ch in body:
            errs.append("contains an " + name)

    meta = re.compile(r"(?:^|[.!?:]\s+|\n)\s*[>\-*\s]*("
                      + "|".join(re.escape(m) for m in META) + r")\b", re.I | re.M)
    for m in meta.finditer(body):
        errs.append("meta-label, announces its own structure: " + repr(m.group(1)))

    for label, table in (("bravado", BRAG), ("declares a gap", GAPS)):
        for p in table:
            if p in low:
                errs.append(label + ": " + repr(p))

    for w in CHEAP:
        if w in low:
            warns.append("filler or salesy word: " + repr(w))

    m = re.search(r"(^|\n)\s*on\s+[a-z][a-z ]{2,30},", body, re.I)
    if m:
        errs.append("'On X,' paragraph opener: " + repr(m.group(0).strip()))

    for s in re.split(r"(?<=[.!?])\s+", body):
        if s.count(",") >= 2:
            parts = [p.strip() for p in s.split(",")]
            if len([p for p in parts if len(p.split()) >= 6]) >= 2:
                errs.append("comma slop, break it up: " + s.strip()[:70])

    for line in body.splitlines():
        if "http" in line or "@" in line or re.search(r"\d:\d\d", line):
            continue
        if ":" in line:
            errs.append("colon in prose: " + line.strip()[:70])

    paras = [p for p in re.split(r"\n\s*\n", body) if p.strip()]
    if len(paras) >= 4:
        lens = [len(p.split()) for p in paras]
        if max(lens) - min(lens) <= 12:
            errs.append("uniform rhythm, paragraphs: " + ", ".join(map(str, lens)))

    if strict:
        words = len(re.findall(r"\b\w+\b", body))
        if words > 140:
            errs.append(str(words) + " words, far too long for a reply")

    return errs, warns


def main():
    args = [a for a in sys.argv[1:] if not a.startswith("--")]
    if not args:
        print(__doc__); return 2
    text = sys.stdin.read() if args[0] == "-" else open(args[0], encoding="utf-8").read()
    errs, warns = check(text, "--strict" in sys.argv)

    if warns:
        print("WARNINGS (" + str(len(warns)) + ")")
        for w in warns:
            print("  ! " + w)
        print()
    if errs:
        print("FAILED (" + str(len(errs)) + ")")
        for e in errs:
            print("  X " + e)
        return 1
    print("PASSED, no hard violations")
    return 0


if __name__ == "__main__":
    sys.exit(main())
```

Two things it is built to ignore, because a gate that cries wolf gets switched off. Fenced code blocks, blockquotes and example lines are skipped, so a document can quote the bad writing it bans. And any block can be exempted outright between `<!-- slop-gate: off -->` and the matching `on` marker.

## Attribution

The tell catalogue and the before and after examples are adapted from [blader/humanizer](https://github.com/blader/humanizer) by Siqi Chen, MIT licensed, which in turn draws on [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup and licensed CC BY-SA 4.0. Keep this attribution with the file if you redistribute it.

The rules, the register scale, the self check and the validator are original.
