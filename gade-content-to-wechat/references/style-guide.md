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

The `22px` horizontal padding controls the local HTML preview. It is not a guarantee that WeChat will preserve an equivalent inset after browser copy and paste.

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

## WeChat paste and manual two-side indentation

WeChat may preserve inline text styles, centering, and borders while discarding layout techniques used to simulate side indentation. In validated mobile previews, outer padding, per-block margins or padding, percentage-width centered blocks, transparent side borders, and three-cell spacer tables did not reliably preserve the requested inset. Treat this as editor sanitization, not as a reason to widen the footer rule or layer on more CSS hacks.

If the user wants a native two-side indentation value such as `8`, keep the complete HTML and additionally provide:

1. `*-body-only.html`: GADE opening divider, every article section, and the source note.
2. `*-footer-only.html`: engagement prompt, green rule, `— 完 —`, star prompt, and community CTA.

Use `assets/wechat-body-only-template.html` and `assets/wechat-footer-only-template.html`. The split boundary is immediately after the source note and before `如果这篇文章对你有启发`. Paste body-only first, select only that material in WeChat, and apply the native indentation. Paste footer-only afterward without selecting or re-indenting the full article. This preserves the footer's centered layout and keeps its `62%` green rule from shrinking.

Do not include the title, summary, author, cover, original/reprint declaration, or account card in the split files; those remain native WeChat fields or components. Do not use split delivery when the user has not asked for manual indentation and the normal complete HTML already pastes correctly.

## Optional body images

Default to a text-only body with a separate cover. Do not prescribe an image count from the number of article sections. Produce body imagery only when requested; when an authentic evidence image or a diagram would materially improve understanding, briefly suggest its purpose rather than creating it automatically.

When the user asks for no body images, omit image placeholders, captions, insertion instructions and separate body-image files. This preference does not remove the cover unless the user also requests that.

For requested body images, follow `visual-workflow.md` and keep the imagery relevant and restrained.

## QA checklist

- Compare the first screen with the target reference: title area remains native WeChat UI; article body begins with the divider.
- Check that no paragraph is isolated merely because the source had a line break.
- Check that orange is muted terracotta, not bright red-orange.
- Check that the footer rule is not full width.
- For split delivery, verify that body-only plus footer-only reproduces the complete HTML's visible text in the same order, with balanced tags and no duplicated source note or CTA.
- Review mobile screenshots when possible; desktop preview alone is insufficient for final spacing judgment.
