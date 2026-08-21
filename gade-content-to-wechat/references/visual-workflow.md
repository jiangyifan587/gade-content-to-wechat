# 标题、摘要、封面与正文配图工作流

## Contents

- Title package
- Summary
- Cover source hierarchy
- Default cover art direction
- Generation workflow
- Cover self-scoring loop
- Cover QA gate
- Body-image recommendations

## Title package

Return one recommended title and four alternatives. Make the five options genuinely different while staying inside the source:

1. Core-question angle.
2. Key-person or interview angle when the person is central.
3. Explanatory angle that names the mechanism or framework.
4. Tension/contrast angle grounded in the video.
5. Restrained long-term implication.

Prefer specificity over hype. Avoid unsupported superlatives, false certainty, invented breaking-news framing, `彻底颠覆`, `震惊`, `史上最强`, and claims that the source only presents as a possibility.

The recommended title should be concise enough to read comfortably on a phone. Preserve essential English names or acronyms when translating them would reduce accuracy.

## Summary

Write one publication-ready summary of 60–120 Chinese characters:

- identify the speaker/source and central subject when useful;
- state what the reader will understand after reading;
- include the article's main tension or mechanism;
- do not repeat the title word for word;
- do not introduce a stronger claim than the article;
- avoid empty promotional language.

## Cover source hierarchy

Choose the least synthetic route that still produces a strong, lawful cover:

1. User-supplied original photo, frame, diagram, or brand asset.
2. Official press/editorial/scientific imagery with clear usage and attribution requirements.
3. A carefully selected source-video frame when appropriate for commentary and the user accepts the source note.
4. An original image generated or illustrated specifically for the article.

Do not use a real person's generated likeness as a substitute for an available authentic photo. Do not fabricate a laboratory, scientific result, paper screenshot, company event, or news scene that readers could mistake for documentary evidence.

## Default cover art direction

Default to no embedded text and no GADE logo unless the user explicitly requests them. The native WeChat title supplies the words; the cover supplies atmosphere and subject.

Aim for:

- editorial photography or scientific-publication art direction;
- one central idea and clear visual hierarchy;
- natural or plausible light;
- tactile paper, glass, metal, laboratory, archival, or data textures when relevant;
- restrained negative space;
- authentic imperfections rather than hyper-polished surfaces;
- a topic-led palette derived from the source, subject matter, environment, or editorial mood;
- color continuity across the cover and body-image package, without requiring every article to reuse the same brand colors;
- GADE forest green `#174A3A`, warm ivory `#F3F1E8`, near-black green `#17241F`, and muted terracotta `#C87959` only when they serve the topic, or as an optional restrained accent.

Do not treat color matching as the main source of brand recognition. Preserve GADE continuity through editorial restraint, clear hierarchy, tactile realism, disciplined composition, and the surrounding article layout. Rotate palettes across articles when that improves subject fit and avoids a repetitive template look.

Avoid:

- humanoid robots, glowing brains, blue-purple neon, holograms, and circuit-board faces;
- floating particles, random glyphs, fake equations, fake interfaces, and illegible pseudo-text;
- waxy faces, plastic skin, exaggerated bokeh, over-sharpening, and HDR glow;
- overly symmetrical poster compositions and generic corporate stock scenes;
- implausible instruments, impossible glassware, inaccurate lab safety details, and ungrounded scientific diagrams;
- decorative gradients or 3D icons that do not explain the topic.

## Generation workflow

When a finished cover is requested and an image-generation/editing capability is available:

1. Derive two distinct concepts and suitable palette directions from the article, not from generic AI keywords or a fixed brand-color recipe.
2. Select the concept with the clearest editorial metaphor and lowest factual risk.
3. Generate a high-resolution master with enough negative space and safe margins for both a wide WeChat crop and a square share crop.
4. Default to no text; explicitly request no letters, captions, logos, watermark, interface, or symbols that could render as pseudo-text.
5. Inspect the rendered image at original detail and thumbnail size.
6. Check focal clarity, anatomy, faces, hands, equipment, diagrams, edge artifacts, texture, noise, and color balance.
7. Simulate or create both the wide and square crops. Keep the main subject away from fragile outer edges.
8. Run the cover self-scoring loop below. Treat the first render as a draft.
9. Revise or restart according to the score. Compare every new candidate with all earlier candidates; do not assume the newest is best.
10. Keep the master, rejected candidates, thumbnails, test crops, prompts, and score records in the task-scoped temporary directory only.
11. Deliver only the highest-scoring passing candidate as the final 900x383 wide cover and 1200x1200 square cover. Put the score and a short production note in the article Markdown; do not create separate cover documentation.

If no image-generation capability is available, provide a production-ready brief containing subject, composition, light, palette, texture, safe area, crop behavior, and an explicit avoidance list.

## Cover self-scoring loop

Evaluate rendered pixels, not the prompt or intended concept. Do not award points because the prompt requested a feature; award them only when the feature is clearly visible.

Before scoring every candidate:

1. Inspect the original image at full detail.
2. Inspect a 240px-wide thumbnail.
3. Inspect the final wide WeChat crop.
4. Inspect a square share crop.
5. List the three most visible weaknesses before assigning scores.

### Hard failures

Reject and regenerate immediately if any condition is true:

- pseudo-text, accidental letters, logo, watermark, or fake interface;
- a generated likeness substituting for a real person;
- fake scientific evidence, document, laboratory, event, or misleading instrument;
- broken anatomy, implausible equipment, malformed objects, or edge artifacts;
- no clear focal point at 240px thumbnail size;
- the focal subject is damaged by the wide or square crop;
- generic AI clichés dominate the image;
- the candidate repeats or closely resembles a visual direction the user already rejected.

A hard failure overrides the numerical score.

### Scoring rubric

Score every dimension from 0–10 and calculate `total = Σ(score / 10 × weight)`.

| Dimension | Weight |
|---|---:|
| Article and source alignment | 15 |
| Editorial originality and low-AI look | 25 |
| Focal hierarchy and thumbnail readability | 15 |
| Material, lighting, and factual plausibility | 15 |
| Wide and square crop robustness | 10 |
| Topic-led palette and editorial-series coherence | 10 |
| Technical integrity and absence of artifacts | 10 |

For every dimension, record the score, visible evidence, most important defect, and one actionable improvement.

### Decision thresholds

- `PASS`: total at least 88, every dimension at least 7, `editorial originality and low-AI look` at least 8.5, and no hard failure.
- `REVISE`: total 80–87.9 with no hard failure. Keep the concept, make one targeted change, and regenerate.
- `RESTART`: total below 80 or any hard failure. Abandon the composition and use the second concept.
- Generate at most 3 candidates by default.
- Deliver only the highest-scoring passing candidate.
- If no candidate passes after 3 attempts, mark the cover `未通过自动质检`, provide the best candidate only as a draft, and do not claim that the cover is finished.
- Keep this evaluation record internal by default. Do not save or deliver it as a scorecard file unless the user asks.

Use this evaluation record:

```text
候选：
硬性淘汰项：
主题匹配：
低 AI 感与编辑原创性：
缩略图焦点：
材质与真实性：
裁切适配：
主题配色与系列一致性：
技术完整性：
加权总分：
三个主要缺陷：
下一步动作：PASS / REVISE / RESTART
下一轮只修改：
```

## Cover QA gate

The cover passes only when all are true:

- the topic is legible without text;
- the image has one clear focal point at small size;
- it reads as editorial/scientific visual communication, not generic AI art;
- no accidental pseudo-text, logo, watermark, or fake interface is present;
- any person is authentic or intentionally non-identifiable and anatomically credible;
- equipment and scientific elements are plausible enough for the article's domain;
- both wide and square crops work without cutting the focal subject;
- the topic-led color and contrast remain readable in WeChat light and dark surroundings;
- the file/result is delivered at high enough resolution for the platform's current crop;
- source, license, or generated-image status is documented.

## Body-image recommendations

Recommend 1–3 images based on article length and information needs. Each recommendation must include:

```text
插入位置：
叙事作用：解释 / 证据 / 转场 / 人物 / 机制图
画面主题：
构图与比例：
主题配色与系列一致性：
实现方式：实拍/授权素材、视频截图、信息图、原创插画或生成图
文字策略：默认无字；如为信息图，仅保留必要标签
图注与来源：
避免事项：
```

Prefer images that add information:

- a speaker or historical scene with a verifiable source;
- a simplified mechanism diagram derived from the article;
- an authentic research object, material, instrument, or environment;
- a restrained editorial metaphor for an abstract concept;
- a timeline, comparison, or closed-loop diagram when relationships matter.

Do not fill every section with decoration. For articles with eight or more sections, three well-spaced images are usually enough.
