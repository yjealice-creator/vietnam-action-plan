# Multilingual Action Plan Site Structure

Reference: https://yeolmiyang.github.io/kapa2026-poster/

## 1. Reference Site Structure

The reference page is a slide-style, single-page HTML document. It is not a normal scrolling article. Its structure is closer to an interactive presentation.

### 1.1 Shell

```md
Page Shell
- Sidebar navigation
- Language switch
- Main slide viewport
- Previous / next controls
- Mobile drawer navigation
- Floating contact button
- Modal layers
```

### 1.2 Slide Navigation

The sidebar groups slides into clear sections.

```md
Cover
- 1. Cover

Background
- 2. Background
- 3. Theory
- 4. Institutional Context

Research Design
- 5. RQ & Hypotheses
- 6. Data & Methods
- 7. Classification

Results
- 8. RQ1 - Partner Distribution
- 9. RQ2 - Tier Comparison
- 10. RQ3 - Policy Area
- 11. Regional Partner Composition
- 12. Evaluation Result Distribution

Conclusion
- 13. Conclusion
- 14. Limitations & Implications
```

### 1.3 Slide Anatomy

Each slide follows a repeated pattern.

```md
Slide
- Header
  - Section number
  - Korean title
  - English title
  - Slide number
- Body
  - Key message
  - Cards / tables / charts / figures
  - Interpretation note
  - Optional detailed modal
```

### 1.4 Readability Features

The reference page improves readability through:

```md
Readability System
- Fixed slide viewport for focused reading
- Sidebar table of contents
- Short slide titles
- One key message per slide
- Cards for grouped arguments
- Metric strips for numbers
- Tables for comparison
- Flow diagrams for process logic
- Timeline blocks for sequence
- Callout boxes for interpretation
- Modal windows for detailed classification rules
- Image lightbox for enlarged charts
- Mobile drawer for small screens
- Keyboard navigation with arrow keys
```

### 1.5 Language System Used

The reference page mixes two language techniques.

```md
Short UI Text
- data-nav-ko
- data-nav-en
- Text changes dynamically when language button is clicked.

Cover Text
- data-ko
- data-en
- Text is swapped in place.

Long Slide Body
- Korean body block
- English body block with class="en-body"
- CSS / JavaScript shows one body and hides the other.

Language State
- body.lang-ko
- body.lang-en
- setLang("ko")
- setLang("en")
```

For our site, this should be expanded to:

```md
body.lang-ko
body.lang-en
body.lang-vi

data-ko
data-en
data-vi

data-nav-ko
data-nav-en
data-nav-vi

.ko-body
.en-body
.vi-body
```

## 2. Recommended Structure For Our Action Plan Site

Our current material is not a research poster. It is an action-plan guide for a training program. So the structure should feel like a practical working guide, not an academic results deck.

```md
Vietnam Action Plan Site
- Cover
- Purpose
- Action Plan Logic
- Session Roadmap
- Team Workflow
- Worksheets
- Worked Examples
- Quality Criteria
- Final Presentation Standard
- Language / Print / Edit Tools
```

## 3. Proposed Page Sections

### 3.1 Cover

```md
id: cover
role: First impression and language entry point

Content
- Program name
- Page title
- Short description
- Language selector
- Edit / Save / Print / Download controls

Language
- Korean title
- English title
- Vietnamese title
```

### 3.2 Purpose

```md
id: purpose
role: Explain what the page helps participants do

Content
- Why action plans are needed
- What teams will produce
- What counts as a good action plan

Readability
- One key-question box
- 3 short cards
- Avoid long paragraphs
```

### 3.3 Action Plan Logic

```md
id: action-plan-logic
role: Show the full policy-design logic

Flow
1. Problem
2. Evidence
3. Options
4. Decision
5. Implementation
6. KPI / Risk
7. Presentation

Readability
- Horizontal or vertical flow diagram
- Each step has one sentence
- Use icons or step numbers
```

### 3.4 Session Roadmap

```md
id: session-roadmap
role: Connect training sessions to concrete outputs

Table Columns
- Session
- Team task
- Required output
- Checkpoint question

Rows
- AP 01 Topic Alignment
- AP 02 Problem Framing
- AP 03 Korea Lesson Translation
- AP 04 Options and Selection
- AP 05 Implementation Design
- Final Preparation
```

### 3.5 Team Workflow

```md
id: team-workflow
role: Tell participants how to work together

Content
- Individual issue note
- Team clustering
- Evidence request log
- Role division
- Draft review
- Final briefing rehearsal

Readability
- Timeline
- Role cards
- Output checklist
```

### 3.6 Worksheets

```md
id: worksheets
role: Give copy-ready templates

Worksheet Blocks
- AP 01 Individual Issue Note
- AP 02 Problem Statement Builder
- AP 03 Korea Lesson Translation
- AP 04 Policy Option Card
- AP 05 Implementation Roadmap
- Final Q&A Sheet

Features
- Copy button per worksheet
- Print-friendly formatting
- Language-specific worksheet labels
```

### 3.7 Worked Examples

```md
id: worked-examples
role: Show weak vs strong answers

Example Types
- Problem statement
- Option comparison
- KPI set
- Risk mitigation
- Decision request

Readability
- Two-column weak / strong comparison
- Highlight the improved part
- Keep examples short
```

### 3.8 Quality Criteria

```md
id: quality-criteria
role: Let teams self-check before presentation

Criteria
- Clear public problem
- Evidence-based diagnosis
- Vietnam institutional fit
- Adaptation from Korean cases, not copying
- Feasible implementation owner
- Measurable KPIs
- Risks and mitigation
- Clear decision request

Readability
- Checklist
- Rubric table
- Status chips: Ready / Needs work
```

### 3.9 Final Deck Standard

```md
id: final-deck
role: Define presentation order

Deck Flow
1. Title, team, and policy question
2. Problem definition and target group
3. Evidence and causes
4. Lessons from Korea and adaptation logic
5. Policy options and selection criteria
6. Preferred action plan
7. Implementation roadmap
8. Risks, KPIs, and expected results
9. Closing message and decision request
```

### 3.10 Appendix / Resources

```md
id: resources
role: Store detailed supporting material without crowding the main page

Content
- Definitions
- Frequently asked questions
- Glossary
- Download links
- Source document notes

Readability
- Accordion sections
- Search within glossary
- Modal for long explanations
```

## 4. Three-Language Content Model

Use one shared structure, but store text in three language fields.

```md
content:
  site:
    ko:
      title: "공공서비스 액션플랜 개발 기준"
      subtitle: "2026 베트남 공무원 연수 프로그램"
    en:
      title: "Public Service Action Plan Development Standard"
      subtitle: "2026 Vietnam Public Service Training Program"
    vi:
      title: "Tiêu chuẩn xây dựng kế hoạch hành động dịch vụ công"
      subtitle: "Chương trình bồi dưỡng công chức Việt Nam 2026"
```

Recommended language codes:

```md
ko: Korean
en: English
vi: Vietnamese
```

Recommended HTML state:

```md
<body class="lang-ko">
<body class="lang-en">
<body class="lang-vi">
```

## 5. Language Switching Rules

### 5.1 Short Text

Use data attributes for labels, buttons, table headers, and short sentences.

```html
<button
  data-ko="저장"
  data-en="Save"
  data-vi="Lưu">
  저장
</button>
```

### 5.2 Long Text

Use separate blocks for paragraphs, worksheets, examples, and tables.

```html
<section class="lang-block ko-body">한국어 본문</section>
<section class="lang-block en-body">English body</section>
<section class="lang-block vi-body">Nội dung tiếng Việt</section>
```

### 5.3 Navigation Text

Use separate navigation labels so the sidebar changes language too.

```html
<span
  data-nav-ko="워크시트"
  data-nav-en="Worksheets"
  data-nav-vi="Phiếu làm việc">
  워크시트
</span>
```

### 5.4 Language Persistence

```md
When user selects a language:
- Update body class
- Update all data-ko / data-en / data-vi text
- Show the matching long-body block
- Hide the other language blocks
- Save selected language in localStorage
- Optional: update URL query, e.g. ?lang=vi
```

## 6. Readability Rules By Language

### Korean

```md
CSS
- word-break: keep-all
- line-height: 1.65-1.75
- Avoid very long noun chains
- Use short headings
```

### English

```md
CSS
- word-break: normal
- line-height: 1.55-1.65
- Use active voice
- Avoid overlong policy sentences
```

### Vietnamese

```md
CSS
- word-break: normal
- line-height: 1.6-1.75
- Avoid all caps for long labels
- Allow slightly wider buttons because Vietnamese labels may be longer
- Check diacritics carefully
```

## 7. Recommended UI Features To Use

```md
Language
- Korean / English / Vietnamese segmented control
- Remember selected language
- Print current language only
- Download current language or all-language HTML

Readability
- Sticky header
- Left or top table of contents
- Section progress indicator
- Cards for concepts
- Flow diagram for action-plan steps
- Tables for session outputs
- Accordions for long templates
- Copy buttons for worksheets
- Modal for glossary / detailed notes
- Print stylesheet

Editing
- Edit mode toggle
- Save to browser localStorage
- Download edited HTML
- Reset local edits
- Optional warning that browser edits are local unless committed to GitHub
```

## 8. Recommended Markdown Content Outline

```md
# 2026 Vietnam Public Service Training Program

## Public Service Action Plan Development Standard

### 1. Purpose
- Why this guide exists
- What teams will produce
- What quality standard will be applied

### 2. Action Plan Logic
- Problem
- Evidence
- Options
- Decision
- Implementation
- KPI and risk
- Presentation

### 3. Session Roadmap
| Session | Team Task | Required Output | Checkpoint |
|---|---|---|---|

### 4. Team Workflow
- Individual preparation
- Team synthesis
- Evidence review
- Role division
- Final rehearsal

### 5. Worksheets
#### AP 01 Individual Issue Note
#### AP 02 Problem Statement Builder
#### AP 03 Korea Lesson Translation
#### AP 04 Policy Option Card
#### AP 05 Implementation Roadmap
#### Final Q&A Sheet

### 6. Worked Examples
- Weak vs strong problem statement
- Option matrix example
- KPI example
- Risk mitigation example

### 7. Quality Criteria
| Criterion | Ready | Needs Work |
|---|---|---|

### 8. Final Deck Standard
1. Title, team, and policy question
2. Problem definition and target group
3. Evidence and causes
4. Lessons from Korea and adaptation logic
5. Policy options and selection criteria
6. Preferred action plan
7. Implementation roadmap
8. Risks, KPIs, and expected results
9. Closing message and decision request

### 9. Appendix
- Glossary
- FAQ
- Source notes
- Download links
```

## 9. Implementation Priority

```md
Phase 1
- Add Korean / English / Vietnamese language switch
- Convert all visible labels to data-ko / data-en / data-vi
- Split long content into ko-body / en-body / vi-body

Phase 2
- Add table of contents
- Add copy buttons for worksheets
- Improve print layout

Phase 3
- Add glossary modal
- Add section progress
- Add language-specific downloads
```

