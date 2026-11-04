**Experiment 1: EDA in IPL Dataset**

**Aim:**

To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.


**Algorithm / Procedure:**


**1.Import Libraries**

  *Import pandas for data handling.
  Import matplotlib and seaborn for visualization.*

  
**Program**

```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

```


**2.Load Dataset**
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().

  
**Program**

```
print("Dataset loaded successfully")
print("Shape of dataset:", df.shape)

df.head()

```

**Output**

<img width="1082" height="543" alt="image" src="https://github.com/user-attachments/assets/408073ba-4748-488c-bcfe-86ee143bc2a7" />


**3.Matches per Season (Univariate Analysis)**


  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.
  

**Program**


```
matches_per_season = df['season'].value_counts().sort_index()

print(matches_per_season)

matches_per_season.plot(kind='bar', figsize=(10,5))

plt.title("Number of Matches Played Per IPL Season")
plt.xlabel("Season")
plt.ylabel("Number of Matches")
plt.xticks(rotation=45)
plt.show()

```

**Output**

<img width="1040" height="756" alt="image" src="https://github.com/user-attachments/assets/debe4f5e-3a53-4dc4-9ef7-4db7428ccdd0" />


**4.Top Winning Teams (Univariate Analysis)**

  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.

  
**Program**
```
top_teams = df['winner'].value_counts().head(5)

print(top_teams)

top_teams.plot(kind='bar', figsize=(10,5))

plt.title("Top 5 Winning Teams in IPL")
plt.xlabel("Teams")
plt.ylabel("Number of Wins")
plt.xticks(rotation=45)
plt.show()

```

**Output**

<img width="1036" height="702" alt="image" src="https://github.com/user-attachments/assets/dc81c626-f93e-46a9-bc03-3b994fdf2da9" />



**5.Toss Decisions (Univariate Analysis)**
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
  

**Program**

```
toss_decisions = df['toss_decision'].value_counts()

print(toss_decisions)

toss_decisions.plot(kind='bar', figsize=(7,5))

plt.title("IPL Toss Decisions")
plt.xlabel("Toss Decision")
plt.ylabel("Number of Matches")
plt.xticks(rotation=0)
plt.show()

```

**Output**

<img width="1032" height="527" alt="image" src="https://github.com/user-attachments/assets/df8646e7-8f9e-451d-8e90-f0110be69841" />

**6.Top Venues (Univariate Analysis)**


  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.


**Program**

```

top_venues = df['venue'].value_counts().head(5)

print(top_venues)

top_venues.plot(kind='barh', figsize=(10,5))

plt.title("Top 5 Stadiums Hosting Maximum IPL Matches")
plt.xlabel("Number of Matches")
plt.ylabel("Stadiums")
plt.gca().invert_yaxis()
plt.show()

```

**Output**

<img width="1045" height="717" alt="image" src="https://github.com/user-attachments/assets/3fdec997-29f0-42e8-a55a-034ac109cc69" />

**7.Draw Insights**


  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.
  
**Program**
```
print("=" * 60)
print("       EXPLORATORY DATA ANALYSIS - IPL DATASET")
print("=" * 60)

print("\n1. MATCHES PLAYED PER SEASON")
print("-" * 60)
print(matches_per_season.to_string())

print("\n2. TOP 5 WINNING TEAMS")
print("-" * 60)
print(top_teams.to_string())

print("\n3. TOSS DECISION ANALYSIS")
print("-" * 60)
print(toss_decisions.to_string())

print("\n4. TOP 5 STADIUMS HOSTING MAXIMUM MATCHES")
print("-" * 60)
print(top_venues.to_string())

print("\n" + "=" * 60)
print("          EDA ANALYSIS COMPLETED SUCCESSFULLY")
print("=" * 60)

```
**Output**

<img width="1037" height="772" alt="image" src="https://github.com/user-attachments/assets/d8e57f53-05ed-4f6e-b428-bbd3f271f2e7" />


***Result***


  This experiment is executed successfully

Highlight the stadiums hosting maximum matches.
