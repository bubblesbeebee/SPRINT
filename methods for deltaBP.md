The study employed a data processing algorithm to analyze blood pressure (BP) differences before and after the implementation of a medical regimen adjustment (MRA or thiazide). The analysis was conducted on a patient-by-patient basis, identified by unique maskids.

For each patient, the algorithm first determined the start date of the MRA (applicable for thiazide as well) . It then calculated the number of days between each BP measurement and the MRA start date, termed 'days_since_MRA'. Only measurements taken at least 30 days after the MRA start were considered for analysis.

The blood pressure difference (bp_diff) was calculated by subtracting the baseline BP (new_first_sbp_avg_filled) from the measured BP (seatsys) for each eligible reading. The algorithm accounted for medication consistency, recording bp_diff values only when the patient's medication regimen was consistent (consistent_med = 1). The last bp_diff before any medication inconsistency was also included as the antihypertensive effect of the newly added medication will be reflected in the subsequent visit.

For each patient, the algorithm stored up to five individual bp_diff values (bp_diff_visit_1 to bp_diff_visit_5). It then calculated the average BP difference (avg_bp_diff) across all recorded bp_diff values for that patient.

To analyze the temporal distribution of measurements contributing to avg_bp_diff, the algorithm calculated several statistics based on the 'days_since_MRA' values of the included measurements:

1. mean_diff_duration: The average number of days since MRA start
2. median_diff_duration: The median number of days since MRA start
3. min_diff_duration: The minimum number of days since MRA start
4. max_diff_duration: The maximum number of days since MRA start

These statistics were only calculated for patients with valid avg_bp_diff values, ensuring alignment between BP difference calculations and their corresponding temporal distributions.

The results were compiled into a dataset, with each patient (maskid) having a single row containing their avg_bp_diff and associated temporal statistics. This dataset was then exported for further statistical analysis.
