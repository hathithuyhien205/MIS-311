# Student Academic Performance & Demographic Analysis
## 1. Executive Summary & Background
Academic performance metrics serve as leading indicators for educational institutions to evaluate learning efficacy, identify systemic equity gaps, and optimize resource allocation. Similar to business analytics applications, early detection of academic disparities enables administrators to implement targeted interventions before student outcomes deteriorate.

This report analyzes student evaluation data across three core disciplines: Mathematics, Reading, and Writing to identify structural patterns, evaluate the impact of parental educational attainment, and uncover gender-based performance gaps. The goal is to derive actionable, data-driven recommendations for curriculum design and student support programs.

<img width="740" height="486" alt="image" src="https://github.com/user-attachments/assets/2722dcb3-9c2c-4563-9de5-85986459879d" />

## 2. Data Overview & Data Cleaning Methodology
### Data Overview
The analysis utilizes a structured dataset evaluating student academic results across various demographic and socioeconomic attributes. The primary variables include:
- **Demographics:** `gender`, `race_ethnicity`, `parental_level_of_education`
- **Performance Metrics:** `math_score`, `reading_score`, `writing_score`
### Data Preparation & Cleaning
Dataset includes 202 rows and 8 columns

To ensure analytical rigor and prevent model distortion: 
- **Deduplication:** Identified and removed 3 exact duplicate records (specifically rows 19, 45, and 112 in the raw dataset, which duplicated student entries from rows 18, 44, and 111 respectively). This adjusted the total sample size from 202 to 199 unique student records, ensuring no inflated variance in statistical evaluations.
- **Missing Values:** Replaced missing data in `parental_level_of_education` (Rows 59 and 92) with `unknown` to maintain sample size.
- **Feature Engineering:** Constructed composite variables `total_score` and `average_score` to measure cumulative academic competence across subject domains.
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
The empirical evidence displayed in **Figure 1** indicates a positive correlation between advanced parental degree attainment and composite student achievement. Higher parental education levels serve as a proxy for greater home learning capital, structured study environments, and increased academic guidance (Coleman, 1988; Sirin, 2005).
#### Strategic Implication
To mitigate this intergenerational equity gap, institution leaders must avoid generic interventions. Instead, schools should establish structured peer-mentoring frameworks and dedicated counseling programs specifically targeted at supporting first generation students or those coming from lower educational attainment backgrounds.

### Finding 2: Asymmetric Domain Specialization Across Gender

**FIGURE 2. Academic Performance Disparity by Gender Across Subjects**

<img width="626" height="424" alt="image" src="https://github.com/user-attachments/assets/a620ee1d-05bf-4517-9d47-ca25efae720f" />

#### Analytical Insight
A structural divergence emerges when evaluating performance by subject domain across gender groups. As depicted in **Figure 2**, female students demonstrate strong proficiency in linguistic disciplines, outperforming males in Reading (72.45 vs. 62.85) and Writing (71.90 vs. 60.89). Conversely, male students exhibit a slight quantitative advantage in Mathematics (64.86 vs. 63.57). This gap reflects early educational socialization and subject specific self efficacy variances rather than underlying cognitive limitations (Voyer & Voyer, 2014; Duckworth & Seligman, 2006).

#### Strategic Implication
Educational administrators should transition from uniform teaching methodologies toward tailored skill building tracks. Implementing quantitative acceleration workshops for female students alongside structured literacy remediation programs for male students will ensure balanced competency growth across all core disciplines.

### Finding 3: Score Variance & Outlier Concentration 

**FIGURE 3. Score Distribution Across Subjects** 

<img width="784" height="478" alt="image" src="https://github.com/user-attachments/assets/f3c8b540-e85d-4dc2-98fe-79d84da51d7e" />


#### Analytical Insight
To ensure statistical rigor, outliers are identified using the Interquartile Range (IQR) method (Tukey, 1977) 

($\text{Lower Bound} = Q1 - 1.5 \times \text{IQR}$):

| Subject | Q1 | Q3 | IQR | Lower Bound | Outliers Found |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Mathematics** | 54.0 | 75.0 | 21.0 | **22.5** | 3 scores (0, 18, 22) |
| **Reading** | 55.5 | 79.0 | 23.5 | **20.25** | 1 score (17) |
| **Writing** | 55.0 | 78.0 | 23.0 | **20.5** | 1 score (10) |

Based on these statistical thresholds, the score distribution reveals distinct variance patterns across subject domains:

* **Math Vulnerability:** Mathematics displays the highest vulnerability at the lower bound, containing all 3 extreme statistical outliers alongside an additional low scorer (27 points). This indicates a severe learning gap isolated within a small subgroup of struggling students, rather than a cohort-wide issue.
* **Reading & Writing Consistency:** Both Reading and Writing demonstrate high overall score stability, featuring only a single extreme low-end outlier each.

#### Strategic Implication
Academic support teams should implement a targeted Early Warning System (EWS) specifically for Mathematics (Allensworth & Easton, 2007). Early diagnostic tracking will allow educators to identify students falling into the bottom quartile before their scores plummet to severe outlier levels (< 30 points).


## 5. Conclusion & Actionable Recommendations

Student academic performance is heavily conditioned by socio-economic background, gender-based domain preferences, and individual variance in quantitative comprehension. Based on the empirical findings, educational leaders should execute three strategic initiatives:

- **Targeted Equity Programs**: Allocate supplemental academic counseling and structured peer-mentoring resources to students whose parents lack higher education credentials to bridge the socio-academic gap.
-  **Customized Academic Intervention**: Shift from a one-size-fits-all curriculum to personalized skill-building tracks, focusing on literacy remediation for male students and quantitative strengthening for female students.
- **Mathematics Outlier Prevention (Early Warning System)**: Establish early diagnostic assessments and a targeted Early Warning System (EWS) in Mathematics (Allensworth & Easton, 2007). The program should specifically monitor and support students scoring in the bottom range (< 22.5 – 30 points) to directly mitigate the severe learning gaps identified in the 3 statistical outliers (and 4 low-performing cases overall) before their academic trajectories deteriorate further.

## 6. References

Allensworth, E. M., & Easton, J. Q. (2007). *What matters for student success: Developing early warning indicators for high school graduation*. Consortium on Chicago School Research.

Coleman, J. S. (1988). Social capital in the creation of human capital. *American Journal of Sociology*, *94*, S95–S120. https://doi.org/10.1086/228943

Duckworth, A. L., & Seligman, M. E. (2006). Self-discipline gives girls the edge: Gender in self-discipline, grades, and achievement test scores. *Journal of Educational Psychology*, *98*(1), 198–208. https://doi.org/10.1037/0022-0663.98.1.198

Sirin, S. R. (2005). Socioeconomic status and academic achievement: A meta-analytic review of research. *Review of Educational Research*, *75*(3), 417–453. https://doi.org/10.3102/00346543075003417

Tukey, J. W. (1977). *Exploratory data analysis*. Addison-Wesley.

Voyer, D., & Voyer, S. D. (2014). Gender differences in scholastic achievement: A meta-analysis. *Psychological Bulletin*, *140*(4), 1174–1204. https://doi.org/10.1037/a0036620
