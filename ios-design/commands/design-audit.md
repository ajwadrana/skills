---
description: "Audit an existing iOS screen's UX design using screenshot + code analysis"
argument-hint: "[screenshot-path-or-description]"
---

You are performing a structured UX design audit of an existing iOS screen. Follow these steps exactly:

## Step 1: Gather Inputs

The user provided: $ARGUMENTS

- If that looks like a file path (ends in .png, .jpg, .jpeg, .heic, or similar), read it as a screenshot in the next step.
- If it's a description of a screen, note it and ask the user for a screenshot file path. Explain that screenshot + code together produces the strongest audit, but you can proceed code-only if they prefer.
- If empty, ask the user what screen they want audited and whether they have a screenshot.

## Step 2: Read the Screenshot

If a screenshot path was provided, use the Read tool to view the image file. Analyze it for:
- Visual hierarchy: What draws the eye first? Is the primary action obvious?
- Spacing and alignment issues
- Color usage and contrast problems
- Typography hierarchy
- Missing states (empty, loading, error)
- Any anti-slop patterns (generic gray cards, unstyled lists, etc.)

Write down your visual findings before looking at any code.

## Step 3: Locate SwiftUI Source Files

Ask the user which view files implement this screen. If they're unsure, search the project:
- Glob for `**/*View.swift`, `**/*Screen.swift`, `**/*Page.swift`
- Grep for view names or text strings visible in the screenshot

## Step 4: Read the Source Files

Read each relevant SwiftUI file. Also read any shared components they reference (custom view modifiers, reusable subviews, theme/style files).

## Step 5: Cross-Reference and Audit

For each visual issue found in the screenshot, locate the responsible code (specific file, line, modifier).
For each code smell found in the source, check whether it manifests visually.

Evaluate across all 12 audit dimensions from the ios-design skill:
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

## Step 6: Output Phased Plan

Structure findings as a phased improvement plan:

### Phase 1: Critical (Functional / Usability Issues)
Issues that affect usability or correctness. Each item must specify the exact file, line range, the problem, and the concrete SwiftUI fix.

### Phase 2: Refinement (Visual Quality)
Issues that affect visual polish. Same format: file, line, problem, fix.

### Phase 3: Polish (Delight)
Opportunities for animation, transitions, haptics, and micro-interactions.

## Step 7: Confirm Before Acting

Present the full plan to the user. Ask which phases or items they want you to implement. Do NOT make any code changes until the user approves.
