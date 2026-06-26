# 🔍 AI-Powered Resume Screening & Ranking System

An explainable NLP system that automatically screens, scores, and ranks resumes against a job description — built as part of the Future Interns Machine Learning Task 3 (2026).

## 📌 Problem Statement

Hiring teams receive hundreds of resumes per role. Manual screening is slow, inconsistent, and error-prone. This project builds a decision-support ML system that:

- Extracts skills from unstructured resume text
- Compares each resume against a job description
- Ranks candidates by role fit
- Explains *why* each candidate ranked where they did — not just a black-box score

## 🚀 Why This Isn't Just "TF-IDF + Cosine Similarity"

Most resume screeners stop at one similarity number. This system uses a **Hybrid Explainable Scoring Engine** that combines three transparent signals so every score can be audited by a non-technical recruiter:

| Signal | Purpose | Weight |
|---|---|---|
| **Weighted Skill Match** | Exact skill-gap detection using a skill taxonomy with alias matching (e.g. "ML" = "Machine Learning"). Required skills weighted 2x preferred skills. | 50% |
| **TF-IDF Semantic Similarity** | Catches skills phrased differently than the taxonomy expects | 30% |
| **Experience Match** | Regex-extracted years of experience vs. JD minimum | 20% |

Each candidate's final score breaks down into these three components, plus a list of exactly which required/preferred skills are missing — e.g.:
