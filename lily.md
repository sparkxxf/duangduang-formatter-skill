# Project consensus (lily.md)

This file records the **state the project has agreed on**—not chat summaries. Lily updates it incrementally after tasks and uses it to check consistency across the project.

---

## Current phase

`wrap-up`

---

## Confirmed assumptions

- **Skill Purpose**: Bridging the "last mile" between AI output and Microsoft Word for professional formatting.
- **Output Format**: Standard HTML 5 code blocks optimized for copy-pasting into Word.
- **Styling Specs**: H1 (18pt, Center, Microsoft YaHei, 35pt LH), H3 (15pt, Left, Bold, Chinese numerals), P (12pt, Justified, 25pt LH), Strong (Red #FF0000).
- **Constraints**: No emojis, professional tone, use existing PDF/DOCX/XLSX skills for extraction.

---

## Rejected assumptions

- **Pure Markdown Output**: Rejected in favor of HTML for better formatting persistence in Word.
- **Emoji Usage**: Explicitly rejected to maintain academic/business professionalism.

---

## Stable invariants

- **Skill Name**: `duangduang-formatter`
- **Output Path**: `/Users/spark/Documents/MyLily/CreateSkills/duangduang-formatter.skill`
- **Logic**: Integrated processing (extract from files -> format to HTML).
