# HR Data Insights 2.0 — Report Wireframe (Mockup)

Audience: HR / People managers
Model: `HR Data Insights 2.0.SemanticModel`
Canvas: 1280 x 720 (16:9)

Existing model inventory used by this mockup:

| Table | Key fields |
|---|---|
| Interview Responses | Consultation ID, Interview Date, Interview Score, Interview Outcome Key, Interviewer ID, Interview No., EmployeeID |
| Employee | Employee Name, Employee Region, Employee Position |
| Interviewer | Interviewer ID, Interviewer Name |
| Policy | Consultation ID, Consultation Start/End Date, Policy |
| Region | region |
| Sentiment | Sentiment Classification, Sentiment Score |
| Consultation Outcome | 1st/2nd Interview Outcome, Interview Outcome Sequence |
| Key Measures | Total Interviews, Total Employees, Happy/Unhappy/Neutral %, Sentiment Result - Happy/Unhappy/Neutral, Filters Label, Refresh date |

---

## Page 1 — Executive Overview

```
+----------------------------------------------------------------------------------+
| HR DATA INSIGHTS                                  Resfreshed Date : 12 Oct, 2026 |
|                                             [Region v] [Policy v] [Position v]     |
+----------------------------------------------------------------------------------+
| Filters (2/4)                                                                            |
|                                                                                        |
| +----------------+ +----------------+ +----------------+ +----------------+ +---------+ |
| | Total          | | Total          | | Happy %        | | Unhappy %      | | Total   | |
| | Interviews     | | Employees      | |                | |                | | Ongoing | |
| |                | |                | |  62.40 %       | |  18.10 %       | |  34     | |
| |    1,284       | |      412       | |  [icons]       | |  [icons]       | |         | |
| +----------------+ +----------------+ +----------------+ +----------------+ +---------+ |
|                                                                                        |
| +--------------------------------------+ +-----------------------------------------+ |
| | SENTIMENT TREND (monthly)            | | SENTIMENT SPLIT                        | |
| |                                      | |                                         | |
| |  100%                                | |   Happy    =====  62.4%               | |
| |    |      /\                         | |   Neutral  ====    19.5%              | |
| |  50%|  /\/   \      /\               | |   Unhappy  ==      18.1%              | |
| |    | /     \____/\/  \               | |                                         | |
| |   0+--------------------------------+ +-----------------------------------------+ |
| |    Jul   Aug   Sep   Oct             | |   (Donut + SVG status pills)           | |
| +--------------------------------------+ +-----------------------------------------+ |
|                                                                                        |
| +----------------------------+ +----------------------------+ +----------------------+ |
| | INTERVIEWS BY REGION      | | AVG INTERVIEW SCORE        | | TOP INTERVIEWERS     | |
| |                            | |                            | |                      | |
| | North  ####  420           | |      7.4  / 10             | | 1. A. Berrada  86%   | |
| | South  ###    312          | |  [trend sparkline]        | | 2. C. Mansour  81%   | |
| | East   ##     245          | |                            | | 3. S. Haddad   79%   | |
| | West   #      307          | |                            | |                      | |
| +----------------------------+ +----------------------------+ +----------------------+ |
+----------------------------------------------------------------------------------+
```

Notes
- Filters Label measure drives the "Filters (n/4)" indicator.
- Sentiment trend uses Consultation Start Date as the axis.
- Every visual cross-filters the whole page.

---

## Page 2 — Employee Detail

```
+----------------------------------------------------------------------------------+
| HR DATA INSIGHTS / Employee Detail                                [Back to Overview] |
+----------------------------------------------------------------------------------+
| +---------------------------+   +--------------------------------------------------+ |
| | EMPLOYEE HEADER (card)    |   | TIMELINE                                         | |
| |  Name     : Salma B.      |   |  12 Jun  Consultation start                      | |
| |  Region   : North          |   |  14 Jun  1st interview - score 7.2 - Happy       | |
| |  Position : Nurse          |   |  02 Jul  2nd interview - score 8.1 - Neutral      | |
| |  Policy   : Policy A       |   |  02 Jul  Outcome: Retained                       | |
| +---------------------------+   +--------------------------------------------------+ |
|                                                                                        |
| +----------------------------+  +----------------------------+ +----------------------+ |
| | INTERVIEW SCORES          |  | SENTIMENT COMPOSITION      | | POLICY COMPARISON    | |
| |                            |  |                            | |                      | |
| | 1st ### 7.2               |  |  Happy    #####            | |  Policy A  74%       | |
| | 2nd #### 8.1               |  |  Neutral  ###              | |  Policy B  68%       | |
| | Avg  7.65                  |  |  Unhappy  #                | |  Policy C  59%       | |
| +----------------------------+  +----------------------------+ +----------------------+ |
|                                                                                        |
| +----------------------------------------------------------------------------------+ |
| | INTERVIEW FEEDBACK (table: Interview Descrpt | Interviewer Name | Score | Sentiment |)  | |
| +----------------------------------------------------------------------------------+ |
```

---

## Page 3 — Interviewer Quality

```
+----------------------------------------------------------------------------------+
| HR DATA INSIGHTS / Interviewer Quality                                              |
+----------------------------------------------------------------------------------+
| +----------------+ +----------------+ +----------------+ +----------------+         |
| | Interviews     | | Avg Score      | | Happy %        | | Rehire Rate    |         |
| | Conducted      | |                | |                | |                |         |
| |     128        | |   7.8 / 10     | |   64.05 %      | |   72.4 %       |         |
| +----------------+ +----------------+ +----------------+ +----------------+         |
|                                                                                        |
| +--------------------------------------+ +-----------------------------------------+ |
| | SCORE BY INTERVIEW ROUND            | | OUTCOME DISTRIBUTION                   | |
| |  1st interview  ######  7.2         | |  Retained    48%                       | |
| |  2nd interview  ####### 8.3         | |  Withdrawn    22%                       | |
| |                                    | |  Rejected    30%                       | |
| +--------------------------------------+ +-----------------------------------------+ |
|                                                                                        |
| +----------------------------------------------------------------------------------+ |
| | INTERVIEWER SCORECARD (table, sorted ascending by Avg Score, conditional data bars) | |
| |  Interviewer | Interviews | Avg Score | Happy % | Unhappy % | Rehire % |                  | |
| +----------------------------------------------------------------------------------+ |
```

---

## Page 4 — Consultation Outcomes

```
+----------------------------------------------------------------------------------+
| HR DATA INSIGHTS / Consultation Outcomes                                             |
+----------------------------------------------------------------------------------+
| [Policy v] [Region v] [Interview Round v]                                            |
| +----------------------------------------------------------------------------------+ |
| | OUTCOME TREND BY MONTH                | 1st vs 2nd OUTCOME COMPARISON            | |
| |                                      |                                          | |
| |   1200 \                             |   1st interview   ########  41%          | |
| |    800  \__                          |   2nd interview   #######    59%          | |
| |    400     \__/\                     |                                          | |
| |         0  --------------------------|   (100% stacked bar)                    | |
| +--------------------------------------+-------------------------------------------+ |
|                                                                                        |
| +--------------------------------------+ +-------------------------------------------+ |
| | DURATION: START -> END               | | CONSULTATION VOLUME BY POLICY            | |
| |  Avg 41 days                         | |  Policy A  #####  420                    | |
| |  [box plot by policy]                | |  Policy B  ####   312                    | |
| +--------------------------------------+ +-------------------------------------------+ |
|                                                                                        |
| +----------------------------------------------------------------------------------+ |
| | OUTCOME DETAIL (matrix: Policy x Outcome, with Interview Outcome Sequence)          | |
| +----------------------------------------------------------------------------------+ |
```

---

## Global design notes

- Slicers, fixed left rail: Region, Policy, Interviewer Name, Employee Position.
- KPI cards always show measure + trend delta.
- Sentiment uses consistent colors: Happy green, Neutral amber, Unhappy red (from the theme palette).
- All visuals cross-filter; slicers are shared across pages.
- Refresh date measure placed in the top-right header on every page.

## Open questions

1. No explicit date table in the model - should I add one for month/year/time intelligence?
2. `Total Sentiment` counts Consultation ID, while `Total Interviews` counts Response Key - is the intent for "sentiment %" to be per response or per consultation?
3. Refresh date measure uses `TODAY() - 200`, which will drift. Should it be fixed or point to the max Consultation Start Date?
4. Region table has `region`, but Employee has `Employee Region` - is there a relationship between them, or are they independent?