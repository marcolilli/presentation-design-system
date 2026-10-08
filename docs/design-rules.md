# Design Rules

This document describes the visual rules and reusable patterns for the presentation design system. Token values are defined in <code>css/tokens/</code>; the stylesheet is the source of truth.

## Visual principles

- Give each slide one idea and one main focal point.
- Treat the slide as a visual aid for a speaker. Keep on-slide wording concise; use the speaker's script for full explanations.
- Leave generous negative space. Aim for roughly half the canvas to remain visually quiet.
- Use type scale, contrast, and spacing for emphasis before adding decoration.
- Let a meaningful number, image, or simple diagram carry the main point.
- Use sentence case. Use one alignment system per slide: left-aligned content or a centered moment.
- Use a flat visual style. Avoid shadows, gradients, 3-D treatments, clip art, and decorative card chrome.
- Use one accent hue per slide. Jade is the default; a meaning-bearing topic hue can replace it for a section. Do not use the accent as decoration.
- Use Alert only for genuine danger, loss, failure, or risk.
- Use tabular numerals for all data figures.

The 15-word target for on-slide copy and the 50% negative-space target are guidelines to support clarity, not hard limits.

## Color

| Token | Value | Intended use |
|---|---|---|
| <code>--pds-color-paper</code> | <code>#FAFAF8</code> | Standard light slide background |
| <code>--pds-color-ink</code> | <code>#16181D</code> | Primary text and rules |
| <code>--pds-color-night</code> | <code>#0B0B0C</code> | Moment slides and full-bleed image ground |
| <code>--pds-color-jade</code> | <code>#00A878</code> | Default accent |
| <code>--pds-color-alert</code> | <code>#E5484D</code> | Genuine danger, loss, or risk |
| <code>--pds-color-mute</code> | <code>#8A8A8E</code> | Captions, sources, and secondary text |

Topic hues are muted and meaning-bearing. Give a section one hue and use it consistently for its label, highlighted keyword, and diagram accent: control <code>#128A6B</code>, silicon <code>#3A6AA0</code>, material <code>#8C6B38</code>, safety <code>#AC5A3C</code>, algorithm <code>#6A57A0</code>, or growth <code>#5E9A52</code>.

Paper is the normal slide ground. Reserve Night for occasional moment slides and full-bleed media. Full-bleed media may use one top or bottom scrim solely to keep overlaid text legible.

## Type and canvas

The design reference is 1920 × 1080 pixels in a 16:9 ratio. A 150px safe margin is used on all sides at reference size; the CSS scales the canvas and type proportionally.

The spacing scale at reference size is 4, 8, 12, 16, 24, 32, 40, 48, 64, 80, 96, 120, and 150px. The 150px token is also the standard canvas inset. Use a 64px footer baseline.

| Role | Reference size | Weight | Tracking |
|---|---:|---:|---:|
| Wordmark | 248px | 700 | −0.04em |
| Hero | 300px | 700 | −0.04em |
| Headline | 92px | 600 | −0.03em |
| Subhead | 60px | 600 | −0.02em |
| Support | 44px | 400 | −0.01em |
| Caption | 28px | 400 | 0 |

Use 1.00 leading for wordmarks and hero text, 1.06 for headlines and subheads, and 1.40 for body copy. Use a 0.18em tracking for uppercase labels. Inter is the Latin typeface; its font file and license are in <code>assets/</code>.

Source and slide-number footers sit at the bottom corners in Mute. Keep them small and consistent.

Rules use a 2px reference stroke. Default, subtle, and chip borders use Ink at 0.34, 0.22, and 0.16 opacity. The radius scale is 0, 4, 8, and pill; use rounded corners for pills only. The default shadow is none.

## Slide layouts

- **Title:** Large wordmark, short subtitle, and optional presenter/course details. Keep the composition quiet.
- **Headline:** One bold claim with a supporting sentence. A content slide can include up to three short supporting points; keep the right area open or use one simple figure.
- **Stats:** Two or three large tabular figures, each with a short muted descriptor.
- **Flow:** A full-width, left-to-right sequence with three or four nodes and thin arrow connectors. Accent the outcome node or the single most important step.
- **Chips:** A row or grid of bordered label/value pills for metadata such as categories, places, or dates. Do not add icons or color fills.
- **Attribute list:** Three to five rows, each with a bold term and a muted definition. Use at most one accented term.
- **Table:** Keep rows and columns few, use clear row and column headers, and align numeric values consistently. Separate rows with horizontal rules rather than boxing every cell.
- **Bullet list:** Keep one level of nesting when it clarifies a parent point. Use concise lead bullets and shorter indented details; if the list crowds the safe area, split it across slides instead of shrinking the type excessively.
- **Moment:** A centered question, statement, or single large number. Night is permitted for this layout.
- **Media / proof:** Use a full-bleed image, a text-and-image split, or a wall of two to four figures. Show real evidence and include an evidence label plus a concise caption.

Use a smaller headline when it shares a slide with a figure. Do not let a narrow text column compete with its image.

## Reusable patterns

- **Plain-language line:** One plain sentence below the headline for audiences with mixed expertise. Mark it with an accent rule and bold the key phrase.
- **Before / after comparison:** Pair the previous limitation with the current result. Keep the old state muted, the new state clear, and accent its defining phrase. Use “first” badges sparingly and only for claims that can be substantiated.
- **Summary line:** Put a one-line takeaway below a diagram so the audience reads the diagram first and then the conclusion.
- **Footnotes:** Use a superscript number in the content and a matching numbered note at the lower left of the safe frame. Keep notes concise and visually separate from the slide-number and source footer.

Place comparison and summary patterns inside the slide's padded content frame. Their positions then follow the same safe inset as the headline and supporting content.

## Data, diagrams, and icons

- Label chart lines and bars directly. Avoid gridlines, chart borders, and legend boxes.
- Use one accented data series; keep secondary series muted.
- Use tables only for directly comparable details. Keep labels concise, align numbers with tabular numerals, and avoid vertical rules or decorative cell fills.
- Use simple single-weight line icons in Ink or Mute, at most one per slide. Avoid filled or multicolor icon sets.
- Keep flow diagrams directional and concise. Let the connectors occupy the space between nodes rather than adding containers around every step.
- Use tabular numerals so values do not shift as their digits change.

## Evidence images

Use real renders, CAD, PCB, prototype, app, or screenshot evidence when a slide makes a claim about something built or observed. Tag the image with its evidence type and add a one-line caption.

- **Full-bleed:** The image is the slide. Use Night as the letterbox ground; use <code>contain</code> to show the whole object or <code>cover</code> to fill the frame.
- **Split:** Keep explanatory text on the left and one framed figure on the right.
- **Proof wall:** Arrange two to four framed figures in one row and caption every figure.

Frames use hairline borders without shadows or rounded corners. A scrim is allowed only when a caption overlays a full-bleed image.
