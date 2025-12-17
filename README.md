* Appreciated if anyone can share me the Qlik license to continue of this work.

# Analytical Calendar

Analytical Calendar is an innovative design for time intelligence in Qlik dashboards.  It fully integrates into the green-white-grey design and fits very well into the associative data model. 

Instead of having complicated calculations in the set analysis, it tries to incorporate all the calculations inside the data model such that once you select, the dashboard reflects directly.

Date looks easy but very complicated.  You might feel it when you apply selection and change it.  If you are a developer, you must understand the pain!

So, here, the analytical calendar has a new design:
1. Unique Date (i.e. 2025, 2025-Q1, 2025-Jan, 2025-W1, 2025-01-01, etc.)  All uniqueness of representing a date range.
2. Analysis Perspective (Actual, YTD, MTD, QTD, YTM, rolling, etc), all valid and possible date range representation.
3. Comparison Perspective (1 day before, 1 month before, 2 weeks before, etc) all valid and possible comparison.

![alt text](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjd2XMh3641spT7tdGCHrAxiXGpEUlZQ8c4hjjDm_wDRSMi0sBH_ZIMxEUwNNHUlyuf1kxi9e1_eLHsCN5Fa3veUfk8SwORHFNQ_Im7zdT3UgQ0hHVF9PM09FhlkxJZ2lXQAha4HAK05pLvf3KHF7uphWEAAIceUluVeByVklDX2mucecZ9E0zMy4ZmTJ4/w640-h322/Analytical%20Calendar%20Complete%20Week%20with%20Custom_Perspective_view.png)

Take a look and enjoy!

* I am trying to manipulate the same in Tableau and PowerBI but because of the fundamental differences of query-based vs assocaitive model, it might not fully show the power of the analytical calendar.   Welcome comments and suggestions. Thanks!

## The analytical calendar (Qlik qvs) Available.
- AnalyticalCalendar.qvs (https://github.com/kongson-cheung/analytical-calendar/blob/main/AnalyticalCalendar.qvs)

Use the QVS to help you generate the analytical calendar.   Please make sure your Fact table with a date field as %DATE_KEY to associate with the analytical calendar.

The following are the parameters to customise:
* **vStartDate** - It is the start date of the calendar.
* **vEndDate** - It is the end date of the calendar.
* **vMaxYRolling** - It is the maximum rolling years.
* **vMaxQRolling** - It is the maximum rolling year quarters.
* **vMaxMRolling** - It is the maximum rolling year months.
* **vMaxWRolling** - It is the maximum rolling year weeks.
* **vMaxDRolling** - It is the maximum rolling days.
* **vMaxYComparison** - It is the maximum comparison year range.
* **vMaxQComparison** - It is the maximum comparison year quarter range.
* **vMaxMComparison** - It is the maximum comparison year month range.
* **vMaxWComparison** - It is the maximum comparison year week range.
* **vMaxDComparison** - It is the maximum comparison date range.

It includes bother Incomplete Week (Broken Week) or Complete Week (Unbroken Week).  So, pick one of the week usage and remove the one that you do not want to use.


## The analytical calendar for 2022 to 2026 is available.
- [ANALYTICAL_CALENDAR.qvd](https://github.com/kongson-cheung/analytical-calendar/raw/refs/heads/main/Analytical%20Calendar%20QVD/2022-2026/ANALYTICAL_CALENDAR.qvd)
- [DIM_CALENDAR.qvd](https://github.com/kongson-cheung/analytical-calendar/raw/refs/heads/main/Analytical%20Calendar%20QVD/2022-2026/DIM_CALENDAR.qvd)
- [LINKED_TABLE_DATE_RANGE.qvd](https://github.com/kongson-cheung/analytical-calendar/blob/main/Analytical%20Calendar%20QVD/2022-2026/LINKED_TABLE_DATE_RANGE.qvd)

Load these three tables (e.g. using web file) and then load your Fact table with a date field as %DATE_KEY.  You can start enjoy the benefit of the analytical calendar.


## How to Make Use of the Analytical Calendar
In general, you will just need two similar expressions.
- analysis period, sum({<[Comparison Perspective]={'N/A'}>} Exp1)
- comparison period, sum(Exp1)

All charts are now integrated to the green-white-grey with both the analysis period and comparison period!!

Enjoy!


# Kongson Blog
If you like to explore more from me, please go to my blog [Kongson Technology Blog](https://kongsoncheung.blogspot.com/).

And if you find it great, support me via [Buy Me Coffee](https://buymeacoffee.com/kongsoncheung).
