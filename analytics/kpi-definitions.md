# KPI Definitions & Dashboard Requirements
### SmartWeather Analytics Platform | Power BI Dashboard Specifications

---

## 📌 Purpose

This document defines the KPIs, dashboard specifications, and reporting requirements 
for the SmartWeather Analytics platform across three industry verticals — Tourism, 
Healthcare, and Retail.

---

## 📊 Dashboard Overview

| Dashboard | Industry | Primary Users |
|---|---|---|
| 1. Platform Overview | All | Platform Administrator |
| 2. Tourism Analytics | Tourism | Tourism Managers, Analysts |
| 3. Healthcare Risk | Healthcare | Healthcare Operations, Planners |
| 4. Retail Demand | Retail | Merchandising, Marketing Managers |

---

## 🔢 KPI Definitions

### Dashboard 1 — Platform Overview

| KPI | Definition | Target |
|---|---|---|
| Active Data Sources | Count of weather API sources currently connected and returning data | ≥ 2 at all times |
| Data Freshness | Time since last successful data refresh across all sources | < 60 minutes |
| API Success Rate | % of API calls returning valid data in last 24 hours | > 99% |
| Failed API Calls | Count of failed API calls in last 24 hours | 0 target |
| Data Coverage | % of configured locations with current weather data available | 100% |

### Dashboard 2 — Tourism Analytics

| KPI | Definition | Target |
|---|---|---|
| Seasonal Demand Index | Composite score (0-100) indicating expected tourism demand based on weather forecast | — |
| Peak Season Weeks | Count of weeks in selected period where Demand Index > 75 | — |
| Sunshine Hours Forecast | Average daily sunshine hours forecast for selected destination and period | — |
| Precipitation Probability | % probability of rainfall for selected destination and date range | — |
| Temperature Range | Min and max forecast temperature for selected destination and period | — |
| Destination Comparison Score | Relative demand index score across selected destinations for side-by-side comparison | — |

### Dashboard 3 — Healthcare Risk

| KPI | Definition | Target |
|---|---|---|
| Respiratory Risk Index | Composite risk score (Low/Medium/High) based on cold, damp, and air quality conditions | Monitor |
| Heat Stress Risk Index | Risk score based on forecast temperature and humidity levels | Monitor |
| Allergy Risk Index | Pollen and allergen risk score based on weather and seasonal data | Monitor |
| High Risk Days Forecast | Count of days in next 14 days where any risk index = High | — |
| Alert Response Time | Time from risk threshold breach to alert sent to healthcare planner | < 1 hour |

### Dashboard 4 — Retail Demand

| KPI | Definition | Target |
|---|---|---|
| Weather Demand Index | Expected % change in product category demand driven by weather forecast | — |
| Forecast Confidence | % confidence level of the demand forecast based on data quality and historical accuracy | > 70% |
| Forecast Accuracy (Historical) | % accuracy of previous weather-driven demand forecasts vs actual sales | Track trend |
| Optimal Promotion Windows | Count of weather-triggered promotion opportunities identified in next 30 days | — |
| Expected Demand Uplift % | Projected % increase in demand during identified promotion windows | — |

---

## 📐 Calculated Measures
Seasonal Demand Index (Tourism)
Demand Index =
(Sunshine Hours Score * 0.4) +
(Temperature Score * 0.3) +
(Precipitation Score * 0.3)
Where each score is normalised 0-100 based on historical optimal ranges
-- API Success Rate
API Success Rate % =
DIVIDE(
COUNT(Successful API Calls),
COUNT(Total API Calls),
0
) * 100
-- Forecast Accuracy (Retail)
Forecast Accuracy % =
100 - AVERAGE(ABS(Forecast Demand % - Actual Demand %))
-- High Risk Days Count (Healthcare)
High Risk Days =
COUNTROWS(
FILTER(ForecastData,
ForecastData[RespiratoryRisk] = "High" ||
ForecastData[HeatStressRisk] = "High" ||
ForecastData[AllergyRisk] = "High"
)
)
---

## 🎛️ Filters & Slicers

| Filter | Applies To | Options |
|---|---|---|
| Date Range | All dashboards | Next 7 / 14 / 30 days / Custom |
| Location / Region | All dashboards | Configured locations list |
| Industry | Platform Overview | Tourism / Healthcare / Retail / All |
| Product Category | Retail dashboard | Configured categories |
| Risk Type | Healthcare dashboard | Respiratory / Heat / Allergy / All |

---

## 🔔 Alert Requirements

| Alert | Trigger | Recipient | Channel |
|---|---|---|---|
| API source failure | API success rate drops below 95% | Platform Administrator | Email within 5 mins |
| Data staleness | No refresh in > 2 hours | Platform Administrator | Email |
| Healthcare risk threshold | Any risk index reaches High | Healthcare Planner | Email within 1 hour |
| High demand window | Tourism Demand Index > 75 for next 7 days | Tourism Manager | Email daily digest |
| Promotion opportunity | Retail demand uplift > 20% forecast | Marketing Manager | Email weekly digest |

---

## 📋 Acceptance Criteria (Key Examples)

**Platform Overview — Data Freshness**
- Given the platform data ingestion service is running
- When a user views the Platform Overview dashboard
- Then the Data Freshness KPI shall show time since last successful refresh
- And if data is older than 60 minutes the KPI shall be highlighted in amber
- And if older than 2 hours it shall be highlighted in red

**Tourism — Seasonal Demand Index**
- Given a tourism user selects a destination and date range
- When the Tourism Analytics dashboard loads
- Then the Seasonal Demand Index shall display a score between 0 and 100
- And the score shall be colour coded: 0-40 Low (red), 41-74 Medium (amber), 75-100 High (green)

**Healthcare — Alert Response Time**
- Given a healthcare risk index reaches High for a configured region
- When the threshold is breached
- Then an alert email shall be sent to the healthcare planner within 1 hour
- And the alert shall include: region, risk type, current level, and forecast duration

---

## 📈 Reporting Schedule

| Report | Frequency | Audience |
|---|---|---|
| Platform health summary | Daily 07:00 | Platform Administrator |
| Tourism demand digest | Daily 08:00 | Tourism Managers |
| Healthcare risk briefing | Daily 07:30 | Healthcare Operations |
| Retail weekly demand forecast | Every Monday 08:00 | Merchandising & Marketing |
| Monthly analytics performance | 1st of each month | All stakeholders |

---

## 📁 Related Documents

- [User Stories](../agile/user-stories.md)
- [Sprint Plan](../agile/sprint-plan.md)
- [Retrospective Notes](../agile/retrospective-notes.md)

---

*Produced by Rupesh Surve | Business Analyst | Part of SmartWeather Agile Scrum Portfolio*
