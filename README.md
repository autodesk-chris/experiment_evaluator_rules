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
- Receive detailed scoring (out of 70 points)
- Get color-coded results (Green/Orange/Red)
- See specific recommendations for improvement

## 📋 What Gets Evaluated

### Problem Space (42 points)
- Outcome (4 pts)
- Trunk Problem (4 pts)
- Branch Problem (4 pts)
- Root Cause (10 pts)
- Supporting Data (10 pts)
- Hypothesis (10 pts)

### Solution Space (28 points)
- Prediction (10 pts)
- Learning Objective (2 pts)
- Test Variant (2 pts)
- Control Variant (2 pts)
- Audience (2 pts)
- Duration (2 pts)
- Success Criteria (2 pts)
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

---

Open this workspace in Cursor and paste your experiment content into a new chat to get started.
