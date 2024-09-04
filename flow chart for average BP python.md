graph TD
    A[Start] --> B[Sort dataframe by maskid and formdays]
    B --> C[Initialize columns]
    C --> D[Group by maskid]
    D --> E{MRA_daystart available?}
    E -->|No| D
    E -->|Yes| F[Calculate days since MRA]
    F --> G[Filter rows >= 30 days after MRA]
    G --> H{Eligible rows exist?}
    H -->|No| D
    H -->|Yes| I[Initialize variables]
    I --> J[For each eligible row]
    J --> K{Is seatsys available?}
    K -->|No| L[Use last valid seatsys]
    K -->|Yes| M[Update last valid seatsys]
    L --> N{Is consistent_med zero?}
    M --> N
    N -->|Yes| O[Calculate bp_diff]
    O --> P[Store in bp_diff_visit_X]
    P --> Q[Increment visit count]
    Q --> J
    N -->|No| R[Reset visit count and last_valid_seatsys]
    R --> J
    J --> S[Calculate average bp_diff]
    S --> T[Update original dataframe]
    T --> U[Export to STATA]
    U --> V[End]
