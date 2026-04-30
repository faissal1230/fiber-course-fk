# Fiber Optics Course Website — Consolidated Product Requirements

This document consolidates the final functional and non-functional requirements for the Fiber Optics Course Website. It intentionally does **not** include implementation code. It is meant as a build brief for another developer or AI coding assistant.

## 1. Product Goal

Build a modern, interactive learning website for a beginner-to-medium-level course on telecom and fiber optics.

The goal is not only to inform the learner, but to build genuine engineering intuition. The course should help the learner understand how concepts connect across physical media, optical physics, components, FTTH architecture, testing, troubleshooting, and network operations.

The final product should feel like a premium learning product: structured, elegant, interactive, visually guided, and practical.

## 2. Scope

The site contains:

- A homepage with a live learning path and curriculum overview.
- Six course chapters.
- Foldable chapter sections.
- Chapter-specific learning visuals and interactive labs.
- Inline tooltip definitions for key terms.
- A chapter-specific “What’s next” bridge section.
- A card-based key terms section per chapter.
- A chapter quiz per chapter.
- A final course-wide exam on the homepage.

The course chapters are:

1. Telecom Foundations
2. How Optical Fiber Works
3. Fiber Components & Hardware
4. FTTH Network Architectures
5. Design, Testing & Troubleshooting
6. Optical Services & Operations

## 3. Functional Requirements

### 3.1 Homepage

The homepage must include:

- A hero section for “OpticalNet Academy” or equivalent course branding.
- A concise course promise: learning telecom and fiber optics like a network engineer.
- A “Live learning path” panel listing all six chapters.
- A curriculum area with chapter selection.
- A search field to search inside the currently selected chapter.
- A preview grid of the selected chapter’s sections.
- A button to open the full lecture page for the selected chapter.
- A dedicated final exam section on the homepage.

### 3.2 Routing and Navigation

- The app should support navigation between the homepage and individual chapter pages.
- Hash routing or equivalent lightweight routing is acceptable.
- Opening a chapter should scroll to the top of that chapter page.
- Returning to the homepage should be clear and easy.
- Chapter cards and learning path items should be clickable.

### 3.3 Chapter Page Layout

Each chapter page must contain:

- A large top hero panel with:
  - chapter number and title,
  - chapter summary,
  - chapter icon,
  - chapter learning path panel.
- The chapter learning path should be integrated into the main hero panel, aligned on the right.
- The learning path must fit in the hero panel without its own scrollbar.
- Only section names should be displayed in the hero learning path, without descriptions.
- A subtle progress rail on the left side of the screen for larger screens.
- Foldable section cards below the hero panel.
- A chapter-specific “What’s next” bridge.
- A card-based key terms section.
- A chapter quiz.

### 3.4 Foldable Sections

- Every chapter section must be foldable.
- Default chapter page view should show folded section cards, not all content fully expanded.
- Each folded section card should show:
  - section number,
  - section title,
  - short enough visual hierarchy to be scannable.
- Opening a section should reveal:
  - explanatory content,
  - at least one visual, diagram, lab, or interactive learning element.
- No section should contain only text.
- Section opening and closing should feel smooth and modern.

### 3.5 Left-Side Progress Rail

- On desktop, a subtle left-side vertical progress rail must show the user’s position in the chapter.
- The rail uses very thin minimalist grey bars.
- The active section bar turns the accent blue.
- The rail lives at the far left side of the viewport, outside the main learning content.
- On hover, the rail expands into a subtle navigation panel showing section names.
- The style must be minimalist, modern, and not distracting.

### 3.6 Chapter “What’s Next” Section

- Each chapter must end with a chapter-specific “What’s next” bridge.
- It must not use generic repeated text.
- It must explicitly explain:
  - what the next chapter is,
  - how the current chapter prepares for it,
  - why the next chapter matters.
- Chapter 6 should end with a “Course complete” bridge and suggest practice as the next step.

### 3.7 Key Terms Section

- Each chapter must include a key terms section.
- It must not be a plain list.
- It must use card-based visuals matching the overall UI.
- Cards should use the dark-blue theme against a white background.
- Clicking a term reveals the definition with a smooth transition.
- Cards should feel like part of the product, not an afterthought.

### 3.8 Inline Glossary Tooltips

- Add inline tooltips for key terms and abbreviations that have not yet been explicitly defined at that point in the course.
- Tooltip terms include, at minimum:
  - FTTH, PON, OLT, ONT,
  - APC,
  - SMF, MMF,
  - dB, dBm,
  - OTDR,
  - EDFA,
  - WDM, CWDM, DWDM,
  - OADM/OADMs, ROADM/ROADMs,
  - OTN, FEC,
  - SLA.
- Tooltips should appear only on key terms.
- Tooltips should appear only at the first occurrence of a term within a section, not every repeated occurrence.
- Tooltip UI:
  - term is highlighted subtly,
  - small info icon appears next to the term,
  - definition appears on hover/focus,
  - dark tooltip background,
  - light blue text,
  - rounded corners,
  - premium subtle style.

### 3.9 Visuals and Interactive Learning Labs

Every section needs a learning visual. The visual should fit the concept. Do not overuse the same template.

Use simple card visuals only for less complex sections. For more complex sections, use tailored interactivity.

Required or final accepted visual patterns include:

#### Chapter 1
- Signal journey lab: interactive flow from intent → bits → signal → path → meaning.
- Media comparison cards for copper, wireless, and fiber.
- Performance metrics lab with selectable service profiles and metric bars.
- Network layer diagnostic simulator.
- Network scale map showing growing blast radius.

#### Chapter 2
- Fiber cross-section diagram.
- Refraction/bend intuition visual.
- Total internal reflection diagram.
- Single-mode vs multimode propagation path visual.
- dB power intuition slider.
- Dispersion/pulse broadening diagram.
- Wavelength window spectrum map.

#### Chapter 3
- Fiber cable structure illustration.
- Connector/endface illustration and contamination reasoning.
- Splice process flow.
- Passive devices cards.
- Optic selection board.
- Field failure cards.

#### Chapter 4
- Chapter 4 is considered good and should not be changed unless explicitly requested.
- Existing Chapter 4 visuals include:
  - architecture decision map,
  - FTTH architecture comparison,
  - PON downstream/upstream traffic visualizer,
  - split ratio explorer,
  - centralized vs cascaded splitter placement,
  - cable plant map,
  - customer premises diagram,
  - testing implications panel,
  - architecture trade-off matrix.

#### Chapter 5
- Link budget mini tool.
- Route planning/corridor map visual.
- Measurement mode lab with sliders for source power and inserted loss:
  - mode switch between dB and dBm,
  - dB shows link loss ratio,
  - dBm shows absolute received power,
  - receiver in-range / too-low / too-high status.
- Interactive OTDR trace:
  - simplified realistic trace,
  - event points for launch connector, fusion splice, connector pair, fiber end/break,
  - hover/click event explanation,
  - event type displayed.
- Troubleshooting scope flow.
- Safety and receiver limits cards.

#### Chapter 6
- Residential FTTH service chain visual.
- Enterprise SLA design cards.
- Mobile transport dependency map:
  - clean top interaction rail,
  - no overlapping text and nodes,
  - selectable stages: radio access, fronthaul/midhaul, backhaul, timing,
  - stage detail and failure intuition.
- WDM/ROADM/OTN channel visual.
- Inventory vs telemetry operations lab.
- Future optics and automation cards.

### 3.10 “Check Yourself” Reasoning Boxes

- Many learning labs should include a “Check yourself” question.
- The answer must not be immediately visible.
- The learner must click a “Reveal reasoning” button to see the reasoning path.
- The answer should not merely give the answer; it should guide how to reason.
- The questions can be somewhat challenging, but they must be solvable using only:
  - basic prior knowledge,
  - content already covered in the course up to that point.
- Do not ask questions that require later-course knowledge unless the reasoning can be built from current knowledge.

### 3.11 Chapter Quizzes

Each chapter must include a short scenario quiz.

Requirements:

- Open in a modal popup.
- Multiple-choice questions.
- Immediate feedback after each submitted answer.
- Feedback box should be green/correct or red/incorrect.
- Questions must be chapter-specific, practical, and varied.
- Avoid lazy generic questions such as “What is the engineering implication of...”
- Questions should test:
  - theory,
  - applied reasoning,
  - troubleshooting intuition,
  - architecture implications,
  - practical engineering decisions.

### 3.12 Final Exam

The homepage must include a final exam section.

Final exam requirements:

- Opens in a modal popup.
- 20–35 questions; current target is 25.
- Multiple choice.
- Mix of:
  - theory,
  - independent reasoning,
  - scenario analysis,
  - OTDR trace interpretation,
  - link-budget intuition,
  - architecture trade-offs,
  - operations thinking.
- Learner can navigate freely between questions.
- No need to submit each question individually.
- No per-question feedback during the quiz.
- A final “Submit quiz” button appears on the last question.
- After submit:
  - show final score,
  - show a stylish scrollable review list,
  - show every question,
  - show submitted answer or “No answer selected,”
  - show correct answer,
  - show feedback for wrong or missing answers.
- The final quiz navigator:
  - must not show question wording,
  - should be a scrollable list,
  - each item should show only the question number and status,
  - statuses: Open, Answered, Correct, Review, No answer,
  - answered state should be light blue using the course accent,
  - current question should be clearly highlighted.
- The final exam popup scrollbar must be custom styled:
  - not default grey browser scrollbar,
  - dark glass-style track,
  - blue gradient thumb,
  - rounded pill shape,
  - subtle glow,
  - hover state,
  - consistent with the course accent.

## 4. Non-Functional Requirements

### 4.1 Visual Design

- Overall look: premium, modern, clean, minimalist.
- Theme:
  - dark navy / slate base,
  - accent blue `#41C3FF`,
  - white cards,
  - subtle light-blue backgrounds,
  - warm off-white page background.
- Avoid clutter.
- Use rounded cards, soft shadows, subtle borders, and spacious but not overly spaced layouts.
- Avoid designs that feel “in your face.”
- Visuals should be elegant, not childish.
- The card style is preferred, but not every visual should be a card grid.

### 4.2 UX Principles

- The learner should always know:
  - where they are in the chapter,
  - what section they are in,
  - how the current concept connects to earlier/later concepts.
- Use visual mental maps where helpful.
- Use interactivity to build intuition, not decoration.
- Interactions should be meaningful:
  - hovering/clicking should reveal conceptually useful information,
  - not merely highlight UI elements.
- The site should support independent reasoning:
  - ask questions,
  - hide reasoning until clicked,
  - guide the mental path to the answer.

### 4.3 Content Depth

- Explanations must not be too short.
- The course should elaborate enough to feel like real learning material, not slide notes.
- Use the provided learning material and fiber optics concepts deeply enough.
- Chapter 4 is the quality benchmark for both content and UX.
- Chapters 1, 2, 3, 5, and 6 should match Chapter 4’s level of seriousness and interactivity.
- Avoid repeated generic text such as identical “engineering takeaway” boxes.
- Each section’s learning support should be unique to its content.

### 4.4 Accessibility

- Interactive elements should be buttons where appropriate.
- Modals should have clear close buttons.
- Tooltips should be hover/focus accessible where possible.
- Color should not be the only indicator of state.
- Text contrast should remain strong on dark and light backgrounds.

### 4.5 Responsiveness

- Desktop layout should use two-column structures where helpful.
- Mobile layout should stack cleanly.
- Foldable cards should work on all screen sizes.
- The progress rail can be hidden on smaller screens.
- Final exam modal should remain usable on smaller screens, with internal scroll areas.

### 4.6 Maintainability

- Course content should be separable from layout/app logic.
- Requirements, content, glossary terms, quiz banks, and final exam questions should be maintainable as structured data.
- Avoid hard-coding UI logic into content where possible.
- Keep Chapter 4 stable unless explicitly instructed otherwise.

### 4.7 Testing / QA Expectations

At minimum, verify:

- Exactly six chapters exist.
- Each chapter has title, short title, summary, icon, gradient/theme, and sections.
- Each chapter has at least five sections.
- Every section has an associated learning visual/lab.
- Chapter 4 section content remains unchanged unless requested.
- Each chapter has key terms.
- Each chapter has a quiz.
- Final exam has between 20 and 35 questions.
- Final exam supports free navigation.
- Final exam shows no feedback before final submission.
- Final exam shows score and detailed review after submission.
- Tooltips appear only once per term per section.
- No default browser scrollbar appears in the final exam modal.
- No JSX/parser/runtime errors.
