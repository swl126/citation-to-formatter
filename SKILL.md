---
name: citation-formatter
description: "Generate accurate in-text citations and bibliography/reference-list/works-cited entries in APA 7th, MLA 9th, Chicago 18th (notes-bibliography or author-date), Turabian 9th, or IEEE style, based on source details the user provides. Use when the user asks to cite a source, format a reference, build a bibliography/works-cited/reference list, convert a citation between styles, or asks 'how do I cite X in Y style'. Rules and examples sourced from the University of Pittsburgh Library citation guide (https://pitt.libguides.com/citationhelp)."
metadata:
  version: '1.0'
  source: https://pitt.libguides.com/citationhelp
---

# Citation Formatter

Turns source details into an accurate, correctly-punctuated citation in whichever style the user needs — both the in-text/parenthetical form and the full bibliography/reference-list/works-cited entry.

## Step 1 — Identify the target style

Ask (or infer from context, e.g. "I'm in a psych class" → APA) which style is needed:

| Style | Common in | Reference file |
|---|---|---|
| **APA 7th edition** | Psychology, education, social sciences | `references/apa7.md` |
| **MLA 9th edition** | Humanities, language & literature | `references/mla9.md` |
| **Chicago 18th — Notes-Bibliography** | History, literature, arts (footnotes/endnotes) | `references/chicago-turabian.md` |
| **Chicago 18th — Author-Date** | Physical/natural/social sciences | `references/chicago-turabian.md` |
| **Turabian 9th** | Student research papers/theses (same as Chicago, minor simplifications) | `references/chicago-turabian.md` |
| **IEEE** | Engineering, computer science, IT | `references/ieee.md` |

If the user doesn't say and it isn't obvious from their field/discipline, ask which style — don't guess silently, since punctuation and structure differ enough between styles that a wrong guess produces a wrong citation. For Chicago, also confirm notes-bibliography vs. author-date if not specified (default to notes-bibliography, the more common choice in humanities, if the user has no preference and doesn't know).

## Step 2 — Identify the source/material type

Determine what kind of source this is: book (print or ebook), chapter in an edited book, journal article (print or electronic), website/webpage, encyclopedia entry, government publication, personal interview, film/DVD, artwork, conference paper/proceedings, technical report, patent, standard, thesis/dissertation, newspaper article, or generative-AI output (a chat/tool response, e.g. ChatGPT/Claude).

Each style's reference file has a materials table with the exact template for that type. If the source type isn't in the table, use the closest analog (e.g. a podcast episode behaves like a journal article — episode = article, series/show = container/journal) and note the substitution to the user.

## Step 3 — Gather the required elements

Load the matching reference file from Step 1 and check which elements its template needs. Typically: author(s)/creator, year (and full date for web/AI content), title of the piece, title of the container (journal/book/website/AI tool name), volume/issue, page numbers, publisher/publisher location, and a DOI or URL. Ask the user for any of these you don't have — don't fabricate a publisher, date, or page number. If genuinely unavailable (e.g., no author listed, no page numbers on a webpage), each reference file documents how that style handles missing elements (see "Missing information" note in each file).

## Step 4 — Apply the style's exact template

Read the relevant reference file and reproduce its punctuation, italics/quotation-mark conventions, and element order exactly — these details (a period vs. comma, italics vs. quotes, "and" vs. "&") are what distinguish styles and are the most common source of citation errors. Key cross-style differences to get right:

- **Author name order**: APA/Chicago author-date/Turabian author-date → `Last, F. M.` for the first author only (bibliography); MLA → `Last, First` for the first author only; Chicago/Turabian notes → `First Last` in the footnote/endnote but `Last, First` in the bibliography; IEEE → `F. Last` for every author (never inverted).
- **Article/chapter titles**: quotation marks in MLA, Chicago, Turabian, IEEE; no quotation marks (and only the first word + proper nouns capitalized) in APA.
- **Journal/book titles**: italicized in every style covered here.
- **Multiple authors**: APA uses `&` before the last author in the reference list (but "and" in-text is written out); MLA and Chicago/Turabian use "and"; 3+ authors get "et al." after the first author's name in most in-text/note citations (check the reference file for each style's exact cutoff — APA switches to "et al." at 3+ authors in-text, MLA/Chicago typically at 4+ in the full entry).
- **In-text form**: parenthetical `(Author, Year)` for APA/Chicago-author-date/Turabian-author-date; parenthetical `(Author page)` for MLA (no year, no comma); numbered footnote/endnote markers for Chicago/Turabian notes-bibliography; bracketed numbers `[1]` for IEEE (never author/date).

## Step 5 — Produce both the in-text and full entry

Give the user:
1. The in-text/parenthetical/footnote citation as it would appear at the point of use.
2. The full bibliography/works-cited/reference-list entry as it would appear in the end-of-document list.

For a **batch of sources** (a reference list, several citations at once), produce all of them in one pass and, unless the style is IEEE (which orders by first-appearance/citation order, not alphabetically), alphabetize the full entries by first author's last name in the final list.

## Step 6 — Special cases

- **Generative AI citations** (ChatGPT, Claude, etc.): APA and MLA both have explicit guidance in `references/apa7.md` and `references/mla9.md` — APA treats the AI company as author/publisher of the "Large Language Model," MLA explicitly does **not** treat the AI tool as an author and instead uses the AI tool as the container. Ask for: the prompt/what was generated, the tool name, the specific model/version, the company, the date generated, and a shareable link if one exists.
- **Secondhand/indirect quotation** ("quoted in"): see the MLA example in `references/mla9.md` (`qtd. in`); other styles use similar "quoted in" phrasing in-text while citing only the secondary source in the bibliography.
- **Missing author, date, or page numbers**: don't invent these. APA has a documented substitution order (title stands in for missing author, "n.d." for no date); note this to the user and apply the same logic pattern to other styles if their file doesn't spell it out explicitly.
- **Style consult**: for anything genuinely ambiguous or not covered in the reference files, tell the user to double-check with their instructor or the official style manual — these reference files are a quick-citation guide, not the full manual, per Pitt's own caveat on the Turabian page.

## Output format

Present results as:

```
**In-text:** <in-text citation>

**Reference-list / Bibliography / Works Cited entry:**
<full entry>
```

For a batch, use one such block per source, with the full-entry list also assembled as a single alphabetized (or numbered, for IEEE) block at the end so it can be copy-pasted directly into a paper's reference list.

## Source

All templates and examples in `references/` are drawn from the University of Pittsburgh Library's [Citation Styles guide](https://pitt.libguides.com/citationhelp): [APA 7th](https://pitt.libguides.com/citationhelp/apa7), [MLA 9th](https://pitt.libguides.com/citationhelp/mla9thedition), [Chicago 18th/Turabian 9th](https://pitt.libguides.com/citationhelp/chicago), [Turabian 9th](https://pitt.libguides.com/citationhelp/turabian), [IEEE](https://pitt.libguides.com/citationhelp/ieee).
