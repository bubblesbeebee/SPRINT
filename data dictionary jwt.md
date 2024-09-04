# Data Dictionary for Newly Created Variables

1. flag_thiazide1 to flag_thiazide10
   - Type: Binary (0/1)
   - Description: Indicates presence of thiazide in each medication column

2. any_thiazide
   - Type: Binary (0/1)
   - Description: Indicates presence of any thiazide medication in the current row

3. first_thiazide_occurrence
   - Type: Binary (0/1)
   - Description: Marks the first occurrence of thiazide for each patient

4. first_thiazide_formdays
   - Type: Numeric
   - Description: Number of days post-randomization when thiazide was first prescribed

5. first_thiazide_daysstart
   - Type: Numeric
   - Description: Start date of first thiazide prescription relative to visit date

6. multiple_thiazide_starts
   - Type: Binary (0/1)
   - Description: Indicates subsequent thiazide prescriptions after the first occurrence

7. concurrent_start
   - Type: Binary (0/1)
   - Description: Indicates if other medications were started concurrently with first thiazide

8. thiazide_solo_start
   - Type: Binary (0/1)
   - Description: Indicates if thiazide was started without concurrent medications

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
