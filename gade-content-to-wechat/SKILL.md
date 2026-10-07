---
name: gade-content-to-wechat
description: Convert a video/audio link, uploaded media, subtitle or transcript, news/article URL, or user-provided source text into a source-faithful Chinese GADE-style WeChat Official Account article. Use when the user asks to 整理视频、把 YouTube/Bilibili/播客/访谈改写成公众号文章、把新闻或公司公告改成公众号文章、核查人物时间数字、生成标题摘要、制作低 AI 感无字封面、规划或制作正文配图、输出可复制微信公众号 HTML，or run the complete source-to-WeChat workflow. Also use for 公众号排版、只排版、合并碎段、调整微信预览、处理两端缩进或落款宽度. Distinguish source facts, quotations, publisher viewpoints, and external verification; do not claim complete coverage unless the full source or a sufficiently complete transcript was inspected.
---

# GADE Content to WeChat

## Overview

Turn videos, news, articles, transcripts, and supplied text into a traceable Chinese WeChat publishing package. Preserve source meaning and uncertainty while rebuilding the article structure for mobile reading. Produce accurate titles, a useful summary, a topic-led low-AI-look visual package, and copy-ready GADE inline-styled HTML.

## Required resources

Read the relevant files completely before acting:

- Read `references/source-workflow.md` for source retrieval, verification, `完整流程`, `只整理`, or `事实核查`.
- Read `references/editorial-workflow.md` before drafting, rewriting, or structurally revising the article. It is optional for a wording-preserving `只排版` request.
- Read `references/visual-workflow.md` when producing titles, summaries, covers, body images, or image recommendations.
- Read `references/style-guide.md` when creating or revising the WeChat HTML.
- Use `assets/wechat-template.html` as the complete HTML shell. When manual two-side indentation requires split delivery, also use `assets/wechat-body-only-template.html` and `assets/wechat-footer-only-template.html`.
- Use `assets/gade-brand-reference.png` only as an optional brand-language reference, never as a mandatory cover palette or article image.

## Modes

Choose the smallest mode that satisfies the request:

- `完整流程` (default): source acquisition, structured dossier, verification, rewrite, title and summary, cover, body-image plan, HTML, and QA.
- `只整理`: comprehensive source-faithful notes; keep video timecodes when available.
- `只改写`: rewrite a transcript, article, or supplied notes without retrieving a new source.
- `只排版`: preserve wording and claims, skip source retrieval and substantive rewriting, and create GADE copy-ready HTML.
- `事实核查`: verify names, roles, dates, numbers, quotations, and announcements with authoritative sources.
- `只配图`: design or produce the cover and body-image package from an existing finished article.

## Workflow

### 1. Route the source

Classify the input as video/audio, transcript/subtitles, news/article URL, official announcement, or supplied text. Follow the matching route in `references/source-workflow.md`.

For `只排版`, treat the supplied text as the complete working source. Do not retrieve or fact-check a new source unless the user requests it.

For videos, do not infer complete content from the title, thumbnail, description, chapters, search snippets, or memory. Obtain the audiovisual source or a sufficiently complete transcript before claiming a complete整理.

For news and articles, open the canonical page and identify the publisher, author, publication and update dates, cited primary sources, and whether the page is independent reporting, an opinion article, a press release, or a company announcement.

### 2. Build a source dossier

Before drafting, record:

- source metadata and access status;
- people, organizations, products, papers, dates, and numbers;
- central claim, reasoning, evidence, examples, qualifications, and counterpoints;
- direct quotations that matter, kept short;
- claims requiring external verification;
- unresolved ambiguity or missing coverage.

For videos, map substantive chapters to time ranges and speakers. For news, build a claim ledger that separates reported facts, attributed statements, publisher analysis, and externally verified facts.

### 3. Verify without blurring attribution

Use primary and authoritative sources for current, numerical, legal, technical, or reputationally material claims. Prefer company announcements, regulatory filings, official documentation, original papers, and named public records over secondary summaries.

Keep these layers distinct:

1. What the source directly reports or shows.
2. What a named person or company claims.
3. What the publisher or interviewer interprets.
4. What external primary-source verification confirms, qualifies, or contradicts.

Do not turn a company disclosure into an independent finding. Do not silently strengthen `可能`, `预计`, or `公司表示` into certainty.

### 4. Redesign the article logic

Do not perform sentence-by-sentence substitution. Rebuild the structure around the reader's central question while retaining the source's facts, causal chain, evidence, caveats, and attribution. For GADE research features, apply the topic-substance and narrative gate in `references/editorial-workflow.md` before drafting: lead with the concrete result, follow one main thread, and explain terms only as needed.

Create:

- one recommended title and four meaningfully different alternatives;
- one 60–120 Chinese-character summary;
- an opening tension grounded in the source;
- normally 5–10 numbered sections for a long article;
- a conclusion that follows from the source and does not invent a new thesis;
- a transparent source and editing note.

Use natural, concrete Chinese, 2–3 sentences per paragraph, concise transitions, and sparse emphasis. Apply the readability and attribution guidance in `references/editorial-workflow.md`: preserve necessary claim-level qualifications, and consolidate routine process disclosures in the source note. Explain specialist terms at first use. Prefer faithful paraphrase over long quotations.

### 5. Produce the visual package

Follow `references/visual-workflow.md`.

- Prefer authentic user-supplied, official, editorial, or scientific imagery before generating a substitute.
- Default to a text-free cover with one strong focal idea and both wide and square crop safety.
- Choose colors from the article subject, source imagery, environment, and editorial mood. GADE green is optional; do not force one palette across unrelated articles.
- Preserve GADE continuity through restraint, hierarchy, tactile realism, disciplined composition, and the surrounding HTML.
- Reject generic AI imagery, pseudo-text, robots, glowing brains, neon circuitry, fake interfaces, fabricated news scenes, or implausible scientific equipment.
- Body imagery is optional. For this GADE workflow, default to a text-only body and a cover; produce body images when the user requests them. A genuinely useful evidence image or explanatory diagram may be suggested briefly, but do not create an extra asset package by default. If the user asks for no body images, omit diagrams, illustrations, insertion instructions, and body-image deliverables.
- Recommend or produce only images that add explanation or verifiable evidence; article length alone does not justify images.

### 6. Format the WeChat article

Follow `references/style-guide.md` and use `assets/wechat-template.html`.

- Keep title, author, summary, cover, original/reprint declaration, and account card outside the body HTML.
- Begin the body with the selectable-text `GADE Insights` divider, not a repeated title.
- Use inline styles only. Do not use scripts, external fonts, gradients, or forced body backgrounds.
- Remove all Markdown syntax from final HTML and use `<strong>` for intended emphasis.
- Do not embed local images by default because clipboard transfer may drop them. Deliver image files separately with exact insertion points and captions.
- In `只排版`, preserve every claim, caveat, source attribution, and argument order. Merge sentence fragments into logical paragraphs, but never shorten or summarize unless requested.

Treat browser-to-WeChat transfer as a sanitizing boundary. Inline typography, centering, and borders may survive while padding, margins, percentage-width wrappers, spacer tables, and transparent side borders do not. Do not promise that HTML can force WeChat's native `两端缩进` setting or keep stacking CSS workarounds after a mobile preview disproves them.

When the user requests native two-side indentation, or a mobile preview shows that the inset was lost, keep the complete HTML and additionally deliver:

- `*-body-only.html`: GADE opening divider, article body, and source note.
- `*-footer-only.html`: engagement prompt, centered `62%` green rule, `— 完 —`, star prompt, and community CTA.

Tell the user to paste body-only first, select only that inserted material in WeChat, and apply the requested native indentation such as `8`. Then paste footer-only at the end without selecting or re-indenting the complete article. Keep title, summary, author, cover, and account card as native WeChat fields or components.

### 7. Validate and deliver

Pass only when:

- every substantive article section maps to the source or an external citation;
- names, roles, dates, numbers, and quotations are consistent;
- facts, quotations, company claims, and publisher viewpoints remain distinguishable;
- no source claim is invented, strengthened, or stripped of a material caveat;
- title and summary are not repeated inside the HTML;
- HTML tags balance, styling is inline, and Markdown markers are absent;
- for split delivery, the visible text of body-only followed by footer-only matches the complete HTML in order, without omissions, duplication, or a second source note;
- the cover passes original-size, thumbnail, wide-crop, square-crop, low-AI-look, and artifact checks;
- source and image attribution or licensing caveats are stated;
- source coverage is reported honestly as complete, near-complete, partial, or blocked.

## Default deliverables

Place the publishable package in one versioned output directory:

```text
<slug>-wechat-article.md
<slug>-wechat.html
cover/<slug>-cover-wide.png
cover/<slug>-cover-square.png
```

When manual two-side indentation is requested, additionally deliver:

```text
<slug>-body-only.html
<slug>-footer-only.html
```

Add finished body-image files only when the user requested them or suitable official/user-supplied assets are available. Keep the title package, summary, cover note, manuscript, body-image plan, source note, citations, and unresolved caveats together in the Markdown file. Keep the HTML limited to the publishable body.

Do not deliver transcripts, dossiers, traceability tables, prompts, rejected covers, thumbnails, scorecards, backups, or QA logs unless requested. Use a task-scoped temporary directory for intermediate work.

## Completion report

Tell the user:

- which source material was actually accessed and the coverage level;
- which facts were externally verified and which remain publisher or company claims;
- the recommended title and summary;
- the final article, HTML, cover, and body-image paths;
- whether images are generated, user-supplied, or official-source assets;
- the winning cover score and crop compatibility;
- any unresolved ambiguity or rights caveat;
- whether normal or split-copy delivery was used;
- how to copy the HTML into WeChat and which elements must be inserted manually.
