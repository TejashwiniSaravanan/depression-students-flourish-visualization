# Analyzing Depression in Students: Advanced Motion Visualization with Flourish

A data visualization independent study applying motion-based and interactive charts to a student mental health dataset. Built in Flourish Studio, the project produces five dynamic visualizations that explore the relationships between academic pressure, sleep patterns, financial stress, family mental health history, and depression severity across student populations.

<p align="center">
  <a href="https://public.flourish.studio/story/2792289/">View Live Flourish Story</a> · <a href="https://tejashwinisaravanan.github.io/depression-students-flourish-visualization/">View GitHub Pages</a>
</p>

<p align="center">
  <img src="images/Motion Scatter Plot.png" width="680" alt="Motion Scatter Plot - Academic Pressure and Suicidal Thoughts"/>
</p>

<p align="center"><em>Dashboard 1: Academic pressure, suicidal ideation, and study satisfaction animated across study hours by gender.</em></p>

---

## Overview

Depression affects a significant and growing proportion of students worldwide. The challenge in communicating mental health data to non-technical audiences - policymakers, university administrators, student support teams - is that static charts flatten the complexity of how multiple variables interact and change over time.

This project explores whether motion-based visualization closes that gap. Using Flourish Studio's animation and interactivity features, five dashboards were built to show how academic pressure, lifestyle factors, and family mental health history relate to student depression - not as a snapshot, but as a dynamic system where relationships shift as variables like study hours and age change.

The project was completed as an independent study (ISM6900) at Seattle Pacific University under faculty supervision, requiring both technical execution in Flourish and Python preprocessing, and a formal written analysis evaluating motion visualization as a communication medium for health data.

---

## Research Questions

Three specific questions guided the analysis:

1. What is the relationship between academic pressure and mental health outcomes including suicidal ideation?
2. How do lifestyle factors - sleep duration, eating habits, physical activity, financial stress - interact with academic performance and well-being?
3. Does family history of mental illness produce measurable differences in academic pressure, study satisfaction, and financial stress patterns over time?

---

## The Dataset

| | |
|---|---|
| Source | [Kaggle - Depression Among Students](https://www.kaggle.com/datasets/ikynahidwin/depression-student-dataset) |
| Variables | Age, gender, academic pressure, study satisfaction, study hours, sleep duration, eating habits, physical activity, financial stress, family history of mental illness, depression severity, suicidal ideation |
| Tool | Flourish Studio, Python (preprocessing) |
| Course | ISM6900 Independent Study - Seattle Pacific University, Fall 2024 |

---

## Data Preparation

Before any visualization was built, the dataset was preprocessed in Python to ensure Flourish Studio could render it accurately.

**Missing value handling.** Variables with null entries were identified and addressed. Missing values in categorical fields like eating habits and physical activity were imputed using mode values within demographic subgroups rather than globally - a more defensible approach given that lifestyle patterns vary significantly by age group.

**Normalization.** Continuous variables including academic pressure scores and financial stress indices were normalized to a common scale to enable meaningful visual comparison across variables with different native ranges.

**Encoding.** Categorical variables were encoded numerically for Flourish compatibility. Depression severity levels were mapped to an ordered numeric scale to allow trend visualization across the severity spectrum.

**Formatting.** The cleaned dataset was exported to CSV format structured to match Flourish's expected input for each visualization type - scatter plots, bubble charts, tree maps, line charts, and stacked area charts each require different column arrangements.

---

## The Five Dashboards

All five visualizations are live and interactive at the Flourish story link above. Each uses motion - animation across a time or continuous axis - to show how relationships between variables evolve rather than presenting a single static view.

---

### Dashboard 1 - Impact of Academic Pressure on Suicidal Thoughts

**Type:** Motion Scatter Plot

<p align="center">
  <img src="images/Motion Scatter Plot.png" width="620" alt="Motion Scatter Plot showing academic pressure vs suicidal ideation by gender"/>
</p>

<p align="center"><em>Academic pressure mapped against suicidal ideation, animated across study hours. Color-coded by gender. Point size reflects study satisfaction level.</em></p>

This scatter plot maps the relationship between academic pressure, suicidal ideation, and study satisfaction, animated across study hours. The motion axis is study hours, showing how the relationship between academic pressure and suicidal ideation shifts as students' weekly study commitment increases.

**Finding:** Higher academic pressure correlates with increased suicidal ideation frequency, and the relationship intensifies as study hours rise. Gender differences in the distribution suggest that the same academic pressure levels produce different mental health outcomes for male and female students.

---

### Dashboard 2 - Academic Pressure vs. Study Satisfaction

**Type:** Motion Bubble Chart

<p align="center">
  <img src="images/Motion Bubble Chart.png" width="620" alt="Motion Bubble Chart showing academic pressure vs study satisfaction by age group"/>
</p>

<p align="center"><em>Academic pressure against study satisfaction, with bubble size representing satisfaction level and color representing age group. Depression status revealed in each point's popup.</em></p>

This bubble chart plots academic pressure against study satisfaction, with bubble size representing satisfaction level and color representing age group. Each data point's popup reveals the student's depression status, enabling viewers to connect the visual pattern to clinical outcomes.

**Finding:** Younger students cluster at higher academic pressure with lower study satisfaction - a combination associated with higher depression status in the popup data. Older students show more dispersed patterns, suggesting that coping mechanisms or course selection strategies shift with age.

---

### Dashboard 3 - Lifestyle Factors and Well-Being

**Type:** Motion Tree Map

<p align="center">
  <img src="images/Motion Tree Map.png" width="620" alt="Motion Tree Map showing lifestyle factors nested by sleep duration and eating habits"/>
</p>

<p align="center"><em>Lifestyle factors nested by sleep duration and eating habits. Tile size reflects study hours and financial stress. An age filter isolates patterns for specific demographic groups.</em></p>

This tree map nests and categorizes data by sleep duration and eating habits, with tiles sized by study hours and financial stress. An age filter allows viewers to isolate lifestyle patterns for specific demographic groups. The layered structure captures the interaction between lifestyle factors that a single-variable chart cannot represent.

**Finding:** Students with shorter sleep durations and irregular eating habits cluster in the highest financial stress segments, regardless of age group. The motion element confirms this pattern is consistent rather than age-specific, suggesting systemic rather than developmental drivers.

---

### Dashboard 4 - Family History of Mental Illness and Academic Well-Being

**Type:** Motion Line Chart

<p align="center">
  <img src="images/Motion Line Chart.png" width="620" alt="Motion Line Chart showing academic and well-being trends split by family mental illness history"/>
</p>

<p align="center"><em>Academic pressure, study satisfaction, study hours, and financial stress tracked over time, split by family history of mental illness status.</em></p>

This line chart tracks academic pressure, study satisfaction, study hours, and financial stress over time, split by family history of mental illness status. Separate lines for students with and without a family history allow direct comparison of how these variables evolve differently across the two groups.

**Finding:** Students with a family history of mental illness show higher baseline academic pressure and financial stress at the same age points. Study satisfaction trends diverge over time between the two groups - a pattern visible in the animated chart but invisible in a static cross-sectional view. Family mental health history is a statistically visible risk signal in the academic data, with direct implications for early intervention targeting.

---

### Dashboard 5 - Sleep Duration, Study Hours, and Financial Stress

**Type:** Stacked Motion Area Chart

<p align="center">
  <img src="images/Stacked Motion Area Chart.png" width="620" alt="Stacked Motion Area Chart showing cumulative relationship between sleep, study hours, and financial stress"/>
</p>

<p align="center"><em>Cumulative view of sleep duration, study hours, and financial stress over time. Age filter enables targeted analysis by demographic group.</em></p>

This stacked area chart shows the cumulative relationship between sleep duration, study hours, and financial stress over time. The stacked design reveals the relative contribution of each variable to the overall burden on students, while the motion element shows how that composition shifts.

**Finding:** Financial stress is the dominant variable for the youngest age groups, compressing both sleep duration and study satisfaction simultaneously. As age increases, the relative weight of financial stress decreases while academic pressure increases - suggesting that early undergraduate students face primarily financial stressors while upper-level students face primarily academic ones. This has practical implications for when and how universities should deploy different types of student support resources.

---

## Why Motion Visualization for Mental Health Data

Static charts represent mental health data as a snapshot. A bar chart showing average depression scores by academic pressure level tells you where things stand but not how they got there or where they are going.

Motion visualization adds the temporal and relational dimensions that mental health data actually has. Depression does not exist at a single point in time - it develops, intensifies, and responds to changes in sleep, academic stress, financial pressure, and social support. A chart that animates across study hours or filters dynamically by age group allows the viewer to see that development rather than just its outcome.

This is particularly important for communicating mental health findings to non-technical audiences. A university administrator reviewing student support resource allocation does not need a regression table - they need to see that financial stress and sleep deprivation cluster together in first-year students, and that this pattern is distinct from what upper-level students experience. Motion visualization makes that visible in seconds.

The limitation of motion visualization is reproducibility. Static charts are easier to embed in reports, share in email, and reference in written policy documents. The most effective use of motion visualization is as a complement to static analysis - using animation to surface patterns and generate hypotheses, then validating those patterns with statistical models that can be reproduced and reported formally.

---

## Connection to Healthcare Analytics

This project sits at the intersection of mental health research and data communication - two areas directly relevant to health informatics and public health analytics roles.

The analytical patterns used here - identifying at-risk demographic subgroups, tracking how risk factors co-occur and evolve over time, and communicating findings to non-clinical audiences - are the same patterns used in population health dashboards, hospital readmission monitoring, and patient outcome reporting.

The family mental health history finding - that a documented family history produces statistically visible differences in academic stress patterns - is the kind of signal that a clinical decision support system would flag as an early intervention trigger. This connects directly to the predictive analytics approach explored in the Clinical Trial Patient Selection project and the AI in Healthcare research paper included in that repository.

---

## Repository Structure

```
depression-students-flourish-visualization/
│
├── images/
│   ├── Motion Scatter Plot.png             # Dashboard 1 - Academic pressure vs suicidal ideation
│   ├── Motion Bubble Chart.png             # Dashboard 2 - Academic pressure vs study satisfaction
│   ├── Motion Tree Map.png                 # Dashboard 3 - Lifestyle factors tree map
│   ├── Motion Line Chart.png               # Dashboard 4 - Family history trends
│   └── Stacked Motion Area Chart.png       # Dashboard 5 - Sleep, study hours, financial stress
│
├── data/
│   └── depression_students_cleaned.csv     # Preprocessed dataset
│
├── depression_preprocessing.py             # Python cleaning and preprocessing script
├── Project_Report.docx                     # Full independent study written report
├── dashboard_walkthrough.mp4               # Video walkthrough of all five dashboards
└── README.md
```

---

## Getting Started

The live Flourish story requires no installation - visit the link at the top of this README to explore all five interactive dashboards directly in your browser.

To reproduce the data preprocessing:

```bash
pip install pandas numpy scikit-learn
python depression_preprocessing.py
```

---

## Limitations and What I Would Do Next

The dataset is cross-sectional - all variables are recorded at a single point in time per student. The motion element animates across study hours or age, but this is a simulated temporal dimension rather than true longitudinal data. Genuine longitudinal data tracking the same students over a semester would allow the motion visualization to show real change rather than cross-sectional variation.

A statistical validation layer would strengthen the visual findings. The patterns visible in the motion charts - particularly the family history split and the financial stress age gradient - should be confirmed with regression models or chi-square tests before being used to inform policy decisions. The visualizations surface hypotheses; formal statistics confirm them.

---

## Tools and Technologies

Flourish Studio - Python - Pandas - NumPy - Scikit-Learn - Microsoft Excel

---

## Related Projects

- **[Clinical Trial Patient Selection](https://github.com/TejashwiniSaravanan/Clinical-Trial-Patient-Selection-Optimization)** - Predictive modeling for patient classification using Orange Data Mining
- **[AI in Healthcare Knowledge Management](https://github.com/TejashwiniSaravanan/Clinical-Trial-Patient-Selection-Optimization/blob/main/docs/AI_in_Healthcare_KM_Research_Paper.pdf)** - Research paper on AI-driven predictive analytics in clinical settings
- **[Healthcare Analytics - PySpark ML & GCP Strategy](https://github.com/TejashwiniSaravanan/Healthcare-Analytics-PySpark-ML-GCP-Strategy)** - Cloud architecture for real-time patient monitoring

---

## About Me

**Tejashwini Saravanan** - Master's student in Data Analytics at Seattle Pacific University, focused on healthcare data visualization, clinical analytics, and public health informatics.

[LinkedIn](https://www.linkedin.com/in/tejashwinisaravanan/) · [GitHub](https://github.com/TejashwiniSaravanan) · [Flourish Public Profile](https://public.flourish.studio/story/2792289/)

---

*Dataset: Kaggle - Depression Among Students · Tool: Flourish Studio · Independent Study ISM6900 · Seattle Pacific University · Fall 2024*
