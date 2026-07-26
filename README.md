# Student Academic Performance & Demographic Analysis
## 1. Executive Summary & Background
Academic performance metrics serve as leading indicators for educational institutions to evaluate learning efficacy, identify systemic equity gaps, and optimize resource allocation. Similar to business analytics applications, early detection of academic disparities enables administrators to implement targeted interventions before student outcomes deteriorate.

This report analyzes student evaluation data across three core disciplines: Mathematics, Reading, and Writing to identify structural patterns, evaluate the impact of parental educational attainment, and uncover gender-based performance gaps. The goal is to derive actionable, data-driven recommendations for curriculum design and student support programs.

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/28d8b376-618c-470a-a40e-2e435e1286c3" />

## 2. Data Overview & Data Cleaning Methodology
### Data Overview
The analysis utilizes a structured dataset evaluating student academic results across various demographic and social economic attributes. The primary variables include:
- **Demographics:** `gender`, `race_ethnicity`, `parental_level_of_education`
- **Performance Metrics:** `math_score`, `reading_score`, `writing_score`
### Data Preparation & Cleaning
Dataset includes 202 rows and 8 columns

To ensure analytical rigor and prevent model distortion:
1. **Deduplication & Data Audit:** Identified and removed **3 exact duplicate records** (specifically rows **19**, **45**, and **112** in the raw dataset, which duplicated student entries from rows **18**, **44**, and **111** respectively). This adjusted the total sample size from **202** to **199 unique student records**, ensuring no inflated variance in statistical evaluations.
2. **Missing Values:** Replaced missing data in `parental_level_of_education` (**Rows 59 and 92**) with `unknown` to maintain sample size.
3. **Feature Engineering:** Constructed composite variables `total_score` and `average_score` to measure cumulative academic competence across subject domains.
## 3. Descriptive Statistics Analysis
To summarize the central tendency, dispersion, and distribution morphology of the student performance metrics, descriptive statistics were calculated for all numerical variables ($N = 199$).

**TABLE 1. Summary Statistics of Academic Scores**

<img width="561" height="228" alt="image" src="https://github.com/user-attachments/assets/efe41523-104b-4a36-a9c6-958b51efdf7c" />

 **Key Takeaways from Summary Statistics:**
 - **Central Tendency & Consistency:** Student performance is highly consistent across subject domains, with mean scores clustering closely around $64 - 67$ points and median scores remaining steady at $65 - 68$. Reading yielded the highest average score ($67.63$), whereas Mathematics recorded the lowest mean ($64.22$).
 - **Data Distribution & Dispersion:** All three subjects display slight negative skewness (ranging from $-0.23$ to $-0.37$), indicating that a majority of students scored above the overall mean, with a small tail of low-performing students pulling the average down. The wide standard deviations ($\approx 15.4 - 16.2$) and high ranges ($83 - 100$ points) highlight substantial academic variance within the cohort, underscoring the need for targeted academic intervention.

## 4. Visualizations & Analytical Findings
### Finding 1: Socio-Academic Inheritance and Parental Educational Capital

**FIGURE 1. Average Student Score by Parental Education Level**

<img width="708" height="465" alt="image" src="https://github.com/user-attachments/assets/ec4454b3-d8d4-4899-9410-9ff84e2b10cd" />

#### Analytical Insight
The empirical evidence displayed in **Figure 1** indicates a positive monotonic relationship between advanced parental degree attainment and composite student achievement. Higher parental education levels serve as a proxy for greater home learning capital, structured study environments, and increased academic guidance.
#### Strategic Implication
To mitigate this intergenerational equity gap, institution leaders must avoid generic interventions. Instead, schools should establish structured peer-mentoring frameworks and dedicated counseling programs specifically targeted at supporting first generation students or those coming from lower educational attainment backgrounds.

### Finding 2: Asymmetric Domain Specialization Across Gender

**FIGURE 2. Academic Performance Disparity by Gender Across Subjects**

<img width="626" height="424" alt="image" src="https://github.com/user-attachments/assets/a620ee1d-05bf-4517-9d47-ca25efae720f" />

#### Analytical Insight
A structural divergence emerges when evaluating performance by subject domain across gender groups. As depicted in **Figure 2**, female students demonstrate strong proficiency in linguistic disciplines, outperforming males in Reading (72.45 vs. 62.85) and Writing (71.90 vs. 60.89). Conversely, male students exhibit a slight quantitative advantage in Mathematics (64.86 vs. 63.57). This gap reflects early educational socialization and subject specific self efficacy variances rather than underlying cognitive limitations.

#### Strategic Implication
Educational administrators should transition from uniform teaching methodologies toward tailored skill building tracks. Implementing quantitative acceleration workshops for female students alongside structured literacy remediation programs for male students will ensure balanced competency growth across all core disciplines.

---

## 5. Conclusion & Actionable Recommendations

Student academic performance is heavily conditioned by both socio-economic background and domain-specific learning preferences. Based on the analytical findings, educational leaders should execute two strategic initiatives:
1. **Targeted Equity Programs:** Allocate supplemental academic counseling resources to students whose parents lack higher education credentials.
2. **Customized Academic Intervention:** Shift from a one-size-fits-all curriculum to personalized learning tracks addressing verbal development in male students and quantitative mastery in female students.
