# 📊 YouTube Shorts Posting Time Impact Analysis
## 🧭 Overview

This project analyzes the **impact of posting time on view performance** for short-form videos on YouTube.  
Using a quasi-experimental design on **3,143 videos** from **80+ channels**, it estimates how posting in different time windows (AM / Afternoon / Night) affects view counts after controlling for channel tier, theme, and video length.

The results show **significant heterogeneity across creator segments**, and provide a **data-driven scheduling strategy** with an estimated **10%+ uplift** in total views.


##  Dataset

| Metric                 | Value                                  |
|------------------------|-----------------------------------------|
| Time Range             | 2025-01-01 to 2025-09-30 (UTC)          |
| Sample Size            | 3,143 videos                            |
| Channels               | 80+                                    |
| Features               | Posting time, theme, duration, views, likes, comments |
| Time Buckets           | AM (06–11), Afternoon (12–19), Night (20–23) |

- Custom Python crawler was used to collect structured metadata.
- Data stored and managed in a local SQL database.
- Posting time was bucketed into AM / Afternoon / Night.


##  Methodology

1. **Quasi-Experimental Design**
   - Within-channel matched pairs based on duration bucket.
   - Fixed-effects OLS controlling for weekday, theme, duration, and channel tier.

2. **Effect Estimation**
   - Average effect of **Night vs AM**: `+9.9%` on views (not significant overall).
   - **Afternoon** posting caused a significant **−55% drop** for mid/top channels (*p < 0.05*).
   - Night effect concentrated in long-tail channels.

3. **Segmentation**
   - Applied K-means clustering on posting-time distributions.
   - Identified three creator segments: AM-heavy, Afternoon-heavy, Night-heavy.

4. **Strategy Design**
   - Reallocating ~30% of mid/top **Afternoon posts** to AM/Night is estimated to yield a **~10% total view uplift**.
   - Designed stratified **A/B testing plan** for future validation.


##  Key Findings

- Night posting provides moderate positive lift overall, strongest in long-tail creators.  
- Afternoon posting underperforms significantly for mid/top-tier channels.  
- Clustering creators by posting behavior allows for **targeted scheduling recommendations**.



