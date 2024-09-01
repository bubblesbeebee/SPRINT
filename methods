Methods

To identify the initiation and patterns of thiazide diuretic use among patients, we conducted a comprehensive analysis of medication data. The study utilized longitudinal patient records, with each record containing up to ten medication entries per visit. We developed a custom algorithm in Stata 16 to process this data systematically.

Initially, we generated indicator variables for thiazide presence across all medication columns, focusing on chlorthalidone and hydrochlorothiazide. These indicators were aggregated to create a binary variable denoting any thiazide use per visit. The algorithm then identified the first occurrence of thiazide prescription for each patient by chronologically assessing visits and marking the earliest thiazide presence.

To capture the timing of thiazide initiation, we recorded both the number of days post-randomization (formdays) and the medication start date relative to the visit (daysstart) for the first thiazide occurrence. These values were propagated across all records for each patient to facilitate subsequent analyses.

We implemented checks for multiple thiazide starts by tracking the cumulative sum of thiazide prescriptions per patient. Any thiazide prescription beyond the first occurrence was flagged as a subsequent start, allowing for the identification of discontinuation and reinitiation patterns.

Concurrent medication initiation was assessed by comparing the start dates of other medications with the thiazide initiation date. This analysis helped distinguish between thiazide monotherapy initiation and combination therapy approaches.

Throughout the process, we maintained the integrity of the original data structure, performing analyses without reshaping the dataset. This approach preserved the temporal sequence of medication changes and allowed for a nuanced understanding of prescription patterns over time.

This methodology enables a detailed examination of thiazide diuretic utilization patterns, including initiation timing, monotherapy versus combination therapy approaches, and patterns of discontinuation and reinitiation.
