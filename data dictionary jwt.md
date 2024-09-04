# Data Dictionary for Newly Created Variables

# Thiazide-related Variables Data Dictionary

| Variable Name | Description | Data Type | Possible Values |
|---------------|-------------|-----------|-----------------|
| flag_thiazide1 to flag_thiazide10 | Indicates presence of thiazide in each medication column | Binary | 0 (absent), 1 (present) |
| any_thiazide | Indicates presence of any thiazide medication in the current row | Binary | 0 (absent), 1 (present) |
| first_thiazide_occurrence | Marks the first occurrence of thiazide for each patient | Binary | 0 (not first), 1 (first) |
| first_thiazide_formdays | Number of days post-randomization when thiazide was first prescribed | Integer | ≥ 0 |
| first_thiazide_daysstart | Start date of first thiazide prescription relative to visit date | Integer | Any integer |
| multiple_thiazide_starts | Indicates subsequent thiazide prescriptions after the first occurrence | Binary | 0 (no), 1 (yes) |
| concurrent_start | Indicates if other medications were started concurrently with first thiazide | Binary | 0 (no), 1 (yes) |
| thiazide_solo_start | Indicates if thiazide was started without concurrent medications | Binary | 0 (no), 1 (yes) |

Notes:
1. flag_thiazide1 to flag_thiazide10 represent up to 10 different medication columns in the dataset.
2. 'Binary' variables are coded as 0 or 1, where 0 typically indicates 'No' or 'Absent', and 1 indicates 'Yes' or 'Present'.
3. first_thiazide_formdays and first_thiazide_daysstart are relative to some baseline date (e.g., randomization date or study start date).
4. A value of 1 for multiple_thiazide_starts indicates that the patient had at least one more thiazide prescription after their first one.
5. concurrent_start and thiazide_solo_start are mutually exclusive; if one is 1, the other must be 0.

# Data Dictionary for BP Diff Analysis

| Variable Name | Description | Data Type | Possible Values |
|---------------|-------------|-----------|-----------------|
| maskid | Unique identifier for each patient | Integer | Positive integers |
| formdays | Date of the BP measurement | Date | Any valid date |
| min_MRA_daystart | Start date of the Medical Regimen Adjustment (MRA) | Date | Any valid date |
| seatsys | Systolic blood pressure measurement | Float | Positive numbers |
| new_first_sbp_avg_filled | Baseline systolic blood pressure | Float | Positive numbers |
| consistent_med | Indicator of consistent medication regimen | Integer | 0 (inconsistent), 1 (consistent) |
| days_since_MRA | Number of days between BP measurement and MRA start | Integer | ≥ 30 |
| bp_diff | Difference between measured BP and baseline BP | Float | Any number |
| bp_diff_visit_1 | BP difference for the first valid visit after MRA | Float | Any number |
| bp_diff_visit_2 | BP difference for the second valid visit after MRA | Float | Any number |
| bp_diff_visit_3 | BP difference for the third valid visit after MRA | Float | Any number |
| bp_diff_visit_4 | BP difference for the fourth valid visit after MRA | Float | Any number |
| bp_diff_visit_5 | BP difference for the fifth valid visit after MRA | Float | Any number |
| avg_bp_diff | Average of all valid bp_diff values for a patient | Float | Any number |
| mean_diff_duration | Mean number of days since MRA for valid BP measurements | Float | ≥ 30 |
| median_diff_duration | Median number of days since MRA for valid BP measurements | Float | ≥ 30 |
| min_diff_duration | Minimum number of days since MRA for valid BP measurements | Integer | ≥ 30 |
| max_diff_duration | Maximum number of days since MRA for valid BP measurements | Integer | > 30 |

Notes:
1. All BP measurements are in mmHg (millimeters of mercury).
2. 'Valid' BP measurements refer to those taken at least 30 days after MRA start and during periods of consistent medication.
3. bp_diff_visit_1 through bp_diff_visit_5 may be NaN if fewer than 5 valid visits occurred.
4. avg_bp_diff and the diff_duration statistics are only calculated for patients with at least one valid bp_diff value.
5. The diff_duration statistics are based on the same set of measurements used to calculate avg_bp_diff.
