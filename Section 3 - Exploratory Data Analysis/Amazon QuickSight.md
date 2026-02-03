# Amazon QuickSight – Key Points for the AWS Machine Learning Specialty Exam

This is a focused summary of Amazon QuickSight visualizations and features relevant to the exam, particularly on selecting appropriate visualizations given a dataset and analysis goal.

---

## QuickSight Dashboards
- **Dashboards** are snapshots of analyses.
- **Read-only:** Users can view but **cannot edit or change filters**.
- Used to **share assembled views of key business data** with other users who have QuickSight access.
  
---

## Visualization Types & Use Cases

### 1. **AutoGraph**
- Automatically suggests the most appropriate visualization based on the data's properties.
- Helps reveal relationships effectively but may sometimes require manual adjustment.

---

### 2. **Bar Charts**
- Used for **comparison and distribution** of categorical or time-period data.
- Can be **vertical or horizontal**.
- Example use case: Comparing sales by different regions.

---

### 3. **Line Charts (including Area and Stacked Area)**
- Best for **showing trends or changes over time**.
- Line charts show straightforward changes.
- Area and stacked area charts show how components add up to a total trend over time.

---

### 4. **Scatter Plots**
- Show **correlation between two continuous variables**.
- Useful to observe patterns, clusters, or relationships in raw data.
- Example: Waiting time vs eruption duration in geyser data.

---

### 5. **Heat Maps**
- Color-coded 2D grid visualizing data intensity or value distributions.
- Useful for correlation or rating matrices (e.g., reviewer ratings for restaurants).
- Colors represent magnitude (e.g., "hot" means high values).

---

### 6. **Pie and Donut Charts**
- **Pie charts:** Show proportions/aggregation of categorical data.
- Example: Population distribution of English native speakers.
- **Donut charts:** Similar to pie charts but better for showing percentages of a total when precision isn't critical and the number of categories is limited.

---

### 7. **Gauge Charts**
- Visualize a single measure relative to a target, similar to a dashboard gauge (e.g., fuel gauge).
- Shows how close a metric is to a goal.

---

### 8. **Tree Maps**
- Display **hierarchical data in nested rectangles** sized proportionally to value.
- Useful for showing hierarchical aggregations (e.g., export categories and subcategories).

---

### 9. **Pivot Tables**
- Tabular data aggregation tool.
- Summarizes multi-dimensional data.
- Enables applying statistical functions at intersections of dimensions (e.g., sales by region and date).

---

### 10. **KPIs (Key Performance Indicators)**
- Highlight key metric values compared to targets.
- Shows progress or status of important metrics quickly.

---

### 11. **Geospatial Charts**
- Maps with data points overlaid.
- Circle size usually represents the measure/value at that geographic location.
- Useful for visualizing location-based data (e.g., population by state).

---

### 12. **Word Clouds**
- Visualize text data frequency.
- Word or phrase size corresponds to how often it appears.
- Useful in analyzing unstructured text data sets (e.g., common words in a text corpus or destination names).

---

## Exam Tips: Visualization Selection

- **Look for the type of data and the question being asked:**
  - Changes over time? → **Line chart**
  - Comparison across categories or distributions? → **Bar chart**
  - Correlation between two variables? → **Scatter plot**
  - Aggregation of parts of a whole? → **Pie chart / Donut chart**
  - Hierarchical data aggregation? → **Tree map**
  - Multi-dimensional aggregation? → **Pivot table**
  - Tracking progress against targets? → **KPI / Gauge chart**
  - Geographic data? → **Geospatial chart**
  - Text frequency analysis? → **Word cloud**
  - Color-coded intensity or correlation? → **Heat map**
  - Unsure? → **AutoGraph** can suggest appropriate visuals.
  
- Remember **Dashboards = read-only snapshots** for sharing, not editing.

---

## Deprecated Features
- **Stories**: Previously a QuickSight feature, now deprecated and **no longer available**.

---

# Summary
Amazon QuickSight offers a broad set of visualization types tailored for different analytical needs. Understand the properties of your data and the primary question or insight you want, then match the visualization type accordingly — this will help you answer exam questions involving visualization choice confidently.

---
