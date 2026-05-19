College Readiness as a Predictor of College Completion
A Population-Level Analysis | Classes of 2016–2025

1. Study Overview
This analysis examines whether a school's existing college readiness designation —
defined by two measurable criteria — meaningfully predicts whether a student ultimately
graduates from college within six years of high school graduation.
The study serves two parallel purposes:

Institutional: Evaluate the operational validity of the college readiness metric
currently in use, and generate projected graduation likelihoods for classes not yet
far enough out to have observed outcomes.
Academic: Demonstrate the application of resampling-based statistical methods
(permutation testing and bootstrapping) in an educational outcomes context, with
careful attention to the implications of working with a full population rather than
a sample.


2. Dataset Structure
The dataset contains one row per student across the Classes of 2016–2025.
The following columns are used in this analysis:
ColumnFieldTypeDescriptionCClass OfInteger (4-digit year)The student's graduating class yearDGPAFloat (e.g., 3.45)High school GPA at graduationFMet GPA?Boolean ("Yes"/"No")Whether the student achieved a GPA ≥ 3.0GMet at Least 1 Benchmark?Boolean ("Yes"/"No")Whether the student met at least one ACT or SAT benchmarkHCollege Ready?Boolean ("Yes"/"No")Derived: "Yes" if and only if both F and G are "Yes"JCollege StatusCategorical (9 options)Observed or current post-secondary enrollment/completion status

Note: Columns A (Student Number), B (Name), E (Test), and I (Match Field)
are not used in this analysis.

College Readiness Rule (Column H)
College Ready = "Yes"  ←→  (GPA ≥ 3.0)  AND  (Met at least 1 ACT/SAT Benchmark)
Column H is entirely derived from columns F and G. It is treated here as a
binary classifier whose predictive validity we are evaluating.

3. Outcome Variable
The target variable for this analysis is a binary "Graduated Within 6 Years" flag,
derived from Column J (College Status).
College StatusCounts as Graduated?Graduated (4-Year)✅ YesGraduated (2-Year)✅ YesGraduated (4-Year), Continuing✅ YesGraduated (2-Year), Continuing✅ YesCredential Received✅ Yes*Currently Enrolled (4-Year)❌ NoCurrently Enrolled (2-Year)❌ NoNo Longer Enrolled❌ NoNever Enrolled❌ No

*️⃣ Note on Credential Received: This status is treated as a graduation-equivalent
outcome, consistent with federal college completion reporting standards. Credentials
(certificates, diplomas) represent a completed, intentional program of study.
This assumption should be revisited if the institution defines completion differently.


4. Cohort Structure
The ten graduating classes are divided into three analytically distinct groups:
Group 1 — Full Analysis Cohort (Classes of 2016–2019)
These four classes are 6 or more years post-high school graduation. College
outcomes are considered fully observed — students have had sufficient time to
complete a 2- or 4-year program within the 6-year window. This group is the
primary training and evaluation cohort for all statistical analyses.
Group 2 — Provisional Cohort (Class of 2020)
The Class of 2020 is included in the analysis but carries an important caveat:
as of this study, this cohort is only 5 years post-graduation, not six. A small
subset of students on longer degree tracks may not yet have a final outcome recorded.
Their inclusion provides additional data volume and an early look at trends, but
results for this class should be interpreted with that one-year gap in mind. Where
relevant, 2020 outcomes are reported separately alongside the 2016–2019 aggregate.
Group 3 — Excluded Cohort (Class of 2021)
The Class of 2021 is fully excluded from this analysis. Due to widespread
standardized testing cancellations during the COVID-19 pandemic, the vast majority
of 2021 seniors did not have ACT or SAT scores on record. As a result, Column G
(Met at Least 1 Benchmark?) and Column H (College Ready?) cannot be validly
assigned for this class. Including them would introduce systematic missingness
into the predictor variable and undermine the integrity of any model trained or
evaluated on it.
Group 4 — Prediction Cohort (Classes of 2022–2025)
These four classes are not yet far enough out to have observed 6-year completion
outcomes. Rather than analyzing outcomes, we will apply the model trained on
Groups 1–2 to generate class-level graduation likelihood estimates for each
cohort, producing projected completion rates as students continue through their
post-secondary journeys.

5. A Critical Methodological Note: Full Population, Not a Sample
This dataset represents the complete population of students who graduated from
this institution between 2016 and 2025. No sampling was performed. This distinction
has meaningful implications for how we interpret the statistics in this analysis:
What Changes

Descriptive statistics are exact. There is no sampling error. A graduation
rate of 61.3% is 61.3% for that cohort — not an estimate of some unknown true value.
Traditional p-values are philosophically awkward. The null hypothesis significance
testing framework is designed to answer: "If I drew another sample, would I see this
again?" That question doesn't apply here. Any difference we observe between groups
is the real difference.

What We Do Instead — and Why It's Still Rigorous

Permutation tests are reframed as a test of structure: Is the relationship
between college readiness and graduation organized, or could labels be shuffled
randomly and produce the same result? This is a valid and meaningful question
even with population data.
Bootstrap confidence intervals are reframed as stability checks: How much
does our observed metric vary under resampling? Narrow intervals indicate a robust,
stable signal. Wide intervals suggest the relationship is sensitive to which students
happen to be in the dataset — useful to know even when you have everyone.
Logistic regression is used as a descriptive and comparative tool, not a
generalization engine. Coefficients describe the structure of this population.


This is a strength of the study, not a limitation. Population-level data eliminates
the ambiguity of sampling and allows us to make direct, unqualified statements
about institutional outcomes. The resampling methods we apply are tools for
understanding signal strength and stability, not for making inferences about
an external population.
