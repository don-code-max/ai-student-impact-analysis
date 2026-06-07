# AI Impact on Students — Data Analysis Project

A full statistical analysis of how generative AI tool usage affects student academic performance, burnout risk, and the effectiveness of institutional AI policies.

**Dataset:** 50,000 student records | 16 columns  
**Tools:** Python (pandas, scipy, statsmodels, scikit-learn), VS Code  
**Report:** See `AI_Student_Impact_Analysis_Report.docx` for the full written findings

---

## The 3 Problems Analyzed

### Problem 1 — Academic Impact
**"Does AI tool usage actually improve student GPA, or does it vary by how they use it?"**

- One-way ANOVA on Primary_Use_Case and Prompt_Engineering_Skill vs GPA Change
- Tukey's HSD post-hoc test to identify which specific groups differ
- Multiple linear regression controlling for all variables simultaneously

**Key Finding:** How you use AI matters far more than how much you use it. Debugging/Troubleshooting produced the highest GPA improvement (+0.0485), while Direct_Answer_Generation was the strongest negative predictor (-0.0668). Weekly AI hours alone had no significant effect on GPA once behavior was controlled for.

---

### Problem 2 — Burnout & Wellbeing Risk
**"Which student profiles are at highest risk of burnout, and can we predict it early?"**

- Logistic regression to classify students into Low, Medium, or High burnout risk
- Confusion matrix evaluated against 10,000 unseen test students
- Feature importance chart to identify highest-risk profiles

**Key Finding:** STEM students in upper years with high perceived AI dependency and heavy traditional study loads are the highest-risk burnout profile. Model achieved 53% accuracy vs 33% random baseline across 3 categories.

---

### Problem 3 — Institutional Policy Effectiveness
**"Does the institution's AI policy actually influence student outcomes — and is it working?"**

- ANOVA on GPA Change and Skill Retention Score across policy groups
- Tukey's HSD to identify which specific policy pairs differ
- Chi-square test on Burnout Risk Level distribution across policies

**Key Finding:** Strict_Ban consistently underperforms — lowest GPA change, lowest skill retention, and highest proportion of High burnout students (29.8% vs 23.8%). Actively_Encouraged and Allowed_With_Citation produce statistically identical outcomes, meaning citation requirements preserve integrity without hurting students.

---

## Repository Structure

```
├── ai_student_impact_dataset_1.csv   # Source dataset (50,000 records)
├── Problem 1.ipynb                   # Academic impact analysis
├── Problem 2.ipynb                   # Burnout risk prediction
├── Problem 3.ipynb                   # Policy effectiveness analysis
├── AI_Student_Impact_Analysis_Report.docx  # Full written findings report
└── README.md
```

---

## Methods Summary

| Method | Used In | Purpose |
|---|---|---|
| One-way ANOVA | Problems 1 & 3 | Test whether group means differ significantly |
| Tukey's HSD | Problems 1 & 3 | Identify which specific group pairs differ |
| Multiple Linear Regression | Problem 1 | Isolate each variable's true effect |
| Logistic Regression | Problem 2 | Predict burnout risk category |
| Confusion Matrix | Problem 2 | Evaluate model accuracy on unseen data |
| Chi-Square Test | Problem 3 | Test association between policy and burnout distribution |

---

## Overall Conclusion

Across all three problems, a consistent pattern emerges: the quality and context of AI use drives outcomes, not the quantity. Students who use AI actively and skillfully — for debugging, with advanced prompting, in supportive institutional environments — outperform peers who use AI passively or under restrictive policies.
