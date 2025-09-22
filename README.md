# Experiment Evaluator - Cursor Rules

Transform your experiment evaluation process using Cursor's AI-powered rules engine. This workspace contains evaluation criteria that automatically assess experiment quality when you upload experiment documents.

## 🚀 Quick Start

### 1. Open This Workspace in Cursor
- Clone or download this repository
- Open the folder in Cursor
- The `.cursor/rules/` files will be automatically detected

### 2. Upload Your Experiment
- Copy your experiment content (TXT, DOCX, or plain text)
- Paste it into a new Cursor chat
- Ask: "Please evaluate this experiment using the evaluation rules"

### 3. Get Instant Feedback
- Receive detailed scoring (out of 90 points)
- Get color-coded results (Green/Orange/Red)
- See specific recommendations for improvement

## 📋 What Gets Evaluated

### Problem Space (56 points)
- Outcome (2 pts)
- Trunk Problem (2 pts)
- Branch Problem (2 pts)
- Root Cause (20 pts)
- Supporting Data (10 pts)
- Hypothesis (20 pts)

### Solution Space (34 points)
- Prediction (10 pts)
- Learning Objective (2 pts)
- Test Variant (2 pts)
- Control Variant (2 pts)
- Audience (2 pts)
- Duration (2 pts)
- Success Criteria (8 pts)
- Data Requirements (2 pts)
- Considerations (2 pts)
- What Next (2 pts)

## 📁 Key Files

- `.cursor/rules/experiment-evaluator.mdc`
- `.cursor/rules/problem-space-rubric.mdc`
- `.cursor/rules/solution-space-rubric.mdc`
- `.cursor/rules/scoring-format.mdc`
- `samples/sample-experiment.txt`

## 🔄 How It Works

The Cursor Rules system uses AI to:
1. Parse your experiment into required sections
2. Apply scoring criteria for each section
3. Provide detailed feedback with recommendations
4. Calculate overall score and color rating

### Important scoring rules
- Total possible score: 90 points (Problem Space 56 + Solution Space 34)
- Binary checks (Outcome, Trunk Problem, Branch Problem): 0 or full points only
- Success Criteria: graded on an 8-point rubric; if no quantitative values are provided for metrics, the maximum score is capped at 2/8

### Evaluation rules and constraints
- Section scope lock: Each section is scored strictly from its own content. Cross-section references are only allowed where explicitly stated in the rules.
- Allowed dependencies (summary):
  - Hypothesis ↔ Root Cause (alignment) and ↔ Supporting Data (consistency)
  - Prediction ↔ Hypothesis (alignment)
  - Success Criteria ↔ Learning Objective (alignment)
  - Data Requirements ↔ Success Criteria (metric alignment)
  - What Next may optionally reference Success Criteria for clarity
- Evidence quoting: Every scored sub-criterion includes at least one verbatim quote from an allowed source, labeled with the section name.
- Binary enforcement: Binary sections use {0, max} only; no partial credit.
- Heuristic warnings (non-scoring):
  - Multi-variant test: Triggered when Test type indicates more than two arms (e.g., “A/B/C vs Control”, “A/B/C/D”). Emitted text: "This test probably has too many variations to test effectively".
  - Root cause quality: Emitted if Root Cause scores < 16/20. Text: "Your root cause problem scored low. This suggests a lack of clarity as to the problem you need to solve."
- Response format (high level): Overall Score, Color Classification, Warning(s) if any, Section-by-section breakdown (score, rationale, quotes, recommendations), and a brief strengths/areas-for-improvement summary.

### Tips
- When asking the AI to evaluate, include the phrase: "Use the workspace evaluation rules"
- Keep your brief structured by the 16 sections for best results

---

Open this workspace in Cursor and paste your experiment content into a new chat to get started.
