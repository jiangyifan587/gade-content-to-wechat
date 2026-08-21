# GADE 公众号排版规范

## Visual system

The colors below define the article HTML and optional brand accents. They do not require every cover or body image to use the GADE palette. For editorial imagery, choose a topic-led palette first and use GADE green or terracotta only when they support the subject.

- Warm ivory reference background: `#F3F1E8` for image assets only.
- Primary forest green: `#174A3A`.
- Accessible on-page green accent: `#2F7B65`.
- Near-black green: `#17241F`.
- Body gray: `#595959`.
- Secondary gray: `#888888`.
- Muted terracotta accent: `#C87959`.
- Divider gray: `#A6AAA8`.
- Avoid blue-purple neon, glossy AI imagery, gradients, and large colored text blocks.

For article HTML, keep the background transparent/white so WeChat dark mode can adapt. Do not force a white body background inside content blocks.

## Layout tokens

| Element | Specification |
|---|---|
| Content width | `max-width:677px` |
| Horizontal padding | `22px` |
| Body font | system sans-serif / PingFang SC |
| Body size | `16px` |
| Body line height | `1.95` |
| Body tracking | `0.04em` |
| Body color | `#595959` |
| Paragraph gap | `24px` |
| Section top gap | `42px` |
| Section heading gap | `20px` |
| Section number | `12px`, `0.18em`, `#C87959` |
| Section heading | `19px`, `1.65`, weight `600`, `#262626` |
| Source note | `13px`, `1.85`, `#888888`, top rule |

Use justified text for the body and centered text only for dividers and closing CTA.

## Paragraph rules

- Merge adjacent sentences that advance the same idea.
- Prefer 2–3 sentences per paragraph; do not exceed roughly 5 mobile lines unless necessary.
- Keep rhetorical questions separate only when they deserve a pause.
- Do not turn every source line break into a paragraph break.
- Keep lists of conceptual steps readable; use bold lead-ins inline rather than one paragraph per label.

## Emphasis rules

- Use terracotta for at most one key opening sentence or selected section number.
- Use dark semibold text for definitions and decisive conclusions.
- Do not combine orange, green, and bold on the same sentence.
- Avoid more than one emphasized paragraph in a section.

## Standard opening

Use a centered divider with two thin gray lines, `GADE Insights`, and a second line `GADE Union 发布`. Default vertical margins: `34px 0 38px`.

Do not repeat the article title or summary inside the body.

## Standard closing

Use the following wording unless the user supplies alternatives:

```text
如果这篇文章对你有启发
欢迎「点赞」「转发」「推荐」
也欢迎在评论区留下你的看法

— 完 —

✦ 点亮星标 ✦
和 GADE 一起追踪 AI 与科学的下一步
```

Style the green rule at `62%` content width, centered, `3px`, color `#2F7B65`. Keep the account card outside the HTML; it is a WeChat-native component.

## Long-article image rhythm

For articles with 8 or more sections, recommend three images:

1. After the conceptual setup or section 02.
2. Near the midpoint, typically after section 05.
3. Before the final analytical turn, typically after section 08.

Images should be editorial, restrained, and consistent with the selected topic palette and with one another. GADE green may appear as an accent but is not required. Do not insert generic AI brains, robots, neon circuitry, or decorative stock technology.

## QA checklist

- Compare the first screen with the target reference: title area remains native WeChat UI; article body begins with the divider.
- Check that no paragraph is isolated merely because the source had a line break.
- Check that orange is muted terracotta, not bright red-orange.
- Check that the footer rule is not full width.
- Review mobile screenshots when possible; desktop preview alone is insufficient for final spacing judgment.
