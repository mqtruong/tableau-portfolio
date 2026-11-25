# Global Development & Health Analysis

### Life Expectancy, Economic Prosperity, and Global Inequality | 1952–2007

## Project Overview

This project explores the relationship between economic development, population health, and global inequality across 142 countries using Tableau. Through interactive dashboards, statistical modeling, advanced visualizations, and data storytelling, the analysis identifies historical improvements in life expectancy, regional disparities, and countries that outperform or underperform relative to their economic development.

## Problem Statement

Economic prosperity is often associated with improved health outcomes. However, GDP per capita alone may not adequately explain differences in life expectancy across countries.

This analysis addresses the following questions:

- How has life expectancy evolved across countries and continents between 1952 and 2007?
- What is the relationship between GDP per capita and life expectancy?
- Which countries outperform or underperform their GDP-predicted life expectancy?
- Which countries have experienced the greatest improvements in life expectancy?
- Has global inequality in life expectancy narrowed over time?

The objective is to generate insights that can support public health research, international development initiatives, and evidence-based decision-making.

## Data Source and Description

**Source:** [Gapminder Dataset — Plotly Data Repository](https://github.com/plotly/datasets/blob/master/gapminderDataFiveYear.csv)

| Attribute | Description |
|---|---|
| Geographic Coverage | 142 countries across 5 continents |
| Time Period | 1952–2007 |
| Frequency | Five-year intervals |
| Unit of Analysis | Country-year observations |
| Data Type | Historical socioeconomic and demographic data |

### Key Variables

| Variable | Description |
|---|---|
| Country | Country name |
| Continent | Geographic classification |
| Year | Observation year |
| Life Expectancy | Average life expectancy in years |
| GDP per Capita | Economic output per person |
| Population | Total country population |

## Tools and Technologies

- Tableau Desktop
- FIXED Level of Detail (LOD) Expressions
- Calculated Fields
- Interactive Parameters and Filters
- Regression and Residual Analysis
- Geographic Data Visualization
- Dashboard Development
- Animated Visualizations
- Tableau Stories and Data Storytelling

## Analytical Methodology

### Exploratory Data Analysis

Historical trends, distributions, and geographic patterns were examined using scatterplots, line charts, box plots, heatmaps, and choropleth maps.

GDP per capita was displayed on a logarithmic scale to improve interpretability across countries with substantially different income levels.

### Level of Detail Expressions

Country-level and year-level FIXED LOD expressions were developed to enable consistent comparisons independently of the visualization's level of detail.

**Country-Level Life Expectancy — 1952**

```tableau
{ FIXED [country] :
    MAX(
        IF [year] = 1952
        THEN [lifeExp]
        END
    )
}
```

**Country-Level Life Expectancy — 2007**

```tableau
{ FIXED [country] :
    MAX(
        IF [year] = 2007
        THEN [lifeExp]
        END
    )
}
```

These calculations were used to measure long-term improvements in life expectancy at the country level.

**Maximum Life Expectancy by Year**

```tableau
{ FIXED [year] :
    MAX([lifeExp])
}
```

**Minimum Life Expectancy by Year**

```tableau
{ FIXED [year] :
    MIN([lifeExp])
}
```

The difference between these measures was used to evaluate the gap between the highest and lowest country-level life expectancy outcomes over time.

### Regression and Residual Analysis

A logarithmic regression model was used to examine the relationship between GDP per capita and life expectancy across 142 countries in 2007.

**Regression equation:**

```text
Predicted Life Expectancy = 4.94961 + 7.2028 × ln(GDP per Capita)
```

| Model Metric | Result |
|---|---:|
| R-squared | 0.654 |
| P-value | < 0.0001 |
| Countries Analyzed | 142 |

Residuals were calculated as the difference between actual and predicted life expectancy.

Positive residuals indicate countries exceeding their GDP-predicted life expectancy, while negative residuals identify countries performing below the model's expectations.

## Interactive Dashboards

### Dashboard 1 — Economic Development & Health

![Economic Development and Health Dashboard](./images/Dashboard%201%20-%20Economic%20Development%20%26%20Health.png)

This dashboard examines the historical relationship between economic prosperity and population health.

Key features include:

- Animated GDP per capita versus life expectancy bubble chart
- Population-based bubble sizing
- Continent-level life expectancy trends
- Logarithmic regression analysis for 2007
- Interactive exploration of economic and health indicators

### Dashboard 2 — Global Health Inequality

![Global Health Inequality Dashboard](./images/Dashboard%202%20-%20Global%20Health%20Inequality.png)

This dashboard examines geographic disparities, country-level improvements, and deviations from expected health outcomes.

Key features include:

- Interactive global choropleth map
- Continent-level life expectancy distributions
- Diverging residual analysis
- Top 15 countries by life expectancy improvement
- Dynamic metric selection and interactive controls

## Advanced Visualizations

| Visualization | Analytical Purpose |
|---|---|
| Animated Bubble Scatterplot | Explore economic and health development over time |
| Multi-Series Line Chart | Compare historical life expectancy trends across continents |
| Box-and-Whisker Plot | Evaluate regional distributions and variability |
| Heatmap | Identify geographic and temporal patterns |
| Ranked Horizontal Bar Chart | Identify countries with the greatest life expectancy gains |
| Diverging Residual Bar Chart | Identify countries above or below GDP-predicted outcomes |
| Regression Scatterplot | Quantify the relationship between income and life expectancy |
| Line and Area Chart | Evaluate the historical global life expectancy gap |
| Interactive Choropleth Map | Examine geographic disparities using selectable metrics |

Two Tableau stories organize these visualizations into analytical narratives focused on economic development and global health inequality.

## Key Findings and Insights

### 1. Global Life Expectancy Improved

Average life expectancy increased across all five continents between 1952 and 2007.

Asia experienced an improvement of approximately 24.4 years in continent-average life expectancy. Despite overall progress, Africa remained the continent with the lowest average life expectancy in 2007, at approximately 54.8 years.

### 2. Economic Prosperity Is Strongly Associated with Health Outcomes

GDP per capita accounted for approximately 65.4% of the cross-country variation in life expectancy within the 2007 regression model.

The relationship was statistically significant, suggesting that economic development is an important indicator of population health. However, the observational relationship does not establish causation.

### 3. GDP Alone Does Not Fully Explain Health Outcomes

Residual analysis identified substantial differences between actual and predicted life expectancy.

| Country | Life Expectancy Residual |
|---|---:|
| Vietnam | +13.1 years |
| Swaziland (now Eswatini) | −25.9 years |

These findings suggest that additional socioeconomic, institutional, environmental, and healthcare-related factors may help explain differences in national health outcomes.

### 4. Several Countries Achieved Substantial Health Improvements

| Country | Life Expectancy Gain, 1952–2007 |
|---|---:|
| Oman | +38.1 years |
| Vietnam | +33.8 years |
| Indonesia | +33.2 years |

These countries represent potential case studies for further research into long-term improvements in population health.

### 5. Global Health Inequality Remained Persistent

| Year | Maximum–Minimum Life Expectancy Gap |
|---|---:|
| 1952 | 43.87 years |
| 1992 | 55.76 years |
| 2007 | 42.99 years |

Although life expectancy improved globally, the difference between the highest and lowest country-level outcomes remained substantial.

The gap peaked in 1992 before narrowing by 2007, indicating that improvements in global health were not distributed uniformly.

## Recommendations

- Evaluate life expectancy alongside GDP per capita rather than relying on economic output alone as an indicator of development.
- Investigate countries with large negative residuals to identify potential barriers to improved health outcomes.
- Examine countries that outperform their predicted life expectancy to identify potential lessons for public health research.
- Incorporate additional socioeconomic and healthcare indicators into future analytical models.
- Monitor regional disparities and long-term health inequality alongside aggregate improvements.

## Limitations

| Limitation | Analytical Impact |
|---|---|
| Historical data ending in 2007 | Findings do not necessarily reflect current global health conditions. |
| Five-year observation intervals | Short-term changes and fluctuations may not be captured. |
| National-level aggregates | Within-country socioeconomic and geographic disparities are not represented. |
| Observational data | Statistical relationships cannot establish causal effects. |
| Single-predictor regression | GDP per capita does not capture all factors influencing life expectancy. |
| Maximum–minimum inequality metric | Results are sensitive to extreme country-level observations. |
| Country coverage | Findings are limited to the countries represented in the dataset. |

Continent-level averages are descriptive country-level averages and should not be interpreted as population-weighted estimates.

These limitations should be considered when interpreting the findings or applying them to public health and international development decisions.

## Conclusion

The project successfully addressed its primary exploratory objectives by identifying historical improvements in life expectancy, quantifying the relationship between economic development and health outcomes, and highlighting persistent global disparities.

The regression and residual analyses demonstrated that GDP per capita is an important but incomplete indicator of life expectancy. Interactive dashboards and advanced visualizations enabled comparisons across countries, continents, and historical periods.

While the analysis cannot establish causal relationships or provide definitive policy interventions, it offers a foundation for identifying health disparities, prioritizing further research, and supporting evidence-based discussions surrounding global development.

## Project Files

| File | Description |
|---|---|
| [Tableau Workbook](./workbooks/Global_Development_Health.twbx) | Interactive packaged Tableau workbook |
| [Project Presentation](./presentations/Global_Development_Health_Presentation.pdf) | Detailed analytical presentation |
| [Dashboard Images](./images/) | Dashboard previews |
| [Source Dataset](https://github.com/plotly/datasets/blob/master/gapminderDataFiveYear.csv) | Original Gapminder data |

## Author

**Minh Truong**

Business Analytics | Data Visualization | Business Intelligence

[GitHub Profile](https://github.com/mqtruong)
