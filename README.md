# supply-chain-operations-analytics
Power BI analytics project analyzing supplier cost, quality, production, and operational efficiency.
# Supply Chain & Operations Efficiency Analytics

## Project Overview
This Power BI project analyzes supplier performance across manufacturing cost, quality, manufacturing speed, and shipping efficiency. The goal was to turn operational supplier data into a concise management dashboard without collapsing multiple metrics into an unsupported single supplier score.

## Business Question
How do suppliers compare across manufacturing cost, inspection and defect performance, manufacturing lead time, and shipping efficiency, and what operational patterns are most visible in the data?

## Tools Used
- Microsoft Power BI
- DAX
- CSV
- GitHub

## Dataset
The analysis uses 100 records across five suppliers. Relevant fields include revenue, production volume, units sold, manufacturing costs, defect rates, inspection results, manufacturing lead time, shipping time, shipping costs, and stock levels.

## Key Analytical Metrics
- Total Revenue
- Total Production
- Total Units Sold
- Average Defect Rate
- Inspection Failure Rate
- Manufacturing Cost Per Unit
- Average Shipping Cost
- Average Shipping Time
- Average Manufacturing Lead Time
- Cost Unit Variance vs. Overall Benchmark
- Defect Rate Variance vs. Overall Benchmark
- Production-to-Sales Ratio
- Stock-to-Production Ratio
- Supplier cost-per-unit ranking

## DAX Techniques Used
Aggregation with `SUM()` and `AVERAGE()`; conditional filtering with `CALCULATE()`; context modification with `ALL()`; safe division with `DIVIDE()`; supplier ranking with `RANKX()`; benchmark and variance calculations; conditional inspection analysis; supplier-level comparisons.

See the [`dax/`](dax/) folder for the documented measures.

## Key Findings

### 1. Supplier 4: Inspection and manufacturing-cost pattern
Supplier 4 shows a concentrated inspection and manufacturing-cost concern, with the highest inspection failure rate and manufacturing cost per unit among suppliers.
- Inspection failure rate: **67%**
- Manufacturing cost per unit: **$0.10**
- Average manufacturing cost for failed inspections: **$67.60**

### 2. Supplier 5: Defect and cycle-time pattern
Supplier 5 shows a stronger defect-rate and cycle-time concern, with the highest defect rate and longest manufacturing and shipping times.
- Average defect rate: **2.67**
- Defect-rate variance: **+17%**
- Manufacturing lead time: **16.33**
- Shipping time: **6.22**

### 3. Supplier 3: Shipping efficiency / quality tradeoff
Supplier 3 has the lowest shipping cost and shipping time, while its defect rate remains above the overall average.
- Average shipping cost: **$4.79**
- Average shipping time: **5.20**
- Average defect rate: **2.47**
- Defect-rate variance: **+8%**

### 4. Supplier 1: Relatively favorable quality / manufacturing speed
Supplier 1 shows relatively favorable defect and manufacturing lead-time results compared with the overall supplier benchmark.
- Average defect rate: **1.80**
- Manufacturing lead time: **12.59**
- Inspection failure rate: **22%**

## Analytical Caveats
- Findings are descriptive and identify observed patterns, not causal relationships.
- Inspection failure does not by itself prove rework, waste, or a specific root cause.
- Inspection failure rate and defect rate are different quality indicators and were kept separate.
- `Production - Sales` was not treated as inventory because reported stock levels did not reconcile with that difference.
- Stock-to-production ratio is treated as a descriptive relationship to reported stock, not inventory turnover or excess inventory.
- Supplier performance was intentionally not reduced to a single “best” or “worst” score.

## Dashboard
![Supply Chain & Operations Efficiency Analytics dashboard](images/project-3-dashboard.jpg)

## Project Conclusion
Supplier performance varies by operational dimension rather than following one universal pattern. Supplier 4's primary pattern is concentrated around inspection failures and manufacturing cost. Supplier 5's pattern is more closely associated with defects and cycle time. Supplier 3 combines favorable shipping measures with an above-average defect rate, while Supplier 1 shows relatively favorable defect and manufacturing lead-time results.

