---
description: "Interactive design review — discuss information hierarchy, content, and CTAs for an iOS screen, then audit"
argument-hint: "[screenshot-path]"
---

You are conducting an interactive design review of an iOS screen. Unlike the design-audit command (which produces a report immediately), this review is a guided conversation. You will discuss the screen's purpose, information architecture, and calls-to-action with the user BEFORE producing any audit output.

## Step 1: Gather Inputs

The user provided: $ARGUMENTS

- If that looks like a file path (ends in .png, .jpg, .jpeg, .heic, or similar), read it as a screenshot in the next step.
- If it's a description of a screen, note it and ask the user for a screenshot file path. Explain that screenshot + code together produces the strongest review, but you can proceed code-only if they prefer.
- If empty, ask the user what screen they want reviewed and whether they have a screenshot.

## Step 2: Read Screenshot + Locate Code

If a screenshot path was provided, use the Read tool to view the image file. Also locate SwiftUI source files:
- Ask the user which view files implement this screen, or search:
  - Glob for `**/*View.swift`, `**/*Screen.swift`, `**/*Page.swift`
  - Grep for view names or text strings visible in the screenshot
- Read all relevant view files and shared components they reference.

Analyze silently — form initial observations but do NOT output findings yet. The next three steps are a dialogue.

## Step 3: Information Architecture Dialogue

Use AskUserQuestion to walk through these questions one at a time. Each follow-up should build on the user's previous answer. Do NOT dump all questions at once — ask one, discuss, then move to the next.

Questions to cover (adapt based on the conversation):

1. **Purpose**: What is this screen's single purpose? Does the current layout serve that purpose, or is it pulled in multiple directions?
2. **Information ranking**: What information is shown on this screen? Walk through each element — what's most important to the user? What's least?
3. **Missing or excess**: Is anything missing that the user needs to act or decide? Is anything present that they don't actually need here?
4. **Competing elements**: Are there items competing for attention that shouldn't be? Does the visual weight match the information priority you just described?

## Step 4: CTA & Interaction Dialogue

Continue the conversation with AskUserQuestion, one question at a time:

1. **Action inventory**: How many actions can the user take on this screen? Which one is the primary action?
2. **CTA clarity**: Is the primary action obvious without reading labels? Could someone guess what to tap just from visual weight and position?
3. **Redundancy**: Are any actions redundant or confusing? Could any be removed or combined?
4. **Hierarchy of actions**: Are destructive or secondary actions properly de-emphasized relative to the primary action?

## Step 5: Content Density Dialogue

Continue the conversation with AskUserQuestion, one question at a time:

1. **Scope**: Is this screen trying to do too much? Could it be split into two screens that each do one thing well?
2. **Sufficiency**: Is there enough context for the user to act confidently, or are they left guessing?
3. **Order**: Does the information order match the user's mental model and task flow? Would rearranging elements better serve how people actually use this?

## Step 6: Synthesize & Transition to Audit

Summarize the key decisions and direction that emerged from the dialogue. Present this summary to the user and confirm it captures what was discussed.

Then transition: "Now I'll run the technical audit filtered through what we just discussed."

Run the 12-dimension audit (same dimensions as design-audit):
1. Visual Hierarchy
2. Spacing & Rhythm
3. Typography
4. Color
5. Alignment
6. Components
7. Iconography
8. Motion & Animation
9. Empty / Loading / Error
10. Dark Mode + Glass
11. Adaptive Layout
12. Accessibility

Cross-reference visual findings from the screenshot with code. But filter and prioritize based on the decisions made in the conversation — the dialogue should shape which findings matter most.

## Step 7: Output Phased Plan

Structure findings as a phased improvement plan. Recommendations should reflect the shared understanding from the dialogue, not just technical observations.

### Phase 1: Critical (Functional / Usability Issues)
Issues that affect usability or correctness. Each item: exact file, line range, the problem, the concrete SwiftUI fix.

### Phase 2: Refinement (Visual Quality)
Issues that affect visual polish. Same format: file, line, problem, fix.

### Phase 3: Polish (Delight)
Opportunities for animation, transitions, haptics, and micro-interactions.

## Step 8: Confirm Before Acting

Present the full plan to the user. Ask which phases or items they want you to implement. Do NOT make any code changes until the user approves.
