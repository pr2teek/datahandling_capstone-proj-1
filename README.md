# Social Media Engagement & Content Performance Dashboard

Capstone project for **Data Handling, Visualization & Feature Engineering (AML001)**
BCA (Hons.) AI & Data Science, KR Mangalam University

**Name:** Navya Goyal | **Roll No:** 2601201013 | **Section:** BCA (AI & DS) (H) - B

---

## Overview

A social media team wants to know how audiences react to its content across platforms, so that posting decisions are based on evidence instead of guesswork. This project explores a dataset of 30 posts and builds an interactive Plotly dashboard that answers three questions:

1. How strongly are likes, shares and comments related to each other?
2. Which platform earns the most and the least engagement per post?
3. How is engagement spread across posts, and how does it change over the posting period?

Each chart title states its finding, so a non-technical reader can understand the result at a glance.

## Dataset

The dataset was created for this exercise inside the notebook. It has **30 posts** and **6 columns**, with 6 posts on each of 5 platforms. One derived column, `Total_Engagement` (Likes + Shares + Comments), is added for the analysis.

| Column | Type | Description |
|---|---|---|
| `Post_ID` | Number | Unique post number (1 to 30) |
| `Likes` | Number | Number of likes on the post |
| `Shares` | Number | Number of shares of the post |
| `Comments` | Number | Number of comments on the post |
| `Platform` | Category | Instagram, Facebook, YouTube, LinkedIn or X |
| `Post_Date` | Date | Date the post was published (1 to 30 January 2026) |
| `Total_Engagement` | Number (derived) | Likes + Shares + Comments |

## Approach

The project follows the pipeline taught in the course: **Explore, Analyze, Visualize, Layout, Story.**

1. **Inspect** the data with `shape`, `info()`, `describe()` and `value_counts()`.
2. **Correlate** likes, shares and comments with a correlation matrix and heatmap.
3. **Group** posts by platform with `groupby()` to compare average engagement.
4. **Visualize** the data with four chart types.
5. **Combine** the charts into one interactive Plotly dashboard, arranged by importance.
6. **Export** the dashboard as a standalone HTML file.

## Dashboard

The dashboard is a 2x2 interactive Plotly figure.

| Position | Chart | Title (states the finding) |
|---|---|---|
| Top-left | Bar chart | YouTube and X Lead on Engagement, Instagram Trails Far Behind |
| Top-right | Scatter plot | Posts With More Likes Also Get More Comments and Shares |
| Bottom-left | Histogram | Most Posts Earn Between 250 and 750 Total Engagements |
| Bottom-right | Line chart | Engagement Per Post Trends Upward Through January |

Design choices:

- The most important chart (platform comparison) is placed top-left.
- Each platform keeps the same colour in every chart.
- Bar chart axes start at zero, so differences are not exaggerated.
- The line chart is sorted by date before plotting.
- Interactivity: hover tooltips, zoom, and legend clicks to hide or show platforms.

<!-- Add a screenshot of your dashboard here, for example:
![Dashboard preview](screenshots/dashboard.png)
-->

## Key Findings

- Likes, shares and comments are almost perfectly correlated (about 0.997 to 0.999).
- **YouTube** has the highest average engagement (about 703 per post), followed very closely by **X** (about 695). **Instagram** has the lowest (about 242).
- The best single post is Post 28 on YouTube, with 1,065 total engagements.
- 18 of the 30 posts earn between 250 and 750 total engagements.
- Average engagement per post is higher in the second half of January (about 631) than in the first half (about 479).

| Platform | Avg. Likes | Avg. Shares | Avg. Comments | Avg. Engagement | Total Engagement | Posts |
|---|---|---|---|---|---|---|
| YouTube | 531.67 | 104.17 | 67.33 | 703.17 | 4,219 | 6 |
| X | 525.00 | 104.17 | 66.17 | 695.33 | 4,172 | 6 |
| Facebook | 440.00 | 86.67 | 56.50 | 583.17 | 3,499 | 6 |
| LinkedIn | 416.67 | 80.33 | 53.33 | 550.33 | 3,302 | 6 |
| Instagram | 186.67 | 32.67 | 23.00 | 242.33 | 1,454 | 6 |

## Repository Contents

| File | Description |
|---|---|
| `Social_Media_Dashboard.ipynb` | Main notebook with all code and outputs |
| `Social_Media_Dashboard.html` | Exported interactive dashboard (opens in any browser) |
| `README.md` | Project description and execution steps |

## How to Run

### Option 1: Google Colab (recommended)

1. Open [Google Colab](https://colab.research.google.com) and choose **File > Upload notebook**.
2. Upload `Social_Media_Dashboard.ipynb`.
3. Click **Runtime > Run all**.
4. The dashboard appears in the notebook and is saved as `Social_Media_Dashboard.html`.

### Option 2: Run locally

1. Install Python 3.9 or newer.
2. Install the libraries:
   ```bash
   pip install pandas numpy matplotlib plotly jupyter
   ```
3. Start Jupyter and open the notebook:
   ```bash
   jupyter notebook Social_Media_Dashboard.ipynb
   ```
4. Run all cells. The cell that imports `google.colab` only works in Colab, so skip it when running locally. The HTML file is still saved in the notebook's folder.

### View the dashboard without running any code

Download `Social_Media_Dashboard.html` and open it in a web browser. It stays fully interactive.

## Tools

Python, Pandas, NumPy, Matplotlib, Plotly, Google Colab.

## Limitations

- The dataset has only 30 records and was created for this exercise, so the findings should not be generalised to real social media accounts.
- Correlation does not prove causation.
- Likes, shares and comments are almost perfectly correlated, which real data rarely is.
- Platforms rotate in a fixed order across consecutive days, so the trend over time is mixed with platform differences.
- This project covers the exploration and dashboard stage only. It does not train a machine-learning model.

## Future Scope

- Test the dashboard on real or larger social media data.
- Add reach and impressions, and engineered features such as engagement rate.
- Build a reusable preprocessing pipeline.
