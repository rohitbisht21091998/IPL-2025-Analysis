

**IPL 2025 — Player & Match Impact Analysis**

**Why I Built This**
Everyone looks at the scoreboard. I wanted to look beyond it.
This project uses ball-by-ball data from IPL 2025 to answer questions a scorecard can't:

-Who was actually creating pressure?
-Does winning the toss really matter?
-Who was the most complete player of the season?


**Dataset**
FileDescription
1.matches.csv  - 74 matches, full results and toss data
2.deliveries.csv - 17,183 balls, every delivery of the season
3.orange_cap.csv Top 15 batters (season summary)
4.purple_cap.csvTop 15 bowlers (season summary)

**Tools**
-Python — Pandas, Matplotlib, Seaborn
-Jupyter Notebook


**What I Did**
**Data Cleaning**

Created legal_ball column — wides and no balls excluded from ball count but included in runs conceded
Removed 3 abandoned matches from match level analysis
Filled blank wicket columns with "none" to enable for wicket count

**Analysis Performed**

Top run scorers, six hitters, four hitters
Best strike rates (min 50 balls faced)
Top wicket takers, economy rates (min 100 balls bowled)
Average runs per over
Dot ball % per bowler
Toss impact on match result
Batting first vs bowling first win rate
Custom Player Impact Score


**Key Findings**
**Batting PlayerStat**
-Sai Sudharsan  Most runs759
-Nicholas PooranBest strike rate190+
-Suryakumar YadavBest balanceHigh runs + High SR
**Bowling PlayerStat**
-Prasidh Krishna Most wickets 26
-Khaleel Ahmed Most Dot ball%  49%
-Bumrah Best economy under 7 (only under 7)
**Match Patterns**
Findings
-Toss impact-  Toss winner won 60% of matches
-Batting first Teams batting first won 60% of matches(while it is believed chasing is easier)

**Custom Player Impact Score**
## Custom Player Impact Score

I built my own metric combining:
## Custom Player Impact Score

I built my own metric combining:

| Factor          | Points      |
|-----------------|-------------|
| 1 run scored    | +1          |
| 1 wicket taken  | +30         |
| SR 170-200      | +35 bonus   |
| SR 150-170      | +20 bonus   |
| SR 130-150      | +10 bonus   |
| SR 120-130      | -40 penalty |
| SR below 120    | -50 penalty |
| Economy below 8 | +50 bonus   |
| Economy 8-9     | +30 bonus   |
| Economy 9-10    | +10 bonus   |
| Economy 10-12   | 0           |
| Economy 12-15   | -15 penalty |
| Economy above 15| -50 penalty |
| catch           | +5          |

> Minimum 50 balls faced for batting points,
> 100 balls bowled for bowling points — to keep comparisons fair.

**Result — Prasidh Krishna ranked #1** — his combination
of wickets, economy and pressure bowling outscored
even the top run scorers.

**Learnings**
Ball-by-ball data requires careful handling of extras
Small features like legal_ball significantly change metric accuracy
Data analysis is not just calculation — it involves designing what the numbers should mean

**Charts**
All analysis charts available in the repository as PNG files.
