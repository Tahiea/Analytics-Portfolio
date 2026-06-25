### Finance KPI: Revenue and Forecast Dashboard

One of the key challenges in this project was creating a realistic view of annual revenue performance while the financial year was still in progress.
The business required a KPI framework that could simultaneously report:

* Revenue already received
* Expected recurring subscription revenue
* Sales pipeline forecasts
* Full-year projected performance

To achieve this, I developed a hybrid Actual + Forecast model.

For completed periods, the dashboard uses actual revenue received. For future periods, the actuals are replaced with:

* Expected subscription revenue already contracted but not yet invoiced
* Forecasted revenue provided by the sales team

This allowed management to monitor both historical performance and projected year-end outcomes within the same reporting framework.

The resulting logic follows the structure below:

| Reporting Period             | Revenue Source                        |
| ---------------------------- | ------------------------------------- |
| January to Current Month - 1 | Actual Revenue                        |
| Current Month onwards        | Subscription Revenue + Sales Forecast |

This approach ensured that future projections reflected both secured recurring income and expected sales activity.

---

#### Custom Month-on-Month Growth Calculations

The original reporting requirement was to compare monthly performance against the previous reporting period.

Built-in DAX Time Intelligence functions were initially evaluated, but did not consistently return the required results within the reporting structure and business requirements.

To gain full control over period comparisons, I implemented custom Month-on-Month calculations using explicit month and year logic.

The solution manually identifies:

* Current reporting month
* Previous reporting month
* Previous reporting year when crossing year boundaries

This approach correctly handles transitions such as:

| Current Period | Comparison Period |
| -------------- | ----------------- |
| February 2025  | January 2025      |
| January 2025   | December 2024     |

The custom implementation provided consistent KPI calculations regardless of reporting period selection.

---

#### Custom Year-on-Year Growth Calculations

Year-on-Year growth measures were developed using similar principles.

Rather than relying entirely on built-in date intelligence functions, the logic explicitly identifies the equivalent period in the previous year and compares performance against that baseline.

This provided greater transparency over how comparisons were calculated and ensured consistency across the finance reporting model.

The resulting KPIs enabled stakeholders to monitor long-term revenue growth trends and identify changes in business performance over time.

---

#### Subscription Revenue Modelling

Recurring subscription revenue represented a key performance metric for the business.

To support this requirement, dedicated DAX measures were created to isolate subscription income from non-recurring revenue streams.

During development, source data quality issues were identified where subscription products were recorded under inconsistent naming conventions.

Rather than relying on upstream data corrections, defensive DAX logic was implemented to ensure all valid subscription transactions were included within KPI calculations.

This ensured that recurring revenue metrics remained accurate despite inconsistencies in the source systems.

---

#### Forecast Scenario Analysis

The reporting model included multiple forecast scenarios to support planning and performance reviews.

Separate measures were developed for:

* Base Forecast
* Committed Forecast
* Stretch Forecast
* Target Forecast

This enabled management to evaluate business performance under different assumptions and assess progress against varying levels of expected revenue achievement.

---

#### Rolling 12-Month Revenue Analysis

Monthly revenue performance was highly susceptible to short-term fluctuations and seasonality.

To provide a more stable view of performance, rolling twelve-month measures were developed.

The rolling calculations aggregate revenue across a moving twelve-month window, allowing stakeholders to focus on underlying growth trends rather than isolated monthly variations.

This significantly improved trend analysis and executive reporting.

---

#### Dynamic KPI Framework

DAX was used extensively throughout the model not only for calculations but also for report usability.

Dynamic measures were developed to:

* Generate KPI titles
* Update labels based on selected periods
* Display contextual reporting information
* Support interactive filtering and drill-down analysis

This reduced report maintenance and ensured KPI definitions remained aligned with user selections.

---

#### Technical Skills Demonstrated

* Advanced DAX Development
* Custom Time Intelligence Calculations
* Financial Performance Reporting
* Revenue Forecasting
* Subscription Revenue Modelling
* Forecast Scenario Analysis
* Rolling Period Analytics
* Star Schema Data Modelling
* KPI Development
* Business Performance Analytics
* Data Quality Remediation within DAX
* Executive Reporting Design

---




