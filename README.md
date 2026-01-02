**Project Name: A-B-Testing-Analysis-of-Webpage-Conversion-Rates-
**

**Overview**

This project evaluates the performance of two webpage variants (Group A and Group B) using A/B testing techniques to determine whether the new version leads to a statistically significant improvement in user conversion rates. In addition to conversion, the analysis examines user engagement, segmentation effects, and potential experimental biases to support data-driven product decisions.

**Objective**

The primary objective is to answer the following business question:

Does the new webpage design (Group B) significantly improve conversion rates compared to the existing design (Group A)?

Secondary objectives include:

1. Assessing engagement differences between variants
2. Identifying device-levl performance differences
3. Validating experiment integrity through bias checks
4. Understanding the relationship between engagement and conversion

**Dataset Description**

The dataset represents user-level interactions from an A/B experiment. 
Key fields include:

1. User ID - Unique identifier per user
2. Group - Experiment assignment (A = control, B = variant)
3. Page Views - Number of pages viewed
4. Time Spent - Total session time (seconds)
5. Conversion - Whether the user converted (Yes / No)
6. Device - User device type (Mobile, Desktop)
7. Location - User geographic region

Each row represents a single user, ensuring independence of observations.

**Methodology**

A. Data Validation & Preparation
   1. Verified data completeness and structure
   2.  Ensured one observation per user
   3.  Converted conversion outcome into a binary flag
   4.  Standadized categorical fields for analysis

B. Exploratory Data Analysis (EDA)
  1. Examined user distribution across experiment groups
  2. Calculated conversion rates per variant
  3. Reviewed engagement metrics (time spent)

C. Hypothesis Testing (Primary Analysis)
Metric: Conversion Rate
Test Used: Two-Proportion Z-Test
Hypotheses:
1. H0: COnversion Rate (A) = Conversion Rate (B)
2. H1: Conversion Rate (B) != Conversion Rate (B)

A 95% confidence level (α = 0.05) was applied to determine statistical significance

D. Effect Size & Business Impact
  1. Calculated absolute conversion lift
  2. Calculated relative percentage improvement
  3. Translated statistical results into business impact

E. Engagement Analysis
  1. Compared time spent between groups
  2. Used Mann-Whitney U Test due to non-normal distribution
  3. Evaluated whether engagement changes align with conversion behavior

F. Segmented Analysis
  1. Analyzed conversion rates by device type
  2. Identified segments with stronger or weaker uplift
  3. Visualized differences across variants and segments

G. Bias & Sanity Checks
  1. Tested device distribution balance across groups
  2. Applied Chi-Square test to detect allocation bias
  3. Confirmed experiment randomization integrity

H. Conversion vs Engagement Relationship
  1. Compared average time spent for converters vs non-converters
  2. Measured correlation between engagement and conversion


**Key Findings**

1. Group B outperformed Group A in conversion rate, with the difference found to be statistically significant at the 95% confidence level.
2. The experiment produced a positive absolute and relative conversion uplift, indicating meaningful business impact.
3. Engagement (time spent) was higher for the variant group, supporting the observed conversion improvement.
4. Mobile users showed stronger conversion uplift compared to other device types.
5. No significant device allocation bias was detected, validating experiment reliability.
6. Users who converted spent more time on the webpage, suggesting engagment as a strong conversion driver.

**Business Recommendation**
Based on the results:

Roll out the new webpage design (Group B), priotizing mobile users where the conversion uplift is strongest.

Continue monitoring post-launch performance to ensure sustained impact and assess downstream metrics such as revenue and retention.

**Limitations**

1. Conversion-based analysis only (no revenue or LTV impact measured)
2. Single test window without long-term retention validation
3. Limited behavioral depth beyond session-level engagement

Next Steps
1. Extend the experiment duration for long-term validation
2. Incorporate revenue and monetization metrics
3. Perform cohort-based retention analysis
4. Explore multi-variant or personalized experiments

**Tools and Technologies**

1. Python: pandas, numpy, scipy, matplotlib
2. Statistical Methods: Two-Proportion Z-test, Mann-Whitney U Test, Chi-Square Test
3. Visualization: Matplotlib
