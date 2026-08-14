# Bellabeat Case Study

## Project Overview

This case study analyses Fitbit smart-device data to identify activity and sleep trends that may be relevant to Bellabeat customers. The goal is to translate behavioural patterns into practical, high-level recommendations for the Bellabeat Time wellness watch.

The analysis focuses on daily activity and sleep data from **12 April to 12 May 2016**.

## Business Task

Analyse smart-device usage trends from Fitbit user data and consider how these trends may apply to Bellabeat customers. Use the insights from this analysis to develop high-level marketing recommendations for the Bellabeat Time wellness watch.

## Key Questions

- What patterns appear in daily activity?
- How does sleep duration vary across the week?
- Is there a meaningful relationship between daily step count and sleep duration?
- How could these findings inform Bellabeat's product and marketing strategy?

## Tools Used

- Python
- pandas
- NumPy
- Matplotlib
- Jupyter Notebook
- Git and GitHub

## Data and Scope

The source Fitbit dataset contains records collected across two periods between March and May 2016. This case study focuses on **12 April to 12 May 2016**, which provides directly comparable daily activity and daily sleep data for a consistent one-month analysis window.

The Fitbit records were collected in 2016, as supplied for this case study.

The final analysis uses:

- **940 daily activity records**
- **33 users with activity data**
- **24 users with sleep data**
- **410 cleaned daily sleep records**
- Daily step count (`TotalSteps`)
- Daily sleep duration (`TotalMinutesAsleep`)

The earlier March–April period also contains activity and sleep data, but its sleep file records each minute as **asleep, restless or awake** instead of providing a ready-made daily sleep-duration measure. To use it in the same analysis, those minute-level records would need to be aggregated and the mapping to a daily `TotalMinutesAsleep` measure would need to be confirmed. Rather than make that assumption, this project uses the later one-month period, where daily activity and sleep measures are already directly comparable. The earlier period could be revisited in a follow-up analysis once the metric definition is confirmed.

## Data Preparation and Quality Checks

Before analysis, the datasets were inspected for structure, completeness, duplicates, date formats and questionable observations.

Key preparation decisions included:

- Converting activity and sleep dates to datetime format
- Removing three exact duplicate sleep rows
- Reviewing unusually short sleep records and retaining them because there was insufficient evidence that they were data-entry errors
- Investigating questionable activity records, including zero-calorie days and records with unusually high sedentary minutes
- Some activity-intensity fields contained inconsistent values, so the main activity analysis focused on total daily steps

## Analysis

The project examined three main areas:

1. **Activity patterns** — average steps by weekday and variation between users
2. **Sleep patterns** — average sleep duration by weekday and differences in sleep-data coverage
3. **Activity and sleep relationship** — the relationship between daily steps and sleep duration beginning that night

## Key Findings

### 1. Activity Patterns

Average daily activity was relatively consistent across the week at roughly **7,000–8,000 steps**.

- Tuesday and Saturday had the highest weekday averages, both above 8,000 steps.
- Sunday had the lowest average at roughly 6,900 steps.
- Individual activity levels varied substantially: 25% of users averaged below roughly 5,500 daily steps, while the top 25% averaged above roughly 9,500.

This suggests that stable overall weekday averages can hide meaningful differences between individual users.

### 2. Sleep Patterns

Average sleep duration was relatively consistent across the week, with modest weekday differences.

- Sunday recorded the highest average sleep duration at approximately **7 hours 33 minutes**.
- Thursday recorded the lowest at approximately **6 hours 41 minutes**.
- Sleep-data coverage varied considerably between users, so weekday sleep averages should be interpreted cautiously.

### 3. Steps vs Sleep Relationship

Daily steps and sleep duration showed a **very weak negative correlation (r = -0.19)**.

Although higher-step days were associated with slightly shorter sleep durations in this dataset, the observations showed substantial variation. The analysis therefore does not provide strong evidence of a meaningful linear relationship between daily steps and sleep duration.

This is an association only and should not be interpreted as causal.

## Recommendations

### 1. Personalised Activity Goals

Bellabeat could provide personalised activity goals and benchmarks based on each user's historical activity rather than relying primarily on generic step targets.

Because activity levels varied considerably between users, personalised goals could provide more relevant and achievable targets as behaviour changes over time.

### 2. Encourage Consistent Sleep Tracking

Bellabeat could encourage more regular sleep tracking through reminders and educational messaging explaining how complete data supports more meaningful personalised insights and trends.

This could include in-app or wearable reminders when sleep data has not been recorded consistently.

### 3. Treat Activity and Sleep as Distinct Wellness Measures

Because the relationship between daily steps and sleep duration was very weak, Bellabeat should avoid assuming that highly active users will necessarily sleep longer.

Activity and sleep could instead be treated as separate wellness measures, with sleep insights based on actual sleep data rather than inferred from activity levels.

## Limitations

- **Small sample size:** activity data covers 33 users and sleep data covers 24 users.
- **Short observation period:** the main analysis covers roughly one month.
- **Incomplete and questionable records:** user coverage varied considerably, particularly for sleep, and some unusual observations could not be confidently classified as errors.
- **Limited demographic information:** age, gender, location and other demographic characteristics are unknown, limiting how confidently the findings can be generalised to Bellabeat's customer base.
- **Historical dataset:** the Fitbit data was collected in 2016. In a real business setting, I would want current user data before using these findings to guide marketing decisions in 2026.

## Conclusion

The analysis found that average activity and sleep patterns were relatively stable across the week, while individual activity levels varied widely and sleep-data coverage differed considerably between users.

Daily steps and sleep duration showed only a very weak relationship. For Bellabeat, the clearest opportunities are to personalise activity goals, encourage more consistent sleep tracking, and provide activity and sleep insights independently.

## Full Analysis

The complete Python analysis, data-quality checks, code, visualisations and interpretation are available in:

[`notebooks/bellabeat_analysis_final.ipynb`](notebooks/bellabeat_analysis_final.ipynb)

---

*Google Data Analytics Professional Certificate — Bellabeat Capstone Case Study*
