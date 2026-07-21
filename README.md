# citation-formatter

An [Agent Skill](https://agentskills.io) that generates accurate, correctly-punctuated citations — both the in-text/parenthetical form and the full bibliography/reference-list/works-cited entry — in **APA 7th**, **MLA 9th**, **Chicago 18th** (Notes-Bibliography or Author-Date), **Turabian 9th**, and **IEEE** style, based on source details you provide.

All templates, examples, and edge-case rules are sourced directly from the [University of Pittsburgh Library's Citation Styles guide](https://pitt.libguides.com/citationhelp).

## Why

Citation styles look similar but differ in exactly the details that are easiest to get wrong: comma vs. no comma, italics vs. quotation marks, inverted vs. non-inverted author names, "&" vs. "and," alphabetical vs. numeric ordering. This skill encodes those differences per style so an agent (or you) can produce a correct citation on the first try instead of guessing from memory.

## What it covers

| Style | Systems | Source types included |
|---|---|---|
| APA 7th | — | Book, edited-book chapter, print/electronic journal article, website, generative-AI chat/tool |
| MLA 9th | — | Book, ebook, journal article, encyclopedia entry, government publication, personal interview, film/DVD, website (with/without author), artwork, generative AI |
| Chicago 18th | Notes-Bibliography · Author-Date | Book, print/electronic journal article, website |
| Turabian 9th | Notes-Bibliography · Author-Date | Book, print/electronic journal article, website |
| IEEE | — | Book, book chapter, ebook, journal article, conference paper/proceedings, newspaper article, technical report, patent, standard, thesis/dissertation |

Also handled: missing author/date/page-number substitution rules, secondhand ("quoted in") citations, multi-author name formatting and "et al." thresholds, and batch processing of a whole reference list in one pass (alphabetized by author, except IEEE which stays in citation order).

## Structure

```
citation-formatter/
├── SKILL.md                        # Decision flow: pick style → source type → gather elements → apply template → output
└── references/
    ├── apa7.md                     # APA 7th templates, examples, AI-citation rules
    ├── mla9.md                     # MLA 9th templates, examples, AI-citation rules
    ├── chicago-turabian.md         # Chicago 18th & Turabian 9th, both systems
    └── ieee.md                     # IEEE numbered-bracket style, full materials table
```

## Usage

Load the skill, then describe what you want cited and in which style — e.g.:

> Cite this in APA: Sapolsky, R. M., *Behave: The biology of humans at our best and worst*, Penguin Books, 2017.

The skill will:
1. Confirm the target style (and Chicago/Turabian system, if relevant).
2. Identify the source type (book, article, website, etc.) and ask for any missing required elements — never fabricating a publisher, date, or page number.
3. Apply that style's exact punctuation and element order from the matching `references/*.md` file.
4. Return both the in-text citation and the full reference-list/bibliography/works-cited entry.

For a batch — e.g. a whole reading list or a set of citations pulled from a document — pass all sources at once; the skill returns all entries together, properly ordered for the chosen style.

## Installing

This is a [Perplexity Computer](https://www.perplexity.ai/computer) custom skill. Download the packaged `.zip` and add it via **Settings → Skills**, or load it directly in a session with:

```
load_skill(name="citation-formatter", scope="user")
```

## Source & credit

Citation templates and examples are drawn from the University of Pittsburgh Library's [Citation Styles: APA, MLA, Chicago, Turabian, IEEE](https://pitt.libguides.com/citationhelp) guide (ULS Librarian), specifically:
- [APA 7th Edition](https://pitt.libguides.com/citationhelp/apa7)
- [MLA 9th Edition](https://pitt.libguides.com/citationhelp/mla9thedition)
- [Chicago 18th / Turabian 9th](https://pitt.libguides.com/citationhelp/chicago)
- [Turabian 9th](https://pitt.libguides.com/citationhelp/turabian)
- [IEEE Style](https://pitt.libguides.com/citationhelp/ieee)

## License

No license specified — this skill packages publicly available library-guide citation examples for personal academic use. Verify against the official style manuals (APA Publication Manual, MLA Handbook, Chicago Manual of Style, IEEE Editorial Style Manual) for anything not covered here.
