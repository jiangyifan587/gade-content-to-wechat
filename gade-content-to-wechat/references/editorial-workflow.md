# 公众号改写、交付与质检

## Internal working materials

Create a source dossier and editorial plan before drafting. Keep them internal unless the user requests evidence.

The editorial plan must include:

- intended reader and one-sentence promise;
- source type and coverage level;
- central question and article angle;
- one recommended title and four alternatives;
- 60–120 Chinese-character summary;
- opening hook;
- numbered outline mapped to source locations or verified claims;
- conclusion boundary;
- cover and body-image direction.

## Rewrite standard

Write a faithful feature article, not a transcript or article disguised by synonym replacement.

- Reorganize around the reader's main question.
- Preserve the source's facts, reasoning, evidence, examples, qualifications, and disagreement.
- Preserve who said what and the original level of certainty.
- Explain acronyms and specialist terms on first use.
- Use 2–3 sentences per paragraph and one idea per paragraph.
- Use numbered sections for long articles, normally 5–10.
- Prefer paraphrase; use only short quotations whose wording matters.
- Avoid generic AI prose, inflated metaphors, repetitive rhetorical questions, and unsupported predictions.
- End with a source-grounded implication or open question, not a new thesis.

For news, distinguish event chronology from analysis. For interviews, preserve speaker attribution and follow the source's argumentative sequence unless a clearer thematic reorganization remains traceable.

## GADE topic substance and narrative gate

For GADE research and practice features aimed at curious readers outside the AI industry, evaluate substance before committing to a long article. Identify what happened, why it matters, and the concrete actions, observations or outcomes available to explain it. A topical title, benchmark score, framework or capability claim alone is not enough. If the source mainly supports definitions and qualifications, prefer a shorter item or explain that the topic needs stronger material; do not stretch it into a feature. Do not require every format to have a discovery story: a useful comparison or practical explanation can qualify when it delivers concrete reader value.

Use the reader-approved Claude biological-system rewrite as an editorial pattern, not a mandatory subject or template:

- Open with what was found or achieved and why readers should care. Add background only when needed to understand the next action.
- Follow one main thread. In a discovery feature, this may be `initial question → investigation → unexpected observation → verification → what remains unknown`. Each section should advance that thread instead of introducing another technical discussion.
- Explain specialist terms at the moment they become necessary. Describe the action and meaning first; avoid stacks of unfamiliar nouns or acronyms. Readers should not need to learn an entire field before understanding the result.
- Make substance come from what someone did, what they observed, and what followed. Keep numbers only when they help readers assess scale or evidence; avoid detailed agent configurations, test ratios and methodological branches that interrupt the central account.
- Retain limitations that change the conclusion, integrated where the evidence is explained. Consolidate routine process disclosures in the source note; never simplify by making the result more certain.
- Let GADE's perspective appear through a specific research or application question. Do not append a generic paragraph about expert value or force every article to serve customer acquisition.

Before HTML formatting, read the article continuously as a reader unfamiliar with the field. Can they explain what happened, how it happened and what the evidence establishes without rereading? If not, rebuild the sequence and remove detours rather than merely shortening sentences. Do not treat publication-ready formatting as evidence that the article is readable.

## Chinese readability and editorial voice

Write natural Chinese for curious readers, including people outside the AI industry. Preserve technical precision, but explain ideas through actions and situations before naming abstractions.

- Prefer concrete subjects and verbs. For example, explain `任务状态` as `已经做了什么，接下来从哪里继续`, and `完成标准` as `怎样才算做完`. Keep a technical term when it adds precision; do not mechanically replace every term with colloquial wording.
- Organize around one reader question. A concrete example can connect several sections when it helps; do not force a recurring example into every article. Mark an invented scenario as hypothetical at its first use, and never imply it was demonstrated by the source.
- Use headings that express the section's actual issue, such as `昨天没做完，今天从哪里接着做？`, rather than stacks of abstract nouns. Vary headings; not every heading needs to be a question.
- Remove translation-like phrasing and empty analytical bridges such as `这提供了一个观察窗口` or `这把一个判断问题带到了产品里` when the next sentence can state the point directly.
- Integrate GADE's perspective through a specific question or implication. Avoid repeatedly asserting the value of experts without explaining what judgment they contribute.
- Before formatting, read the draft as continuous Chinese prose. Check unclear subjects, long noun phrases, abrupt transitions, repeated explanations and sentences a reader must reread. Improve the article's argument and language, not just sentence length.

## Attribution without repeated caveats

Keep claim-level attribution and material limitations: `Meta 表示`, an unknown experimental outcome, a research-preview status, or a known failure may be necessary to understand the evidence.

Put editorial process disclosures (not independently tested, video coverage, verification cutoff, source access) in the closing source note by default. Do not repeatedly interrupt the body with generic reminders such as `上述设计是公司公布的方案，不能据此认定实际使用已经没有问题`, `公开说明不能替代独立验证`, or `这个例子不是产品实测` once the source attribution and hypothetical status are already clear. If a sentence would otherwise mislead, qualify that sentence specifically instead of adding a blanket disclaimer.

Removing redundant caveats must never strengthen a company claim into an established fact or remove a limitation material to the article's conclusion.

## Title package

Return one recommended title and four genuinely different alternatives:

1. Core fact or question.
2. Mechanism or explanatory angle.
3. Person, organization, or product angle when central.
4. Grounded tension or contrast.
5. Restrained implication.

Prefer specificity over hype. Avoid unsupported superlatives, fake breaking-news language, and stronger certainty than the source.

## Summary

Write one 60–120 Chinese-character summary that adds context rather than repeating the title. Identify the source and central mechanism when useful. Do not add promotional conclusions.

## Source notes

For a public video:

```text
本文根据【平台/栏目】视频《【标题】》的公开字幕与视频内容整理改写。为便于阅读，对访谈内容进行了结构化编辑与语言精简，未改变嘉宾原意；如有时间点或术语歧义，以原视频为准。
```

For a news or official article:

```text
本文根据【发布方】于【日期】发布的《【标题】》整理改写，并参考文中链接及相关权威资料核查人物、时间、数字与公告。为便于阅读，对信息结构和表述进行了重新组织；涉及公司观点、案例效果与预测的内容均保留发布方归属。
```

For supplied text:

```text
本文根据用户提供的《【标题】》原文整理改写。为便于阅读，对段落结构与语言表达进行了编辑，未增加与原文无关的结论。
```

When coverage is partial, replace the complete-source wording with an explicit limitation.

## Publishing package

Keep these fields in one article Markdown file:

```text
推荐标题：
备选标题：
摘要：
作者建议：
封面图与制作说明：
完整正文：
正文配图计划：
来源说明与引用：
未解决问题：
```

Keep the final HTML limited to the article body. The native WeChat title, author, summary, cover, original/reprint declaration, and account card stay outside the HTML.

## Traceability QA

Maintain an internal map:

| Article section | Source location | Main source points | Verification/additions |
|---|---|---|---|

Pass only if:

- every substantive article claim has a source location or external citation;
- every material source section is represented or deliberately excluded with a reason;
- facts, quotations, company claims, and publisher opinions remain distinguishable;
- qualifiers, disagreement, and uncertainty are retained;
- names, roles, dates, numbers, and quotations are consistent;
- the conclusion introduces no unsupported thesis.

## HTML QA

- no Markdown markers, heading syntax, or fenced code remain;
- all styling is inline;
- opening and closing tags balance;
- title and summary are not repeated inside the body;
- body uses readable mobile typography and has no horizontal overflow;
- the `GADE Insights` divider uses selectable text and survives clipboard transfer;
- no fake account card or production placeholder appears;
- local images are delivered separately unless the user explicitly requests embedded remote images;
- source note and closing block are present unless the user opts out.

## Delivery report

Report coverage as `完整`, `接近完整`, `部分`, or `受阻`. Name the actual source material accessed. List final file paths, image provenance, cover crop status and score, unresolved facts, and any rights caveat. Explain that users should open the HTML in Safari or Chrome, copy the rendered page, paste it into WeChat, then upload cover and body images separately.
