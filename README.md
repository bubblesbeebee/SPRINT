Aim: 
1) remove duplicates and close out visits 
2) remove combination meds
3) create MRA column
4) generate flags to label first use of MRA
    - ensure no other medications were added on the same day MRA was started 
5) using the first use of MRA
    remove baseline use of MRA (if the daystart is <0)
    remove observations in the CLOSEOUT period 
7) record number of times MRA is started - 1 = first time MRA is started, 2 = MRA was stopped and resumed. Only 1 will be included in the cohort. 
8) merge with BP data
9) summarize medication list, ensure medication list is identical for the visit prior to MRA startday and on the MRA startday 
10) enter python loop to calculate pre-MRA SBP averaged across 60 days
        find the average days pre-MRA initiation 
11) merge the pre-MRA SBP data w the current master dataset, and export to python 
12) calculate the mean SBP difference post-pre MRA initiation via python 
        find the average visit days 
13) export back to STATA
