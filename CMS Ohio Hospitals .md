```python
# IMPORTS + LOAD CMS COST REPORT (CCR) DATA

import pandas as pd
import numpy as np

# Load data
cms_ccr = pd.read_csv("/Users/abdulrahmanalali/Desktop/GitHub Projects/CMS Project/Hospital Provider Cost Report/2023/CostReport_2023_Final.csv")

# Preview
pd.set_option('display.max_columns', None)
pd.reset_option("display.max_rows")

display(cms_ccr)

```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rpt_rec_num</th>
      <th>Provider CCN</th>
      <th>Hospital Name</th>
      <th>Street Address</th>
      <th>City</th>
      <th>State Code</th>
      <th>Zip Code</th>
      <th>County</th>
      <th>Medicare CBSA Number</th>
      <th>Rural Versus Urban</th>
      <th>CCN Facility Type</th>
      <th>Provider Type</th>
      <th>Type of Control</th>
      <th>Fiscal Year Begin Date</th>
      <th>Fiscal Year End Date</th>
      <th>FTE - Employees on Payroll</th>
      <th>Number of Interns and Residents (FTE)</th>
      <th>Total Days Title V</th>
      <th>Total Days Title XVIII</th>
      <th>Total Days Title XIX</th>
      <th>Total Days (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds</th>
      <th>Total Bed Days Available</th>
      <th>Total Discharges Title V</th>
      <th>Total Discharges Title XVIII</th>
      <th>Total Discharges Title XIX</th>
      <th>Total Discharges (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds + Total for all Subproviders</th>
      <th>Hospital Total Days Title V For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Days (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Hospital Number of Beds For Adults &amp; Peds</th>
      <th>Hospital Total Bed Days Available For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title V For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Discharges (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Cost of Charity Care</th>
      <th>Total Bad Debt Expense</th>
      <th>Cost of Uncompensated Care</th>
      <th>Total Unreimbursed and Uncompensated Care</th>
      <th>Total Salaries From Worksheet A</th>
      <th>Overhead Non-Salary Costs</th>
      <th>Depreciation Cost</th>
      <th>Total Costs</th>
      <th>Inpatient Total Charges</th>
      <th>Outpatient Total Charges</th>
      <th>Combined Outpatient + Inpatient Total Charges</th>
      <th>Wage-Related Costs (Core)</th>
      <th>Wage-Related Costs (RHC/FQHC)</th>
      <th>Total Salaries (adjusted)</th>
      <th>Contract Labor: Direct Patient Care</th>
      <th>Wage Related Costs for Part - A Teaching Physicians</th>
      <th>Wage Related Costs for Interns and Residents</th>
      <th>Cash on Hand and in Banks</th>
      <th>Temporary Investments</th>
      <th>Notes Receivable</th>
      <th>Accounts Receivable</th>
      <th>Less: Allowances for Uncollectible Notes and Accounts Receivable</th>
      <th>Inventory</th>
      <th>Prepaid Expenses</th>
      <th>Other Current Assets</th>
      <th>Total Current Assets</th>
      <th>Land</th>
      <th>Land Improvements</th>
      <th>Buildings</th>
      <th>Leasehold Improvements</th>
      <th>Fixed Equipment</th>
      <th>Major Movable Equipment</th>
      <th>Minor Equipment Depreciable</th>
      <th>Health Information Technology Designated Assets</th>
      <th>Total Fixed Assets</th>
      <th>Investments</th>
      <th>Other Assets</th>
      <th>Total Other Assets</th>
      <th>Total Assets</th>
      <th>Accounts Payable</th>
      <th>Salaries, Wages, and Fees Payable</th>
      <th>Payroll Taxes Payable</th>
      <th>Notes and Loans Payable (Short Term)</th>
      <th>Deferred Income</th>
      <th>Other Current Liabilities</th>
      <th>Total Current Liabilities</th>
      <th>Mortgage Payable</th>
      <th>Notes Payable</th>
      <th>Unsecured Loans</th>
      <th>Other Long Term Liabilities</th>
      <th>Total Long Term Liabilities</th>
      <th>Total Liabilities</th>
      <th>General Fund Balance</th>
      <th>Total Fund Balances</th>
      <th>Total Liabilities and Fund Balances</th>
      <th>DRG Amounts Other Than Outlier Payments</th>
      <th>DRG Amounts Before October 1</th>
      <th>DRG Amounts After October 1</th>
      <th>Outlier Payments For Discharges</th>
      <th>Disproportionate Share Adjustment</th>
      <th>Allowable DSH Percentage</th>
      <th>Managed Care Simulated Payments</th>
      <th>Total IME Payment</th>
      <th>Inpatient Revenue</th>
      <th>Outpatient Revenue</th>
      <th>Total Patient Revenue</th>
      <th>Less Contractual Allowance and Discounts on Patients' Accounts</th>
      <th>Net Patient Revenue</th>
      <th>Less Total Operating Expense</th>
      <th>Net Income from Service to Patients</th>
      <th>Total Other Income</th>
      <th>Total Income</th>
      <th>Total Other Expenses</th>
      <th>Net Income</th>
      <th>Cost To Charge Ratio</th>
      <th>Net Revenue from Medicaid</th>
      <th>Medicaid Charges</th>
      <th>Net Revenue from Stand-Alone CHIP</th>
      <th>Stand-Alone CHIP Charges</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>747534</td>
      <td>110130</td>
      <td>IRWIN COUNTY HOSPITAL</td>
      <td>710 NORTH IRWIN AVENUE</td>
      <td>OCILLA</td>
      <td>GA</td>
      <td>31774</td>
      <td>IRWIN</td>
      <td>99911.0</td>
      <td>R</td>
      <td>STH</td>
      <td>1</td>
      <td>9</td>
      <td>12/01/2022</td>
      <td>01/31/2023</td>
      <td>97.15</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.0</td>
      <td>5.0</td>
      <td>286.0</td>
      <td>34.0</td>
      <td>2108.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>77.0</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>154.0</td>
      <td>34.0</td>
      <td>2108.0</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>77.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>23092.0</td>
      <td>1492240.0</td>
      <td>1.541403e+06</td>
      <td>79660.0</td>
      <td>2.463462e+06</td>
      <td>1.892400e+06</td>
      <td>3.881115e+06</td>
      <td>5.773515e+06</td>
      <td>141304.0</td>
      <td>NaN</td>
      <td>1492240.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>385434.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>11838510.0</td>
      <td>-9502121.0</td>
      <td>236208.0</td>
      <td>108038.0</td>
      <td>14149.0</td>
      <td>3178818.0</td>
      <td>182812.0</td>
      <td>201748.0</td>
      <td>10450346.0</td>
      <td>NaN</td>
      <td>23300.0</td>
      <td>8143685.0</td>
      <td>NaN</td>
      <td>298277.0</td>
      <td>6750223.0</td>
      <td>NaN</td>
      <td>206286.0</td>
      <td>206286.0</td>
      <td>1.013533e+07</td>
      <td>2052873.0</td>
      <td>821279.0</td>
      <td>NaN</td>
      <td>142755.0</td>
      <td>6426148.0</td>
      <td>611623.0</td>
      <td>9997226.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9997226.0</td>
      <td>1.381010e+05</td>
      <td>1.381010e+05</td>
      <td>1.013533e+07</td>
      <td>NaN</td>
      <td>4929.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>61.0</td>
      <td>0.0496</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.892400e+06</td>
      <td>4.398064e+06</td>
      <td>6.290464e+06</td>
      <td>4.732674e+06</td>
      <td>1.557790e+06</td>
      <td>3.033643e+06</td>
      <td>-1475853.0</td>
      <td>227033.0</td>
      <td>-1248820.0</td>
      <td>NaN</td>
      <td>-1248820.0</td>
      <td>0.426683</td>
      <td>30844.0</td>
      <td>140289.0</td>
      <td>13.0</td>
      <td>212.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>748262</td>
      <td>144042</td>
      <td>LAKE BEHAVIORAL HOSPITAL</td>
      <td>2615 WASHINGTON ST</td>
      <td>WAUKEGAN</td>
      <td>IL</td>
      <td>60085</td>
      <td>LAKE</td>
      <td>29404.0</td>
      <td>U</td>
      <td>PH</td>
      <td>4</td>
      <td>5</td>
      <td>10/01/2022</td>
      <td>12/31/2022</td>
      <td>227.95</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>613.0</td>
      <td>391.0</td>
      <td>10311.0</td>
      <td>161.0</td>
      <td>14812.0</td>
      <td>NaN</td>
      <td>47.0</td>
      <td>50.0</td>
      <td>1057.0</td>
      <td>161.0</td>
      <td>NaN</td>
      <td>613.0</td>
      <td>391.0</td>
      <td>10311.0</td>
      <td>161.0</td>
      <td>14812.0</td>
      <td>NaN</td>
      <td>47.0</td>
      <td>50.0</td>
      <td>1057.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3462338.0</td>
      <td>5.123484e+06</td>
      <td>551836.0</td>
      <td>8.111462e+06</td>
      <td>2.237270e+07</td>
      <td>9.606190e+05</td>
      <td>2.333332e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1226478.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5786393.0</td>
      <td>-2093427.0</td>
      <td>73316.0</td>
      <td>82586.0</td>
      <td>NaN</td>
      <td>5075346.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>30000000.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1780042.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>26537904.0</td>
      <td>NaN</td>
      <td>403396.0</td>
      <td>44986420.0</td>
      <td>7.659967e+07</td>
      <td>1964623.0</td>
      <td>779946.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>663708.0</td>
      <td>3408277.0</td>
      <td>NaN</td>
      <td>29278281.0</td>
      <td>NaN</td>
      <td>16472518.0</td>
      <td>45750799.0</td>
      <td>49159076.0</td>
      <td>2.744059e+07</td>
      <td>2.744059e+07</td>
      <td>7.659967e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.417546e+07</td>
      <td>9.606190e+05</td>
      <td>2.513608e+07</td>
      <td>1.535178e+07</td>
      <td>9.784298e+06</td>
      <td>8.585822e+06</td>
      <td>1198476.0</td>
      <td>1434403.0</td>
      <td>2632879.0</td>
      <td>NaN</td>
      <td>2632879.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>748457</td>
      <td>43036</td>
      <td>EVEREST REHABILITATION HOSPITAL BENT</td>
      <td>4313 S PLEASANT CROSSING BLVD</td>
      <td>ROGERS</td>
      <td>AR</td>
      <td>72758-1347</td>
      <td>BENTON</td>
      <td>22220.0</td>
      <td>U</td>
      <td>RH</td>
      <td>5</td>
      <td>6</td>
      <td>01/01/2023</td>
      <td>02/28/2023</td>
      <td>74.54</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>524.0</td>
      <td>10.0</td>
      <td>895.0</td>
      <td>36.0</td>
      <td>2124.0</td>
      <td>NaN</td>
      <td>43.0</td>
      <td>1.0</td>
      <td>63.0</td>
      <td>36.0</td>
      <td>NaN</td>
      <td>524.0</td>
      <td>10.0</td>
      <td>895.0</td>
      <td>36.0</td>
      <td>2124.0</td>
      <td>NaN</td>
      <td>43.0</td>
      <td>1.0</td>
      <td>63.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>905192.0</td>
      <td>1.542746e+06</td>
      <td>270723.0</td>
      <td>2.795440e+06</td>
      <td>2.948357e+06</td>
      <td>3.417200e+04</td>
      <td>2.982529e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1092364.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>521497.0</td>
      <td>-207057.0</td>
      <td>52275.0</td>
      <td>6758.0</td>
      <td>430324.0</td>
      <td>1896161.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19452573.0</td>
      <td>NaN</td>
      <td>74613.0</td>
      <td>1047730.0</td>
      <td>468998.0</td>
      <td>NaN</td>
      <td>16816798.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>532493.0</td>
      <td>1.924545e+07</td>
      <td>369908.0</td>
      <td>97646.0</td>
      <td>22833.0</td>
      <td>837486.0</td>
      <td>NaN</td>
      <td>88192.0</td>
      <td>1416065.0</td>
      <td>NaN</td>
      <td>17507370.0</td>
      <td>NaN</td>
      <td>8940237.0</td>
      <td>26447607.0</td>
      <td>27863672.0</td>
      <td>-8.618220e+06</td>
      <td>-8.618220e+06</td>
      <td>1.924545e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.948358e+06</td>
      <td>3.417300e+04</td>
      <td>2.982531e+06</td>
      <td>1.532078e+06</td>
      <td>1.450453e+06</td>
      <td>2.447938e+06</td>
      <td>-997485.0</td>
      <td>478980.0</td>
      <td>-518505.0</td>
      <td>NaN</td>
      <td>-518505.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>748589</td>
      <td>454155</td>
      <td>OCEANS BEHAVIORAL HOSPITAL CORPUS CH</td>
      <td>600 ELIZABETH ST BUILDING B  4TH FLO</td>
      <td>CORPUS CHRISTI</td>
      <td>TX</td>
      <td>78404</td>
      <td>NUECES</td>
      <td>18580.0</td>
      <td>U</td>
      <td>PH</td>
      <td>4</td>
      <td>4</td>
      <td>11/17/2022</td>
      <td>12/31/2022</td>
      <td>68.01</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>1041.0</td>
      <td>42.0</td>
      <td>1890.0</td>
      <td>NaN</td>
      <td>6.0</td>
      <td>NaN</td>
      <td>137.0</td>
      <td>42.0</td>
      <td>NaN</td>
      <td>64.0</td>
      <td>NaN</td>
      <td>1041.0</td>
      <td>42.0</td>
      <td>1890.0</td>
      <td>NaN</td>
      <td>6.0</td>
      <td>NaN</td>
      <td>137.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1586231.0</td>
      <td>1.858997e+06</td>
      <td>95066.0</td>
      <td>1.965696e+06</td>
      <td>1.703505e+06</td>
      <td>NaN</td>
      <td>1.703505e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1079601.0</td>
      <td>-33678.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>84181.0</td>
      <td>-2622367.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1726846.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1632247.0</td>
      <td>NaN</td>
      <td>7675778.0</td>
      <td>7675778.0</td>
      <td>6.685658e+06</td>
      <td>80298.0</td>
      <td>168672.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>982950.0</td>
      <td>1231920.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7734502.0</td>
      <td>7734502.0</td>
      <td>8966422.0</td>
      <td>-2.280764e+06</td>
      <td>-2.280764e+06</td>
      <td>6.685658e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.703505e+06</td>
      <td>NaN</td>
      <td>1.703505e+06</td>
      <td>4.417440e+05</td>
      <td>1.261761e+06</td>
      <td>3.445228e+06</td>
      <td>-2183467.0</td>
      <td>170.0</td>
      <td>-2183297.0</td>
      <td>NaN</td>
      <td>-2183297.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>748617</td>
      <td>144043</td>
      <td>MONTROSE BEHAVIORAL HEALTH HOSPITAL</td>
      <td>4720 NORTH CLARENDON AVENUE</td>
      <td>CHICAGO</td>
      <td>IL</td>
      <td>60640-5122</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>PH</td>
      <td>4</td>
      <td>3</td>
      <td>10/03/2022</td>
      <td>12/31/2022</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>6098</th>
      <td>807239</td>
      <td>220030</td>
      <td>BAYSTATE WING HOSPITAL &amp; MEDICAL CTR</td>
      <td>40 WRIGHT STREET</td>
      <td>PALMER</td>
      <td>MA</td>
      <td>01069</td>
      <td>NaN</td>
      <td>44140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>10/01/2022</td>
      <td>09/30/2023</td>
      <td>434.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6197.0</td>
      <td>762.0</td>
      <td>13929.0</td>
      <td>40.0</td>
      <td>14600.0</td>
      <td>NaN</td>
      <td>1504.0</td>
      <td>245.0</td>
      <td>3295.0</td>
      <td>68.0</td>
      <td>NaN</td>
      <td>6197.0</td>
      <td>762.0</td>
      <td>13929.0</td>
      <td>40.0</td>
      <td>14600.0</td>
      <td>NaN</td>
      <td>1504.0</td>
      <td>245.0</td>
      <td>3295.0</td>
      <td>357748.0</td>
      <td>4511408.0</td>
      <td>2021314.0</td>
      <td>3508198.0</td>
      <td>36504154.0</td>
      <td>7.197307e+07</td>
      <td>4280963.0</td>
      <td>9.587266e+07</td>
      <td>7.714597e+07</td>
      <td>1.804255e+08</td>
      <td>2.575715e+08</td>
      <td>8290430.0</td>
      <td>NaN</td>
      <td>36504154.0</td>
      <td>10661535.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4974748.0</td>
      <td>8406477.0</td>
      <td>NaN</td>
      <td>18444442.0</td>
      <td>-6004177.0</td>
      <td>1184126.0</td>
      <td>330804.0</td>
      <td>NaN</td>
      <td>29155616.0</td>
      <td>247842.0</td>
      <td>1602049.0</td>
      <td>76481055.0</td>
      <td>NaN</td>
      <td>5578275.0</td>
      <td>32624879.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>49610090.0</td>
      <td>8366196.0</td>
      <td>2378965.0</td>
      <td>10745161.0</td>
      <td>8.951087e+07</td>
      <td>11140259.0</td>
      <td>4284940.0</td>
      <td>NaN</td>
      <td>1005872.0</td>
      <td>102322.0</td>
      <td>2248462.0</td>
      <td>40223471.0</td>
      <td>NaN</td>
      <td>21705037.0</td>
      <td>NaN</td>
      <td>1749321.0</td>
      <td>23454358.0</td>
      <td>63677829.0</td>
      <td>2.583304e+07</td>
      <td>2.583304e+07</td>
      <td>8.951087e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>14001192.0</td>
      <td>NaN</td>
      <td>149463.0</td>
      <td>0.0000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.965193e+07</td>
      <td>1.981820e+08</td>
      <td>2.778340e+08</td>
      <td>1.772606e+08</td>
      <td>1.005734e+08</td>
      <td>1.084772e+08</td>
      <td>-7903843.0</td>
      <td>6556930.0</td>
      <td>-1346913.0</td>
      <td>NaN</td>
      <td>-1346913.0</td>
      <td>0.000000</td>
      <td>19159126.0</td>
      <td>55467523.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6099</th>
      <td>807244</td>
      <td>251331</td>
      <td>BMH - CALHOUN</td>
      <td>140 BURKE CALHOUN CITY ROAD</td>
      <td>CALHOUN</td>
      <td>MS</td>
      <td>38916</td>
      <td>CALHOUN</td>
      <td>99925.0</td>
      <td>R</td>
      <td>CAH</td>
      <td>1</td>
      <td>1</td>
      <td>10/01/2022</td>
      <td>09/30/2023</td>
      <td>145.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3708.0</td>
      <td>31.0</td>
      <td>3974.0</td>
      <td>25.0</td>
      <td>9125.0</td>
      <td>NaN</td>
      <td>137.0</td>
      <td>1.0</td>
      <td>167.0</td>
      <td>145.0</td>
      <td>NaN</td>
      <td>599.0</td>
      <td>31.0</td>
      <td>734.0</td>
      <td>25.0</td>
      <td>9125.0</td>
      <td>NaN</td>
      <td>137.0</td>
      <td>1.0</td>
      <td>167.0</td>
      <td>669418.0</td>
      <td>1220950.0</td>
      <td>1278752.0</td>
      <td>2038049.0</td>
      <td>9919762.0</td>
      <td>1.383443e+07</td>
      <td>805576.0</td>
      <td>2.077617e+07</td>
      <td>1.970193e+07</td>
      <td>2.095826e+07</td>
      <td>4.066019e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>968092.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7661211.0</td>
      <td>-2673060.0</td>
      <td>198794.0</td>
      <td>201608.0</td>
      <td>NaN</td>
      <td>6397192.0</td>
      <td>44800.0</td>
      <td>1165179.0</td>
      <td>6264891.0</td>
      <td>NaN</td>
      <td>2620037.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5736161.0</td>
      <td>NaN</td>
      <td>151031.0</td>
      <td>151031.0</td>
      <td>1.228438e+07</td>
      <td>167808.0</td>
      <td>752466.0</td>
      <td>NaN</td>
      <td>22130.0</td>
      <td>NaN</td>
      <td>1533162.0</td>
      <td>14671536.0</td>
      <td>NaN</td>
      <td>47220.0</td>
      <td>NaN</td>
      <td>241001.0</td>
      <td>288221.0</td>
      <td>14959757.0</td>
      <td>-2.675373e+06</td>
      <td>-2.675373e+06</td>
      <td>1.228438e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.045974e+07</td>
      <td>2.058276e+07</td>
      <td>4.104250e+07</td>
      <td>1.772323e+07</td>
      <td>2.331928e+07</td>
      <td>2.375420e+07</td>
      <td>-434918.0</td>
      <td>1272203.0</td>
      <td>837285.0</td>
      <td>NaN</td>
      <td>837285.0</td>
      <td>1.000000</td>
      <td>992329.0</td>
      <td>3420392.0</td>
      <td>22154.0</td>
      <td>52606.0</td>
    </tr>
    <tr>
      <th>6100</th>
      <td>807290</td>
      <td>450771</td>
      <td>TEXAS HEALTH PRESBYTERIAN HOSPITAL P</td>
      <td>6200 WEST PARKER ROAD</td>
      <td>PLANO</td>
      <td>TX</td>
      <td>75093</td>
      <td>COLLIN</td>
      <td>19124.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>1472.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20082.0</td>
      <td>1631.0</td>
      <td>92701.0</td>
      <td>307.0</td>
      <td>112055.0</td>
      <td>NaN</td>
      <td>3738.0</td>
      <td>356.0</td>
      <td>19681.0</td>
      <td>355.0</td>
      <td>NaN</td>
      <td>17898.0</td>
      <td>679.0</td>
      <td>68192.0</td>
      <td>242.0</td>
      <td>88330.0</td>
      <td>NaN</td>
      <td>3738.0</td>
      <td>356.0</td>
      <td>19681.0</td>
      <td>22995143.0</td>
      <td>63998032.0</td>
      <td>37879433.0</td>
      <td>37879433.0</td>
      <td>156836461.0</td>
      <td>2.949226e+08</td>
      <td>28273229.0</td>
      <td>4.016429e+08</td>
      <td>1.122377e+09</td>
      <td>6.182463e+08</td>
      <td>1.740623e+09</td>
      <td>34458632.0</td>
      <td>NaN</td>
      <td>156836461.0</td>
      <td>1397516.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>278691.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>84660837.0</td>
      <td>NaN</td>
      <td>6911724.0</td>
      <td>1048097.0</td>
      <td>NaN</td>
      <td>101982596.0</td>
      <td>10554981.0</td>
      <td>NaN</td>
      <td>239097165.0</td>
      <td>NaN</td>
      <td>61648188.0</td>
      <td>106058060.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>148641205.0</td>
      <td>NaN</td>
      <td>227990.0</td>
      <td>2447956.0</td>
      <td>2.530718e+08</td>
      <td>13962598.0</td>
      <td>11926119.0</td>
      <td>13166179.0</td>
      <td>NaN</td>
      <td>3441444.0</td>
      <td>NaN</td>
      <td>42496340.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1821364.0</td>
      <td>1821364.0</td>
      <td>44317704.0</td>
      <td>2.087541e+08</td>
      <td>2.087541e+08</td>
      <td>2.530718e+08</td>
      <td>NaN</td>
      <td>32257669.0</td>
      <td>10894686.0</td>
      <td>NaN</td>
      <td>814501.0</td>
      <td>0.0000</td>
      <td>36655038.0</td>
      <td>NaN</td>
      <td>1.122377e+09</td>
      <td>6.182463e+08</td>
      <td>1.740623e+09</td>
      <td>1.193392e+09</td>
      <td>5.472307e+08</td>
      <td>4.517590e+08</td>
      <td>95471661.0</td>
      <td>4402332.0</td>
      <td>99873993.0</td>
      <td>NaN</td>
      <td>99873993.0</td>
      <td>0.000000</td>
      <td>18403527.0</td>
      <td>97104801.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6101</th>
      <td>807296</td>
      <td>470003</td>
      <td>UNIVERSITY OF VERMONT MEDICAL CENTER</td>
      <td>111 COLCHESTER AVENUE</td>
      <td>BURLINGTON</td>
      <td>VT</td>
      <td>05401</td>
      <td>CHITTENDEN</td>
      <td>15540.0</td>
      <td>R</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>10/01/2022</td>
      <td>09/30/2023</td>
      <td>7475.00</td>
      <td>322.0</td>
      <td>NaN</td>
      <td>42735.0</td>
      <td>34593.0</td>
      <td>140185.0</td>
      <td>448.0</td>
      <td>163357.0</td>
      <td>NaN</td>
      <td>6481.0</td>
      <td>4516.0</td>
      <td>20252.0</td>
      <td>468.0</td>
      <td>NaN</td>
      <td>38717.0</td>
      <td>26099.0</td>
      <td>116395.0</td>
      <td>381.0</td>
      <td>139054.0</td>
      <td>NaN</td>
      <td>6481.0</td>
      <td>4516.0</td>
      <td>20252.0</td>
      <td>9061626.0</td>
      <td>18899098.0</td>
      <td>15716911.0</td>
      <td>85531505.0</td>
      <td>800101552.0</td>
      <td>1.044641e+09</td>
      <td>69411741.0</td>
      <td>1.259506e+09</td>
      <td>1.380289e+09</td>
      <td>2.193234e+09</td>
      <td>3.573524e+09</td>
      <td>127970026.0</td>
      <td>NaN</td>
      <td>806713018.0</td>
      <td>100693315.0</td>
      <td>1257744.0</td>
      <td>6957383.0</td>
      <td>135449579.0</td>
      <td>104554955.0</td>
      <td>NaN</td>
      <td>207634474.0</td>
      <td>NaN</td>
      <td>54190441.0</td>
      <td>NaN</td>
      <td>126328679.0</td>
      <td>640073938.0</td>
      <td>29857748.0</td>
      <td>7390982.0</td>
      <td>800624103.0</td>
      <td>82478056.0</td>
      <td>NaN</td>
      <td>535039420.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>587568615.0</td>
      <td>457666940.0</td>
      <td>45453916.0</td>
      <td>537889048.0</td>
      <td>1.765532e+09</td>
      <td>30343553.0</td>
      <td>95894487.0</td>
      <td>NaN</td>
      <td>20560073.0</td>
      <td>NaN</td>
      <td>98570727.0</td>
      <td>245368840.0</td>
      <td>NaN</td>
      <td>386879788.0</td>
      <td>NaN</td>
      <td>46100666.0</td>
      <td>432980454.0</td>
      <td>678349294.0</td>
      <td>1.005496e+09</td>
      <td>1.087182e+09</td>
      <td>1.765532e+09</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>68591422.0</td>
      <td>NaN</td>
      <td>2628766.0</td>
      <td>0.0000</td>
      <td>34316985.0</td>
      <td>17131599.0</td>
      <td>1.380305e+09</td>
      <td>3.034928e+09</td>
      <td>4.415233e+09</td>
      <td>2.565553e+09</td>
      <td>1.849680e+09</td>
      <td>2.058745e+09</td>
      <td>-209065452.0</td>
      <td>328946452.0</td>
      <td>119881000.0</td>
      <td>NaN</td>
      <td>119881000.0</td>
      <td>0.000000</td>
      <td>98671557.0</td>
      <td>548187058.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6102</th>
      <td>807303</td>
      <td>670090</td>
      <td>CRESCENT MEDICAL CENTER LANCASTER</td>
      <td>2600 W. PLEASANT RUN RD.</td>
      <td>LANCASTER</td>
      <td>TX</td>
      <td>75146</td>
      <td>DALLAS</td>
      <td>19124.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>5</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>238.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>616.0</td>
      <td>10.0</td>
      <td>4303.0</td>
      <td>84.0</td>
      <td>30660.0</td>
      <td>NaN</td>
      <td>147.0</td>
      <td>1.0</td>
      <td>1071.0</td>
      <td>84.0</td>
      <td>NaN</td>
      <td>481.0</td>
      <td>10.0</td>
      <td>4006.0</td>
      <td>76.0</td>
      <td>27740.0</td>
      <td>NaN</td>
      <td>147.0</td>
      <td>1.0</td>
      <td>1071.0</td>
      <td>NaN</td>
      <td>6049924.0</td>
      <td>869477.0</td>
      <td>881235.0</td>
      <td>15487442.0</td>
      <td>2.673478e+07</td>
      <td>664056.0</td>
      <td>3.752390e+07</td>
      <td>9.018291e+07</td>
      <td>1.709129e+08</td>
      <td>2.610958e+08</td>
      <td>2850844.0</td>
      <td>NaN</td>
      <td>15487442.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>267626.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>30585961.0</td>
      <td>NaN</td>
      <td>1596307.0</td>
      <td>764375.0</td>
      <td>NaN</td>
      <td>28004140.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>739843.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9705346.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4399752.0</td>
      <td>211878.0</td>
      <td>1246765.0</td>
      <td>1606318.0</td>
      <td>3.401021e+07</td>
      <td>8253674.0</td>
      <td>420610.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>8674284.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7802928.0</td>
      <td>7802928.0</td>
      <td>16477212.0</td>
      <td>1.753300e+07</td>
      <td>1.753300e+07</td>
      <td>3.401021e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1553946.0</td>
      <td>NaN</td>
      <td>13014.0</td>
      <td>0.0000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9.007912e+07</td>
      <td>1.710169e+08</td>
      <td>2.610960e+08</td>
      <td>2.208347e+08</td>
      <td>4.026132e+07</td>
      <td>4.222222e+07</td>
      <td>-1960898.0</td>
      <td>6179409.0</td>
      <td>4218511.0</td>
      <td>NaN</td>
      <td>4218511.0</td>
      <td>0.000000</td>
      <td>19106.0</td>
      <td>214755.0</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>6103 rows × 117 columns</p>
</div>



```python
# QUICK DATA CHECK: URBAN HOSPITAL CITIES

display(cms_ccr[cms_ccr['Rural Versus Urban'] == 'U']['City'].unique().tolist())
```


    ['WAUKEGAN',
     'ROGERS',
     'CORPUS CHRISTI',
     'GEORGETOWN',
     'POMONA',
     'LONGVIEW',
     'SPRINGFIELD',
     'GILBERT',
     'SAN ANTONIO',
     'TEMPLE',
     'EAU CLAIRE',
     'LIBERTY TOWNSHIP',
     'AUGUSTA',
     'KNOXVILLE',
     'CASPER',
     'ZEELAND',
     'LOCKPORT',
     'LANSING',
     'CARSON CITY',
     'LANCASTER',
     'SALT LAKE CITY',
     'WENATCHEE',
     'SENATOBIA',
     'SACRAMENTO',
     'PEORIA',
     'LOS ANGELES',
     'TUSCALOOSA',
     'ATLANTA',
     'GREEN BAY',
     'EUTAW',
     'THOMSON',
     'OKLAHOMA CITY',
     'ALTON',
     'TULSA',
     'SUGAR LAND',
     'KATY',
     'SIOUX FALLS',
     'TALLASSEE',
     'HONOLULU',
     'WINCHESTER',
     'MOBILE',
     'FRONT ROYAL',
     'GOODYEAR',
     'NAMPA',
     'WHITTIER',
     'DOWNEY',
     'NEWNAN',
     'BRUNSWICK',
     'CONCORD',
     'PEARISBURG',
     'SARASOTA',
     'ZION',
     'BATON ROUGE',
     'FALMOUTH',
     'ASHLAND',
     'CLERMONT',
     'DALTON',
     'CUMMING',
     'CANTON',
     'GAINESVILLE',
     'WINDER',
     'LAWRENCEVILLE',
     'VALDOSTA',
     'COLLINS',
     'FORT WORTH',
     'BIRMINGHAM',
     'OPELIKA',
     'GADSDEN',
     'GREENSBORO',
     'ENCINITAS',
     'MANSFIELD CENTER',
     'MELBOURNE',
     'COCOA BEACH',
     'NORTH MIAMI',
     'MEMPHIS',
     'JEFFERSON CITY',
     'LAFAYETTE',
     'BESSEMER',
     'TALLAHASSEE',
     'JUPITER',
     'ST. CLOUD',
     'VIERA',
     'NORTH VENICE',
     'DAHLONEGA',
     'DULUTH',
     'MONTICELLO',
     'LAS CRUCES',
     'WAGONER',
     'TAHOKA',
     'TORRINGTON',
     'AMERICAN FALLS',
     'CHICAGO',
     'NEW LENOX',
     'CAMBRIDGE',
     'HYANNIS',
     'MARLBOROUGH',
     'BROCKTON',
     'MILTON',
     'BURLINGTON',
     'ATHOL',
     'WABASHA',
     'RHINEBECK',
     'CARMEL',
     'WAKEFIELD',
     'CENTREVILLE',
     'KING CITY',
     'DECATUR',
     'LEOMINSTER',
     'BOSTON',
     'RAEFORD',
     'EASLEY',
     'COLUMBIA',
     'TRAVELERS REST',
     'RICHMOND',
     'WAUKESHA',
     'OCONOMOWOC',
     'STAFFORD SPRINGS',
     'WATERBURY',
     'BRISTOL',
     'WASHINGTON',
     'PALM BAY',
     'BIDDEFORD',
     'NEWBURYPORT',
     'BEVERLY',
     'PLYMOUTH',
     'MEDFORD',
     'NEEDHAM',
     'STATESVILLE',
     'CARY',
     'GRANTS PASS',
     'GREER',
     'SIMPSONVILLE',
     'SUMTER',
     'GREENVILLE',
     'DUARTE',
     'VALENCIA',
     'SAN DIEGO',
     'PUTNAM',
     'MADERA',
     'DAPHNE',
     'HAYWARD',
     'EDGEWOOD',
     'HENDERSON',
     'PORTLAND',
     'BAY ST. LOUIS',
     'OKMULGEE',
     'ARLINGTON',
     'CROWLEY',
     'FORT MYERS',
     'OCOEE',
     'LAUDERDALE LAKES',
     'DANVILLE',
     'HATTIESBURG',
     'JONESBORO',
     'OXFORD',
     'SAN JUAN',
     'BELLAIRE',
     'HOUSTON',
     'ENGLEWOOD',
     'BOCA RATON',
     'BANGOR',
     'FLORESVILLE',
     'CLEBURNE',
     'KILLEEN',
     'ELECTRA',
     'PHOENIX',
     'MANSFIELD',
     'WESTFIELD',
     'GARDNER',
     'DETROIT',
     'WARRENTON',
     'SAHUARITA',
     'NEW IBERIA',
     'MILFORD',
     'PONCE',
     'SUGARLAND',
     'WEST MEMPHIS',
     'BELLE GLADE',
     'EL PASO',
     'TITUSVILLE',
     'BOISE',
     'CALDWELL',
     'WICHITA',
     'MARION',
     'FORT WAYNE',
     'SOUTHBRIDGE',
     'HOLYOKE',
     'WORCESTER',
     'PONTIAC',
     'HARTSVILLE',
     'BOUNTIFUL',
     'FOLEY',
     'LITTLE ROCK',
     'DADE CITY',
     'BLOOMINGTON',
     'BLUFFTON',
     'FLOWOOD',
     'TOPEKA',
     'OVERLAND PARK',
     'BILOXI',
     'PLACERVILLE',
     'COVINA',
     'MACON',
     'BOLINGBROOK',
     'GREAT BARRINGTON',
     'GLENDALE HEIGHTS',
     'LUBBOCK',
     'SPRINGDALE',
     'ST. CHARLES',
     'ROCHELLE PARK',
     'LAWTON',
     'AUSTIN',
     'FOND DU LAC',
     'WEST ALLIS',
     'PLANO',
     'SEATTLE',
     'ST. FRANCISVILLE',
     'GLEN ROSE',
     'CHARLESTON',
     'HOLLY SPRINGS',
     'BRANFORD',
     'SAVANNAH',
     'CLAREMORE',
     'LAS VEGAS',
     'MARLIN',
     'SALEM',
     'BRADENTON',
     'JACKSON',
     'JEFFERSON',
     'LIBERTY',
     'LA JOLLA',
     'GRAND JUNCTION',
     'CHAMPAIGN',
     'ASHEVILLE',
     'AKRON',
     'LORIS',
     'OROVILLE',
     'LAKE WORTH',
     'DAYTONA BEACH',
     'HENRYETTA',
     'SAN GERMAN',
     'TAYLOR',
     'VIRGINIA BEACH',
     'SOUTHFIELD',
     'GRAND RAPIDS',
     'DENTON',
     'ORLANDO',
     'WAYNESBORO',
     'BAY CITY',
     'OMAHA',
     'EDINBURG',
     'BROOKSVILLE',
     'RAPID CITY',
     'COLLEGE PARK',
     'LONDON',
     'ARECIBO',
     'MAYAGUEZ',
     'WETUMPKA',
     'KENNER',
     'OLIVE BRANCH',
     'MARLTON',
     'SOUTH ATTLEBORO',
     'WALLINGFORD',
     'SHREVEPORT',
     'JAMAICA PLAINS',
     'WESTWOOD',
     'VOORHEES',
     'BERKELEY HEIGHTS',
     'EUGENE',
     'CAGUAS',
     'CIDRA',
     'CYPRESS',
     'LAYTON',
     'MAGEE',
     'BAKERSFIELD',
     'TORRANCE',
     'FORT COLLINS',
     'WEST PALM BEACH',
     'CAMDEN',
     'MT. HOLLY',
     'WILLINGBORO',
     'TOMS RIVER',
     'HATO REY',
     'HUMBLE',
     'SHERMAN',
     'WESLACO',
     'QUEEN CREEK',
     'ST. PAUL',
     'MINNEAPOLIS',
     'ENID',
     'EDMOND',
     'BAYAMON',
     'WESTON',
     'RIVER FALLS',
     'APACHE JUNCTION',
     'REDWOOD CITY',
     'LONGMONT',
     'THORTON',
     'JOHNSTOWN',
     'ST. AUGUSTINE',
     'SPARKS',
     'RENO',
     'RIDGEWOOD',
     'HAMILTON',
     'AGUADILLA',
     'AIKEN',
     'WEST COLUMBIA',
     'VIBORG',
     'KINGSPORT',
     'BELTON',
     'JANESVILLE',
     'RICHARDSON',
     'WOODLAND',
     'WESTHAMPTON',
     'CAYCE',
     'TOPPENISH',
     'MADISON',
     'VICTORIA',
     'LOVELAND',
     'TAVARES',
     'STAUNTON',
     'COVINGTON',
     'HARAHANELO',
     'LAKEWOOD',
     'MARYSVILLE',
     'LIMA',
     'LULING',
     'WICHITA FALLS',
     'KINGWOOD',
     'DALLAS',
     'ROUND ROCK',
     'IRVINE',
     'SANN JOSE',
     'LUTZ',
     'KANKAKEE',
     'WINSTON SALEM',
     'WARWICK',
     'SPARTANBURG',
     'ELGIN',
     'BEDFORD',
     'BELOIT',
     'LAVEEN',
     'MESA',
     'WILLCOX',
     'FLAGSTAFF',
     'NORTH LITTLE ROCK',
     'CONWAY',
     'SOUTH SAN FRANCISCO',
     'WALNUT CREEK',
     'SAN RAFAEL',
     'FRESNO',
     'VERO BEACH',
     'NAPLES',
     'CLARKSVILLE',
     'HAMMOND',
     'ST. LOUIS',
     'CHESTERFIELD',
     'BROWNS MILLS',
     'LONG BRANCH',
     'HACKETTSTOWN',
     'LANGHORNE',
     'PHILADELPHIA',
     'FLORENCE',
     'CARROLLTON',
     'GREENILLE',
     'LAREDO',
     'TEMECULA',
     'TARZANA',
     'LANAI',
     'KULA',
     'BETTENDORF',
     'NASHUA',
     'RAHWAY',
     'KENMORE',
     'LEWISTON',
     'ANDERSON',
     'EVERETT',
     'WEATHERFORD',
     'CAPE CORAL',
     'EDWARDSVILLE',
     'COLUMBIA CITY',
     'INDIANAPOLIS',
     'BLACKWOOD',
     'WYCKOFF',
     'BUFFALO',
     'MEDINA',
     'MIDWEST CITY',
     'SOUTH OGDEN',
     'SOUTHLAKE',
     'SCOTTSDALE',
     'CHANDLER',
     'FREMONT',
     'MANTECA',
     'JACKSONVILLE',
     'JEFFERSONVILLE',
     'DUBUQUE',
     'ALEXANDRIA',
     'NEW PRAGUE',
     'HAZLEHURST',
     'PASSAIC',
     'FARGO',
     'MISSION',
     'ABILENE',
     'OREM',
     'LYNCHBURG',
     'FREDERICKSBURG',
     'LEESBURG',
     'FAIRFAX',
     'STAFFORD',
     'KENNEWICK',
     'ALLEN',
     'GLENDALE',
     'SAN FRANCISCO',
     'GLENDORA',
     'RANCHO MIRAGE',
     'LOUISVILLE',
     'LITTLETON',
     'DELRAY BEACH',
     'COUNCIL BLUFFS',
     'SLIDELL',
     'BROUSSARD',
     'MAPLEWOOD',
     'SAINT PAUL',
     'KINGSTON',
     'BRONX',
     'UNIONTOWN',
     'NASHVILLE',
     'GERMANTOWN',
     'NASSAU BAY',
     'AMARILLO',
     'HUNTINGTON',
     'FRANKLIN',
     'MCKINNEY',
     'WILDOMAR',
     'PASADENA',
     'WESTMINSTER',
     'TAMPA',
     'CEDAR RAPIDS',
     'SHAWNEE MISSION',
     'HIBBING',
     'WYOMING',
     'STILLWATER',
     'EDINA',
     'MENDENHALL',
     'JERSEY CITY',
     'ONEIDA',
     'BATAVIA',
     'OREGON',
     'AVON',
     'OBERLIN',
     'CINCINNATI',
     'NORTH SMITHFIELD',
     'IRVING',
     'BEAUMONT',
     'MARTINSBURG',
     'BERKELEY SPRINGS',
     'ROMNEY',
     'MONROE',
     'PRAIRIE DU SAC',
     'THE WOODLANDS',
     'FORT SMITH',
     'NEWARK',
     'PALM COAST',
     'PANAMA CITY',
     'DOWNERS GROVE',
     'SHELBYVILLE',
     'GREENWOOD',
     'ST. LOUIS PARK',
     'WACONIA',
     'CREVE COEUR',
     'SECAUCUS',
     'NEW YORK',
     'UTICA',
     'CLIFTON SPRINGS',
     'WACO',
     'NEW LONDON',
     'WAUSAU',
     'CORONA',
     'GARDENA',
     'REDDING',
     'GREELEY',
     'BYRON',
     'PEKIN',
     'MANHATTAN',
     'LINCOLN',
     'NEW BEDFORD',
     'NORTHFIELD',
     'CAPE MAY COURT HOUSE',
     'SOMERVILLE',
     'PARAMUS',
     'BELLE MEAD',
     'PORT JEFFERSON',
     'GLENS FALLS',
     'RIO PIEDRAS',
     'PUYALLUP',
     'TACOMA',
     'OLYMPIA',
     'MESQUITE',
     'NEW BRAUNFELS',
     'SURPRISE',
     'ST. HELENA',
     'SAN BERNARDINO',
     'SANTA ROSA',
     'COLORADO SPRINGS',
     'LAKELAND',
     'LIBERTYVILLE',
     'OAK LAWN',
     'CHALMETTE',
     'LUTCHER',
     'LAPLACE',
     'CHESTNUT HILL',
     'SAGINAW',
     'MOUNT CLEMENS',
     'ST PAUL',
     'POMPTON PLAINS',
     'PATERSON',
     'ELIZABETH',
     'NEW BRUNSWICK',
     'GENEVA',
     'NIAGARA FALLS',
     'RIVERDALE',
     'FAIRFIELD',
     'WARREN',
     'LORAIN',
     'TROY',
     'YOUNGSTOWN',
     'OREGON CITY',
     'MILWAUKIE',
     'DORADO',
     'WOONSOCKET',
     'BROWNSVILLE',
     'SPOKANE',
     'MIDDLETON',
     'HUNTINGTON PARK',
     'NORTHRIDGE',
     'NORWALK',
     'TUSTIN',
     'MODESTO',
     'VALLEJO',
     'VENTURA',
     'WESLEY CHAPEL',
     'LAND O LAKES',
     'ELMHURST',
     'GARY',
     'FRANKLINTON',
     'VINELAND',
     'PORT JERVIS',
     'SCHENECTADY',
     'BERMUDA RUN',
     'OWASSO',
     'YAUCO',
     'FRISCO',
     'TROPHY CLUB',
     'KENOSHA',
     'ALABASTER',
     'JASPER',
     'TALLADEGA',
     'PHENIX CITY',
     'HUBTSVILLE',
     'TUCSON',
     'YUMA',
     'PALMDALE',
     'AURORA',
     'CHATSWORTH',
     'ROME',
     'ATHENS',
     'SMYRNA',
     'FT. THOMAS',
     'NORWOOD',
     'GULFPORT',
     'BELLEVILLE',
     'MULLICA HILL',
     'LIVINGSTON',
     'WEST ORANGE',
     'EAST MEADOW',
     'NYACK',
     'SUFFERN',
     'OCEANSIDE',
     'PLAINVIEW',
     'NORTHWOOD',
     'PARMA',
     'BEACHWOOD',
     'COLUMBUS',
     'TOLEDO',
     'CABO ROJO',
     'BAYTOWN',
     'GRAFTON',
     'ANCHORAGE',
     'ESCONDIDO',
     'CASTLE ROCK',
     'BARRINGTON',
     'STATEN ISLAND',
     'MOUNT KISCO',
     'SYRACUSE',
     'PICKENS',
     'TYLER',
     'SUFFOLK',
     'NEWPORT NEWS',
     'WILLIAMSBURG',
     'PETERSBURG',
     'FLOWER MOUND',
     'SAN PEDRO',
     'NEWPORT BEACH',
     'SAN LUIS OBISPO',
     'SIMI VALLEY',
     'SOUTH LAKE TAHOE',
     'SANTA BARBARA',
     'HARBOR CITY',
     'FOUNTAIN VALLEY',
     'VERNON',
     'MANCHESTER',
     'IDAHO FALLS',
     'NAPERVILLE',
     'PRINCETON',
     'BURNSVILLE',
     'BILLINGS',
     'DENVILLE',
     'YONKERS',
     'BROOKLYN',
     'MOUNT VERNON',
     'MARTINS FERRY',
     'MIDDLEBURG HEIGHTS',
     'PORT CLINTON',
     'WOODBRIDGE',
     'GLOUCESTER',
     'YORKTOWN',
     'MORGANTOWN',
     'FAYETTEVILLE',
     'PANORAMA CITY',
     'INGLEWOOD',
     'SHERMAN OAKS',
     'MONTCLAIR',
     'ANTIOCH',
     'MORENO VALLEY',
     'VACAVILLE',
     'TULARE',
     'WASHINGTON DC',
     'EVANSTON',
     'MORRIS',
     'MARYVILLE',
     'LAWRENCEBURG',
     'YORK',
     'DORCHESTER',
     'TAUNTON',
     'CEDAR GROVE',
     'SANTA FE',
     'ELMIRA',
     'NEW HYDE PARK',
     'HIGH POINT',
     'WADESBORO',
     'CHARLOTTE',
     'LELAND',
     'ROCK CREEK',
     'OKALHOMA CITY',
     'NORRISTOWN',
     'BENSALEM',
     'PROVIDENCE',
     'NORTH PROVIDENCE',
     'HARLINGEN',
     'MIDLAND',
     'MURRAY',
     'AUBURN',
     'BALDWIN PARK',
     'SANTA ANA',
     'PARKER',
     'PALM BEACH GARDENS',
     'DUNEDIN',
     'EVANSVILLE',
     'CORALVILLE',
     'NEW ORLEANS',
     'LACOMBE',
     'FORT WASHINGTON',
     'NORTH BERGEN',
     'NEWTON',
     'SUMMIT',
     'GLEN COVE',
     'OSWEGO',
     'ROCHESTER',
     'DURHAM',
     'LEXINGTON',
     'ALBEMARLE',
     'WINSTON-SALEM',
     'BURGAW',
     'RALEIGH',
     'VEGA BAJA',
     'MANATI',
     'BRYAN',
     'WINNIE',
     'FALLS CHURCH',
     'WEBSTER',
     'KELLER',
     'UPLAND',
     'HANFORD',
     'HOLLYWOOD',
     'SAN DIMAS',
     'SAN JOSE',
     'ANAHEIM',
     'TARPON SPRINGS',
     'MIAMI',
     'PORT ST. LUCIE',
     'DEQUINCY',
     'BASTROP',
     'GONZALES',
     'ROCKVILLE',
     'MORRISTOWN',
     'HOPEWELL',
     'LISBON',
     'SLEEPY HOLLOW',
     'TALIHINA',
     'NEWBERG',
     'BURLESON',
     'ISSAQUAH',
     'HOT SPRINGS',
     'TURLOCK',
     'SANTA CRUZ',
     'YUBA CITY',
     'ROSEVILLE',
     'LONG BEACH',
     'SAN LEANDRO',
     'TEHACHAPI',
     'ZEPHYRHILLS',
     'URBANA',
     'NOBLESVILLE',
     'MUNSTER',
     'CLIVE',
     'HOUMA',
     'SILVER SPRING',
     'MT. CLEMENS',
     'LAKE ST. LOUIS',
     'FLEMINGTON',
     'PERTH AMBOY',
     'READING',
     'BURLINGAME',
     'OAKLAND',
     'VICTOR VALLEY',
     'DAVIS',
     'CERRITOS',
     'LA MESA',
     'DENVER',
     'HIALEAH',
     'OAK PARK',
     'PAOLA',
     'BOWLING GREEN',
     'GREAT FALLS',
     'SOMERS POINT',
     'RIO RANCHO',
     'CLACKAMAS',
     'HILLSBORO',
     'ALTOONA',
     'SUNNYVALE',
     'FAIRBANKS',
     'VAN NUYS',
     'NOVATO',
     'BERKELEY',
     'TRACY',
     'CASTRO VALLEY',
     'DELANO',
     'SUN CITY',
     'HINSDALE',
     'LAPORTE',
     'MOORESVILLE',
     'LEBANON',
     'NEWBURGH',
     'OLATHE',
     'BOULDER CITY',
     'BAYONNE',
     'XENIA',
     'RAVENNA',
     'ELYRIA',
     'DAYTON',
     'DUBLIN',
     'WEST CHESTER',
     'BERWICK',
     'SANTURCE',
     'MOCA',
     'CHARLETON',
     'ROCKWALL',
     'GOSHEN',
     'GREENCASTLE',
     'BOSSIER CITY',
     'LAWRENCE',
     'KANSAS CITY',
     'TEANECK',
     'HOBOKEN',
     'STAYTON',
     'WHEELING',
     'SUN VALLEY',
     'HEMET',
     'EUREKA',
     'NEW ALBANY',
     'MISHAWAKA',
     'EAST CHICAGO',
     'LEAVENWORTH',
     'EL DORADO',
     'LEAWOOD',
     'DERBY',
     'PORT HURON',
     'OWOSSO',
     'GARDEN CITY',
     'FLINT',
     'LEES SUMMIT',
     'MISSOULA',
     'TRENTON',
     'BEND',
     'KIRKLAND',
     'LEHIGH ACRES',
     'ARLINGTON HEIGHTS',
     'BLUE SPRINGS',
     'ALBUQUERQUE',
     'WHITE PLAINS',
     'TOOELE',
     'COSTA MESA',
     'ELKHART',
     'SOUTH BEND',
     'ELWOOD',
     'YPSILANTI',
     'ST. PETERS',
     'CAPE GIRARDEAU',
     'JENKS',
     'ROSEMEAD',
     'DYER',
     'TEXARKANA',
     'WAHIAWA',
     'BROWNSBURG',
     'SULPHUR',
     'AYER',
     'FREEHOLD',
     'ROSLYN',
     'MCMINNVILLE',
     'DREXEL HILL',
     'ODESSA',
     'PEARLAND',
     'TUBA CITY',
     'BARSTOW',
     'DAVENPORT',
     'BETHPAGE',
     'CAMP HILL',
     'ASHEBORO',
     'SELLS',
     'IOWA CITY',
     'PORT JEFFERESON',
     'ROCKVILLE CENTRE',
     'WEST ISLIP',
     'LOUSIVILLE',
     'HENDERSONVILLE',
     'CHINO',
     'HAVRE DE GRACE',
     'ADDISON',
     'BRANDON',
     'HOPKINSVILLE',
     'ADA',
     'RIVERSIDE',
     'DANBURY',
     'LODI',
     'MCDONOUGH',
     'CLEVELAND',
     'MOUNTAINSIDE',
     'WEST JORDAN',
     'STOCKTON',
     'SPRINGVILLE',
     'LITTLE FALLS',
     'MT. PLEASANT',
     'SUMMERVILLE',
     'JOHNSTON',
     'WEST LAFAYETTE',
     'ERWIN',
     'WILSON',
     'GLEN DALE',
     'HUDSON',
     'GARLAND',
     'LUMBERTON',
     'FT WAYNE',
     'WARM SPRINGS',
     'WOODLAND HILLS',
     'MENOMONEE FALLS',
     'METAIRIE',
     'CONROE',
     'TUSCON',
     'VERSAILLES',
     'FAJARDO',
     'AMHERST',
     'MIDVALE',
     'MURRIETA',
     'ATTLEBORO',
     'WALTHAM',
     'BELLVILE',
     'CHIPPEWA FALLS',
     'MILWAUKEE',
     'GRANITE CITY',
     'JOHNSON CITY',
     'SANTA TERESA',
     'BARRIO RINCON',
     'AIBONITO',
     'WEST MONROE',
     'AUBREY',
     'HORIZON CITY',
     'LAKE CHARLES',
     'DE SOTO',
     'MIAMI LAKES',
     'SEBASTOPOL',
     'WILMINGTON',
     'SARATOGA SPRINGS',
     'SALLISAW',
     'HUMACAO',
     'GUAYAMA',
     'HILTON HEAD ISLAND',
     'EDMONDS',
     'BAY MINETTE',
     'FAIRHOPE',
     'TEMPE',
     'CARBONDALE',
     'GREENFIELD',
     'KATONAH',
     'WARNER ROBINS',
     'CHATTANOOGA',
     'MARICOPA',
     'DOVER',
     'GRESHAM',
     'SILVERTON',
     'TUALATIN',
     'LATROBE',
     'SMITHTOWN',
     'NORTH LOGAN',
     'BELLEVUE',
     'MIAMISBURG',
     'TERRE HAUTE',
     'PLAINFIELD',
     'LENEXA',
     'ONAGA',
     'TUPELO',
     'SACHSE',
     'WATSONVILLE',
     'EWA BEACH',
     'HOLTON',
     'MARSHALL',
     'WEST HAVERSTRAW',
     'GAHANNA',
     'INDEPENDENCE',
     'HARKER HEIGHTS',
     'HUNTSVILLE',
     'GREENBRAE',
     'CRESTVIEW',
     'SHILOH',
     'ST LOUIS',
     'BRIDGETON',
     'ROCK HILL',
     'ALDIE',
     'LAKEWAY',
     'THOMASVILLE',
     'OJAI',
     'MANDEVILLE',
     'SEAFORD',
     'RADCLIFF',
     'ROSLINDALE',
     'WYANDOTTE',
     'GALLATIN',
     'SOUTH CHARLESTON',
     'PENSACOLA',
     'EASTON',
     'GASTONIA',
     'MONROVIA',
     'VISALIA',
     'MANGONIA PARK',
     'BOYNTON BEACH',
     'TAMARAC',
     'CLEARWATER',
     'ALPENA',
     'VANCOUVER',
     'PELHAM',
     'BRAINTREE',
     'EAST STROUDSBURG',
     'PITTSBURGH',
     'MECHANICSBURG',
     'PLEASANT GAP',
     'SEWICKLEY',
     'ERIE',
     'NEW CANAAN',
     'DICKSON',
     'NORFOLK',
     'COLLEGE STATION',
     'DES PLAINES',
     'MARRERO',
     'WESTERVILLE',
     'MYRTLE BEACH',
     'RENTON',
     'CORPUS CHRIST',
     'MIRAMAR',
     'BATTLE CREEK',
     'BARTLETT',
     'NICEVILLE',
     'SANFORD',
     'STUART',
     'PRINCE FREDERICK',
     'ST. JOSEPH',
     'ROWLETT',
     'BECKLEY',
     'SAN ANGELO',
     'PALM SPRINGS',
     'SAN RAMON',
     'POST FALLS',
     ...]



```python
# FILTER: OHIO (URBAN HOSPITALS ONLY)

cms_ccr_oh_u = cms_ccr[(cms_ccr['State Code'] == 'OH') & (cms_ccr['Rural Versus Urban'] == 'U')].copy()

display(cms_ccr_oh_u)
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rpt_rec_num</th>
      <th>Provider CCN</th>
      <th>Hospital Name</th>
      <th>Street Address</th>
      <th>City</th>
      <th>State Code</th>
      <th>Zip Code</th>
      <th>County</th>
      <th>Medicare CBSA Number</th>
      <th>Rural Versus Urban</th>
      <th>CCN Facility Type</th>
      <th>Provider Type</th>
      <th>Type of Control</th>
      <th>Fiscal Year Begin Date</th>
      <th>Fiscal Year End Date</th>
      <th>FTE - Employees on Payroll</th>
      <th>Number of Interns and Residents (FTE)</th>
      <th>Total Days Title V</th>
      <th>Total Days Title XVIII</th>
      <th>Total Days Title XIX</th>
      <th>Total Days (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds</th>
      <th>Total Bed Days Available</th>
      <th>Total Discharges Title V</th>
      <th>Total Discharges Title XVIII</th>
      <th>Total Discharges Title XIX</th>
      <th>Total Discharges (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds + Total for all Subproviders</th>
      <th>Hospital Total Days Title V For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Days (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Hospital Number of Beds For Adults &amp; Peds</th>
      <th>Hospital Total Bed Days Available For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title V For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Discharges (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Cost of Charity Care</th>
      <th>Total Bad Debt Expense</th>
      <th>Cost of Uncompensated Care</th>
      <th>Total Unreimbursed and Uncompensated Care</th>
      <th>Total Salaries From Worksheet A</th>
      <th>Overhead Non-Salary Costs</th>
      <th>Depreciation Cost</th>
      <th>Total Costs</th>
      <th>Inpatient Total Charges</th>
      <th>Outpatient Total Charges</th>
      <th>Combined Outpatient + Inpatient Total Charges</th>
      <th>Wage-Related Costs (Core)</th>
      <th>Wage-Related Costs (RHC/FQHC)</th>
      <th>Total Salaries (adjusted)</th>
      <th>Contract Labor: Direct Patient Care</th>
      <th>Wage Related Costs for Part - A Teaching Physicians</th>
      <th>Wage Related Costs for Interns and Residents</th>
      <th>Cash on Hand and in Banks</th>
      <th>Temporary Investments</th>
      <th>Notes Receivable</th>
      <th>Accounts Receivable</th>
      <th>Less: Allowances for Uncollectible Notes and Accounts Receivable</th>
      <th>Inventory</th>
      <th>Prepaid Expenses</th>
      <th>Other Current Assets</th>
      <th>Total Current Assets</th>
      <th>Land</th>
      <th>Land Improvements</th>
      <th>Buildings</th>
      <th>Leasehold Improvements</th>
      <th>Fixed Equipment</th>
      <th>Major Movable Equipment</th>
      <th>Minor Equipment Depreciable</th>
      <th>Health Information Technology Designated Assets</th>
      <th>Total Fixed Assets</th>
      <th>Investments</th>
      <th>Other Assets</th>
      <th>Total Other Assets</th>
      <th>Total Assets</th>
      <th>Accounts Payable</th>
      <th>Salaries, Wages, and Fees Payable</th>
      <th>Payroll Taxes Payable</th>
      <th>Notes and Loans Payable (Short Term)</th>
      <th>Deferred Income</th>
      <th>Other Current Liabilities</th>
      <th>Total Current Liabilities</th>
      <th>Mortgage Payable</th>
      <th>Notes Payable</th>
      <th>Unsecured Loans</th>
      <th>Other Long Term Liabilities</th>
      <th>Total Long Term Liabilities</th>
      <th>Total Liabilities</th>
      <th>General Fund Balance</th>
      <th>Total Fund Balances</th>
      <th>Total Liabilities and Fund Balances</th>
      <th>DRG Amounts Other Than Outlier Payments</th>
      <th>DRG Amounts Before October 1</th>
      <th>DRG Amounts After October 1</th>
      <th>Outlier Payments For Discharges</th>
      <th>Disproportionate Share Adjustment</th>
      <th>Allowable DSH Percentage</th>
      <th>Managed Care Simulated Payments</th>
      <th>Total IME Payment</th>
      <th>Inpatient Revenue</th>
      <th>Outpatient Revenue</th>
      <th>Total Patient Revenue</th>
      <th>Less Contractual Allowance and Discounts on Patients' Accounts</th>
      <th>Net Patient Revenue</th>
      <th>Less Total Operating Expense</th>
      <th>Net Income from Service to Patients</th>
      <th>Total Other Income</th>
      <th>Total Income</th>
      <th>Total Other Expenses</th>
      <th>Net Income</th>
      <th>Cost To Charge Ratio</th>
      <th>Net Revenue from Medicaid</th>
      <th>Medicaid Charges</th>
      <th>Net Revenue from Stand-Alone CHIP</th>
      <th>Stand-Alone CHIP Charges</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>16</th>
      <td>752657</td>
      <td>363045</td>
      <td>EVEREST REHABILITATION HOSPITAL NORT</td>
      <td>7810 BETHANY RD</td>
      <td>LIBERTY TOWNSHIP</td>
      <td>OH</td>
      <td>45044</td>
      <td>BUTLER</td>
      <td>17140.0</td>
      <td>U</td>
      <td>RH</td>
      <td>5</td>
      <td>6</td>
      <td>01/01/2023</td>
      <td>02/28/2023</td>
      <td>54.37</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>432.0</td>
      <td>15.0</td>
      <td>608.0</td>
      <td>36.0</td>
      <td>2124.0</td>
      <td>NaN</td>
      <td>41.0</td>
      <td>1.0</td>
      <td>53.0</td>
      <td>36.0</td>
      <td>NaN</td>
      <td>432.0</td>
      <td>15.0</td>
      <td>608.0</td>
      <td>36.0</td>
      <td>2124.0</td>
      <td>NaN</td>
      <td>41.0</td>
      <td>1.0</td>
      <td>53.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>786929.0</td>
      <td>1.339796e+06</td>
      <td>290888.0</td>
      <td>3.399352e+06</td>
      <td>1.707395e+06</td>
      <td>NaN</td>
      <td>1.707395e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>466135.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>371835.0</td>
      <td>-252664.0</td>
      <td>60382.0</td>
      <td>12415.0</td>
      <td>272772.0</td>
      <td>930875.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.260304e+07</td>
      <td>NaN</td>
      <td>39347.0</td>
      <td>1297083.0</td>
      <td>308354.0</td>
      <td>NaN</td>
      <td>2.297482e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.021870e+05</td>
      <td>2.450788e+07</td>
      <td>130841.0</td>
      <td>70192.0</td>
      <td>-42.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>498982.0</td>
      <td>699973.0</td>
      <td>21642956.0</td>
      <td>2.051660e+05</td>
      <td>NaN</td>
      <td>8.390192e+06</td>
      <td>3.023831e+07</td>
      <td>3.093829e+07</td>
      <td>-6430404.0</td>
      <td>-6430404.0</td>
      <td>2.450788e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.707394e+06</td>
      <td>NaN</td>
      <td>1.707394e+06</td>
      <td>9.087280e+05</td>
      <td>7.986660e+05</td>
      <td>2.126725e+06</td>
      <td>-1328059.0</td>
      <td>1083.0</td>
      <td>-1326976.0</td>
      <td>NaN</td>
      <td>-1326976.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>647</th>
      <td>769454</td>
      <td>362032</td>
      <td>AULTMAN SPECIALTY HOSPITAL</td>
      <td>2600 - SIXTH STREET SW</td>
      <td>CANTON</td>
      <td>OH</td>
      <td>44710</td>
      <td>STARK</td>
      <td>15940.0</td>
      <td>U</td>
      <td>LTCH</td>
      <td>2</td>
      <td>2</td>
      <td>10/01/2022</td>
      <td>09/30/2023</td>
      <td>19.88</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>481.0</td>
      <td>156.0</td>
      <td>1987.0</td>
      <td>30.0</td>
      <td>10950.0</td>
      <td>NaN</td>
      <td>24.0</td>
      <td>5.0</td>
      <td>72.0</td>
      <td>30.0</td>
      <td>NaN</td>
      <td>481.0</td>
      <td>156.0</td>
      <td>1987.0</td>
      <td>30.0</td>
      <td>10950.0</td>
      <td>NaN</td>
      <td>24.0</td>
      <td>5.0</td>
      <td>72.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1933779.0</td>
      <td>2.236188e+06</td>
      <td>NaN</td>
      <td>4.033564e+06</td>
      <td>6.573601e+06</td>
      <td>NaN</td>
      <td>6.573601e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>423372.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>616795.0</td>
      <td>-301199.0</td>
      <td>NaN</td>
      <td>2500.0</td>
      <td>NaN</td>
      <td>3342026.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.342026e+06</td>
      <td>100706.0</td>
      <td>8093.0</td>
      <td>-8093.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>100706.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.007060e+05</td>
      <td>3241320.0</td>
      <td>3241320.0</td>
      <td>3.342026e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.573601e+06</td>
      <td>NaN</td>
      <td>6.573601e+06</td>
      <td>3.721306e+06</td>
      <td>2.852295e+06</td>
      <td>4.169967e+06</td>
      <td>-1317672.0</td>
      <td>40064.0</td>
      <td>-1277608.0</td>
      <td>NaN</td>
      <td>-1277608.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>687</th>
      <td>770581</td>
      <td>362027</td>
      <td>SSH - AKRON  LLC</td>
      <td>200 EAST MARKET STREET</td>
      <td>AKRON</td>
      <td>OH</td>
      <td>44308</td>
      <td>SUMMIT</td>
      <td>10420.0</td>
      <td>U</td>
      <td>LTCH</td>
      <td>2</td>
      <td>4</td>
      <td>12/01/2022</td>
      <td>11/30/2023</td>
      <td>172.81</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3673.0</td>
      <td>2066.0</td>
      <td>15538.0</td>
      <td>60.0</td>
      <td>21900.0</td>
      <td>NaN</td>
      <td>140.0</td>
      <td>67.0</td>
      <td>565.0</td>
      <td>60.0</td>
      <td>NaN</td>
      <td>3673.0</td>
      <td>2066.0</td>
      <td>15538.0</td>
      <td>60.0</td>
      <td>21900.0</td>
      <td>NaN</td>
      <td>140.0</td>
      <td>67.0</td>
      <td>565.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13216458.0</td>
      <td>1.936431e+07</td>
      <td>710694.0</td>
      <td>2.978976e+07</td>
      <td>2.242922e+08</td>
      <td>NaN</td>
      <td>2.242922e+08</td>
      <td>2099014.0</td>
      <td>NaN</td>
      <td>13216458.0</td>
      <td>1198653.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5478412.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>346614.0</td>
      <td>162065.0</td>
      <td>5987091.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.323050e+05</td>
      <td>167097.0</td>
      <td>NaN</td>
      <td>6530750.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.895042e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.784473e+07</td>
      <td>3.572686e+07</td>
      <td>2009550.0</td>
      <td>2520039.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5090812.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.304005e+07</td>
      <td>2.304005e+07</td>
      <td>2.813086e+07</td>
      <td>7595999.0</td>
      <td>7595999.0</td>
      <td>3.572686e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.242922e+08</td>
      <td>NaN</td>
      <td>2.242922e+08</td>
      <td>1.890665e+08</td>
      <td>3.522571e+07</td>
      <td>3.258076e+07</td>
      <td>2644946.0</td>
      <td>71770.0</td>
      <td>2716716.0</td>
      <td>-68764.0</td>
      <td>2785480.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>751</th>
      <td>772302</td>
      <td>360189</td>
      <td>MADISON HEALTH</td>
      <td>210 NORTH MAIN STREET</td>
      <td>LONDON</td>
      <td>OH</td>
      <td>43140-</td>
      <td>MADISON</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>240.91</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>837.0</td>
      <td>41.0</td>
      <td>3398.0</td>
      <td>45.0</td>
      <td>16425.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>45.0</td>
      <td>NaN</td>
      <td>464.0</td>
      <td>28.0</td>
      <td>1990.0</td>
      <td>32.0</td>
      <td>11680.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>496204.0</td>
      <td>5407503.0</td>
      <td>1741928.0</td>
      <td>5319204.0</td>
      <td>18010729.0</td>
      <td>3.367992e+07</td>
      <td>5293848.0</td>
      <td>4.602876e+07</td>
      <td>2.958593e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>5182408.0</td>
      <td>NaN</td>
      <td>18010729.0</td>
      <td>1154149.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2664688.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7969832.0</td>
      <td>NaN</td>
      <td>1161089.0</td>
      <td>1543583.0</td>
      <td>NaN</td>
      <td>16694600.0</td>
      <td>2058728.0</td>
      <td>1432397.0</td>
      <td>4.912698e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>28774601.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.575774e+07</td>
      <td>37072011.0</td>
      <td>3870344.0</td>
      <td>4.094236e+07</td>
      <td>9.339470e+07</td>
      <td>2216194.0</td>
      <td>3060674.0</td>
      <td>NaN</td>
      <td>1620663.0</td>
      <td>NaN</td>
      <td>1974927.0</td>
      <td>8872458.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.599493e+07</td>
      <td>3.599493e+07</td>
      <td>4.486739e+07</td>
      <td>48527314.0</td>
      <td>48527314.0</td>
      <td>9.339470e+07</td>
      <td>NaN</td>
      <td>1399457.0</td>
      <td>380850.0</td>
      <td>NaN</td>
      <td>53410.0</td>
      <td>0.12</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.958594e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>1.413727e+08</td>
      <td>6.025978e+07</td>
      <td>5.101758e+07</td>
      <td>9242202.0</td>
      <td>-2053858.0</td>
      <td>7188344.0</td>
      <td>-680.0</td>
      <td>7189024.0</td>
      <td>0.228281</td>
      <td>4628233.0</td>
      <td>3.594478e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>752</th>
      <td>772303</td>
      <td>360351</td>
      <td>CRYSTAL CLINIC ORTHOPAEDIC CENTER</td>
      <td>444 N. MAIN STREET</td>
      <td>AKRON</td>
      <td>OH</td>
      <td>44310</td>
      <td>SUMMIT</td>
      <td>10420.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>4</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>829.28</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>59.0</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>NaN</td>
      <td>4966858.0</td>
      <td>1025756.0</td>
      <td>4491088.0</td>
      <td>59842683.0</td>
      <td>1.410437e+08</td>
      <td>19791461.0</td>
      <td>1.757999e+08</td>
      <td>1.723140e+08</td>
      <td>6.789364e+08</td>
      <td>8.512503e+08</td>
      <td>16227538.0</td>
      <td>NaN</td>
      <td>59842683.0</td>
      <td>2833456.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20226359.0</td>
      <td>NaN</td>
      <td>91445.0</td>
      <td>143984935.0</td>
      <td>-115969987.0</td>
      <td>4254008.0</td>
      <td>5590825.0</td>
      <td>364672.0</td>
      <td>58542257.0</td>
      <td>1797791.0</td>
      <td>972311.0</td>
      <td>7.353677e+06</td>
      <td>14842928.0</td>
      <td>5829690.0</td>
      <td>40446507.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.777400e+07</td>
      <td>NaN</td>
      <td>116070299.0</td>
      <td>1.160703e+08</td>
      <td>2.123866e+08</td>
      <td>5248828.0</td>
      <td>5287289.0</td>
      <td>NaN</td>
      <td>15147407.0</td>
      <td>NaN</td>
      <td>13317765.0</td>
      <td>39001289.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.039823e+08</td>
      <td>1.039823e+08</td>
      <td>1.429836e+08</td>
      <td>69402949.0</td>
      <td>69402949.0</td>
      <td>2.123866e+08</td>
      <td>NaN</td>
      <td>8019249.0</td>
      <td>2943604.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.723155e+08</td>
      <td>7.043064e+08</td>
      <td>8.766219e+08</td>
      <td>6.728033e+08</td>
      <td>2.038185e+08</td>
      <td>2.008864e+08</td>
      <td>2932156.0</td>
      <td>4699468.0</td>
      <td>7631624.0</td>
      <td>NaN</td>
      <td>7631624.0</td>
      <td>0.206520</td>
      <td>6048085.0</td>
      <td>4.606535e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>5863</th>
      <td>803875</td>
      <td>364063</td>
      <td>GEORGETOWN BEHAVIORAL HOSPITAL</td>
      <td>425 HOME STREET</td>
      <td>GEORGETOWN</td>
      <td>OH</td>
      <td>45121-1407</td>
      <td>BROWN</td>
      <td>17140.0</td>
      <td>U</td>
      <td>PH</td>
      <td>4</td>
      <td>4</td>
      <td>07/01/2023</td>
      <td>07/31/2024</td>
      <td>17.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>380.0</td>
      <td>NaN</td>
      <td>2238.0</td>
      <td>24.0</td>
      <td>9504.0</td>
      <td>NaN</td>
      <td>37.0</td>
      <td>NaN</td>
      <td>249.0</td>
      <td>24.0</td>
      <td>NaN</td>
      <td>380.0</td>
      <td>NaN</td>
      <td>2238.0</td>
      <td>24.0</td>
      <td>9504.0</td>
      <td>NaN</td>
      <td>37.0</td>
      <td>NaN</td>
      <td>249.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1890342.0</td>
      <td>2.252392e+06</td>
      <td>36752.0</td>
      <td>2.792093e+06</td>
      <td>3.357004e+06</td>
      <td>NaN</td>
      <td>3.357004e+06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>-5303.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>285551.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>60380.0</td>
      <td>NaN</td>
      <td>340628.0</td>
      <td>NaN</td>
      <td>13900.0</td>
      <td>1.220200e+04</td>
      <td>NaN</td>
      <td>53228.0</td>
      <td>117105.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.214960e+05</td>
      <td>NaN</td>
      <td>4264.0</td>
      <td>4.264000e+03</td>
      <td>4.663880e+05</td>
      <td>2600379.0</td>
      <td>9539.0</td>
      <td>11231.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>38649.0</td>
      <td>2659798.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>8.544562e+06</td>
      <td>8.544562e+06</td>
      <td>1.120436e+07</td>
      <td>-10737972.0</td>
      <td>-10737972.0</td>
      <td>4.663880e+05</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.806343e+06</td>
      <td>NaN</td>
      <td>3.806343e+06</td>
      <td>2.027437e+06</td>
      <td>1.778906e+06</td>
      <td>4.142734e+06</td>
      <td>-2363828.0</td>
      <td>1245.0</td>
      <td>-2362583.0</td>
      <td>NaN</td>
      <td>-2362583.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5868</th>
      <td>804003</td>
      <td>360143</td>
      <td>MARYMOUNT HOSPITAL</td>
      <td>12300 MCCRACKEN ROAD</td>
      <td>GARFIELD HTS.</td>
      <td>OH</td>
      <td>44125-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>743.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7617.0</td>
      <td>1004.0</td>
      <td>32016.0</td>
      <td>188.0</td>
      <td>68620.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>262.0</td>
      <td>NaN</td>
      <td>6670.0</td>
      <td>864.0</td>
      <td>28081.0</td>
      <td>160.0</td>
      <td>58400.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>4960258.0</td>
      <td>6005537.0</td>
      <td>6610489.0</td>
      <td>20288869.0</td>
      <td>68760998.0</td>
      <td>1.288689e+08</td>
      <td>13004822.0</td>
      <td>1.861900e+08</td>
      <td>2.915091e+08</td>
      <td>4.133701e+08</td>
      <td>7.048792e+08</td>
      <td>15485875.0</td>
      <td>NaN</td>
      <td>68760998.0</td>
      <td>10372586.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3327.0</td>
      <td>8750189.0</td>
      <td>NaN</td>
      <td>35798654.0</td>
      <td>-12021126.0</td>
      <td>5908241.0</td>
      <td>187265.0</td>
      <td>NaN</td>
      <td>40704523.0</td>
      <td>2156995.0</td>
      <td>9811905.0</td>
      <td>1.891104e+08</td>
      <td>2497691.0</td>
      <td>604085.0</td>
      <td>47685000.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9.535494e+07</td>
      <td>39783842.0</td>
      <td>3642514.0</td>
      <td>4.342636e+07</td>
      <td>1.794858e+08</td>
      <td>8567580.0</td>
      <td>6329099.0</td>
      <td>160114.0</td>
      <td>11316159.0</td>
      <td>NaN</td>
      <td>1607638.0</td>
      <td>27980590.0</td>
      <td>NaN</td>
      <td>3.013659e+07</td>
      <td>NaN</td>
      <td>-2.380000e+04</td>
      <td>3.011279e+07</td>
      <td>5.809338e+07</td>
      <td>121392439.0</td>
      <td>121392439.0</td>
      <td>1.794858e+08</td>
      <td>NaN</td>
      <td>9998352.0</td>
      <td>3597148.0</td>
      <td>NaN</td>
      <td>294682.0</td>
      <td>0.00</td>
      <td>23296909.0</td>
      <td>NaN</td>
      <td>2.919227e+08</td>
      <td>4.143265e+08</td>
      <td>7.062492e+08</td>
      <td>5.214664e+08</td>
      <td>1.847829e+08</td>
      <td>1.976299e+08</td>
      <td>-12847074.0</td>
      <td>13090602.0</td>
      <td>243528.0</td>
      <td>NaN</td>
      <td>243528.0</td>
      <td>0.000000</td>
      <td>23534379.0</td>
      <td>1.543868e+08</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5877</th>
      <td>804173</td>
      <td>360348</td>
      <td>DUBLIN METHODIST HOSPITAL</td>
      <td>7500 HOSPITAL DRIVE</td>
      <td>DUBLIN</td>
      <td>OH</td>
      <td>43016</td>
      <td>FRANKLIN</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>07/01/2023</td>
      <td>06/30/2024</td>
      <td>859.00</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1840.0</td>
      <td>31253.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>110.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1544.0</td>
      <td>26218.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>8662644.0</td>
      <td>6529247.0</td>
      <td>9971937.0</td>
      <td>18212017.0</td>
      <td>90872508.0</td>
      <td>1.670756e+08</td>
      <td>3714520.0</td>
      <td>2.098559e+08</td>
      <td>3.923512e+08</td>
      <td>6.831627e+08</td>
      <td>1.075514e+09</td>
      <td>18520085.0</td>
      <td>NaN</td>
      <td>90076936.0</td>
      <td>6895971.0</td>
      <td>NaN</td>
      <td>284692.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>213365159.0</td>
      <td>-158441459.0</td>
      <td>4583939.0</td>
      <td>NaN</td>
      <td>1826117.0</td>
      <td>62663175.0</td>
      <td>12002054.0</td>
      <td>4304133.0</td>
      <td>1.064236e+08</td>
      <td>NaN</td>
      <td>57315630.0</td>
      <td>36133457.0</td>
      <td>5318246.0</td>
      <td>NaN</td>
      <td>9.830465e+07</td>
      <td>NaN</td>
      <td>5493960.0</td>
      <td>5.493960e+06</td>
      <td>1.664618e+08</td>
      <td>7361901.0</td>
      <td>7402489.0</td>
      <td>NaN</td>
      <td>22046460.0</td>
      <td>NaN</td>
      <td>15200134.0</td>
      <td>52010984.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.901896e+08</td>
      <td>1.901896e+08</td>
      <td>2.422006e+08</td>
      <td>-75738784.0</td>
      <td>-75738784.0</td>
      <td>1.664618e+08</td>
      <td>NaN</td>
      <td>3886533.0</td>
      <td>13695949.0</td>
      <td>NaN</td>
      <td>208793.0</td>
      <td>0.00</td>
      <td>18207187.0</td>
      <td>1329710.0</td>
      <td>3.923885e+08</td>
      <td>6.831627e+08</td>
      <td>1.075551e+09</td>
      <td>7.004998e+08</td>
      <td>3.750514e+08</td>
      <td>2.579481e+08</td>
      <td>117103275.0</td>
      <td>3609144.0</td>
      <td>120712419.0</td>
      <td>NaN</td>
      <td>120712419.0</td>
      <td>0.000000</td>
      <td>9424320.0</td>
      <td>9.308563e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6015</th>
      <td>806349</td>
      <td>360144</td>
      <td>SOUTH POINTE HOSPITAL</td>
      <td>4110 WARRENSVILLE CENTER ROAD</td>
      <td>WARRENSVILLE HEIGHTS</td>
      <td>OH</td>
      <td>44122-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>681.00</td>
      <td>32.0</td>
      <td>NaN</td>
      <td>7495.0</td>
      <td>1723.0</td>
      <td>30896.0</td>
      <td>138.0</td>
      <td>51424.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>138.0</td>
      <td>NaN</td>
      <td>6763.0</td>
      <td>1146.0</td>
      <td>22962.0</td>
      <td>96.0</td>
      <td>36094.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>3404647.0</td>
      <td>5056528.0</td>
      <td>4612672.0</td>
      <td>9297780.0</td>
      <td>57312306.0</td>
      <td>9.714770e+07</td>
      <td>9197783.0</td>
      <td>1.297566e+08</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>12323638.0</td>
      <td>NaN</td>
      <td>59365336.0</td>
      <td>13294493.0</td>
      <td>20052.0</td>
      <td>1077300.0</td>
      <td>2041.0</td>
      <td>-110582469.0</td>
      <td>NaN</td>
      <td>25837032.0</td>
      <td>-10247255.0</td>
      <td>4513176.0</td>
      <td>180759.0</td>
      <td>NaN</td>
      <td>-88970100.0</td>
      <td>4703177.0</td>
      <td>8196400.0</td>
      <td>1.427239e+08</td>
      <td>24966.0</td>
      <td>2244703.0</td>
      <td>29978152.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.180659e+07</td>
      <td>NaN</td>
      <td>4059481.0</td>
      <td>4.059481e+06</td>
      <td>-2.310403e+07</td>
      <td>5085976.0</td>
      <td>3691350.0</td>
      <td>NaN</td>
      <td>5419373.0</td>
      <td>NaN</td>
      <td>969652.0</td>
      <td>15166351.0</td>
      <td>NaN</td>
      <td>1.737651e+07</td>
      <td>NaN</td>
      <td>1.936435e+06</td>
      <td>1.931295e+07</td>
      <td>3.447930e+07</td>
      <td>-57583330.0</td>
      <td>-57583330.0</td>
      <td>-2.310403e+07</td>
      <td>NaN</td>
      <td>9785083.0</td>
      <td>3206009.0</td>
      <td>NaN</td>
      <td>347512.0</td>
      <td>0.00</td>
      <td>21935652.0</td>
      <td>1393594.0</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>4.463686e+08</td>
      <td>1.428610e+08</td>
      <td>1.544600e+08</td>
      <td>-11598964.0</td>
      <td>3247968.0</td>
      <td>-8350996.0</td>
      <td>NaN</td>
      <td>-8350996.0</td>
      <td>0.000000</td>
      <td>21682032.0</td>
      <td>1.265699e+08</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6085</th>
      <td>807149</td>
      <td>360059</td>
      <td>METROHEALTH MEDICAL CENTER</td>
      <td>2500 METROHEALTH DRIVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44109</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>13</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>7711.00</td>
      <td>400.0</td>
      <td>NaN</td>
      <td>13400.0</td>
      <td>7587.0</td>
      <td>113599.0</td>
      <td>501.0</td>
      <td>182865.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>670.0</td>
      <td>NaN</td>
      <td>11346.0</td>
      <td>5024.0</td>
      <td>82749.0</td>
      <td>398.0</td>
      <td>145270.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>52249491.0</td>
      <td>41241147.0</td>
      <td>64768232.0</td>
      <td>172613758.0</td>
      <td>815495894.0</td>
      <td>1.022078e+09</td>
      <td>122305389.0</td>
      <td>1.144066e+09</td>
      <td>1.305561e+09</td>
      <td>2.477536e+09</td>
      <td>3.783097e+09</td>
      <td>151234382.0</td>
      <td>NaN</td>
      <td>815495894.0</td>
      <td>4095473.0</td>
      <td>2234972.0</td>
      <td>6887728.0</td>
      <td>167167876.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>181964719.0</td>
      <td>-32420355.0</td>
      <td>28286678.0</td>
      <td>18745013.0</td>
      <td>NaN</td>
      <td>451274662.0</td>
      <td>274381921.0</td>
      <td>25832250.0</td>
      <td>1.035162e+09</td>
      <td>17809023.0</td>
      <td>398974483.0</td>
      <td>259449588.0</td>
      <td>2564590.0</td>
      <td>NaN</td>
      <td>1.234442e+09</td>
      <td>536909228.0</td>
      <td>734717506.0</td>
      <td>1.271627e+09</td>
      <td>2.957343e+09</td>
      <td>89655513.0</td>
      <td>122910887.0</td>
      <td>NaN</td>
      <td>24192974.0</td>
      <td>NaN</td>
      <td>32359137.0</td>
      <td>270430031.0</td>
      <td>NaN</td>
      <td>1.090432e+09</td>
      <td>NaN</td>
      <td>1.183095e+09</td>
      <td>2.273527e+09</td>
      <td>2.543957e+09</td>
      <td>413385756.0</td>
      <td>413385756.0</td>
      <td>2.957343e+09</td>
      <td>NaN</td>
      <td>19277875.0</td>
      <td>6847645.0</td>
      <td>NaN</td>
      <td>2427061.0</td>
      <td>0.00</td>
      <td>57246922.0</td>
      <td>7608953.0</td>
      <td>1.512498e+09</td>
      <td>3.187045e+09</td>
      <td>4.699543e+09</td>
      <td>3.424704e+09</td>
      <td>1.274839e+09</td>
      <td>1.842426e+09</td>
      <td>-567586421.0</td>
      <td>598744604.0</td>
      <td>31158183.0</td>
      <td>NaN</td>
      <td>31158183.0</td>
      <td>0.000000</td>
      <td>276594217.0</td>
      <td>1.271232e+09</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>135 rows × 117 columns</p>
</div>



```python
# DATA CLEANING: DROP MISSING CCR + QUICK CHECKS

cms_ccr_oh_u.dropna(subset=['Cost To Charge Ratio'], inplace=True)

display(cms_ccr_oh_u)

```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rpt_rec_num</th>
      <th>Provider CCN</th>
      <th>Hospital Name</th>
      <th>Street Address</th>
      <th>City</th>
      <th>State Code</th>
      <th>Zip Code</th>
      <th>County</th>
      <th>Medicare CBSA Number</th>
      <th>Rural Versus Urban</th>
      <th>CCN Facility Type</th>
      <th>Provider Type</th>
      <th>Type of Control</th>
      <th>Fiscal Year Begin Date</th>
      <th>Fiscal Year End Date</th>
      <th>FTE - Employees on Payroll</th>
      <th>Number of Interns and Residents (FTE)</th>
      <th>Total Days Title V</th>
      <th>Total Days Title XVIII</th>
      <th>Total Days Title XIX</th>
      <th>Total Days (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds</th>
      <th>Total Bed Days Available</th>
      <th>Total Discharges Title V</th>
      <th>Total Discharges Title XVIII</th>
      <th>Total Discharges Title XIX</th>
      <th>Total Discharges (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds + Total for all Subproviders</th>
      <th>Hospital Total Days Title V For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Days (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Hospital Number of Beds For Adults &amp; Peds</th>
      <th>Hospital Total Bed Days Available For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title V For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Discharges (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Cost of Charity Care</th>
      <th>Total Bad Debt Expense</th>
      <th>Cost of Uncompensated Care</th>
      <th>Total Unreimbursed and Uncompensated Care</th>
      <th>Total Salaries From Worksheet A</th>
      <th>Overhead Non-Salary Costs</th>
      <th>Depreciation Cost</th>
      <th>Total Costs</th>
      <th>Inpatient Total Charges</th>
      <th>Outpatient Total Charges</th>
      <th>Combined Outpatient + Inpatient Total Charges</th>
      <th>Wage-Related Costs (Core)</th>
      <th>Wage-Related Costs (RHC/FQHC)</th>
      <th>Total Salaries (adjusted)</th>
      <th>Contract Labor: Direct Patient Care</th>
      <th>Wage Related Costs for Part - A Teaching Physicians</th>
      <th>Wage Related Costs for Interns and Residents</th>
      <th>Cash on Hand and in Banks</th>
      <th>Temporary Investments</th>
      <th>Notes Receivable</th>
      <th>Accounts Receivable</th>
      <th>Less: Allowances for Uncollectible Notes and Accounts Receivable</th>
      <th>Inventory</th>
      <th>Prepaid Expenses</th>
      <th>Other Current Assets</th>
      <th>Total Current Assets</th>
      <th>Land</th>
      <th>Land Improvements</th>
      <th>Buildings</th>
      <th>Leasehold Improvements</th>
      <th>Fixed Equipment</th>
      <th>Major Movable Equipment</th>
      <th>Minor Equipment Depreciable</th>
      <th>Health Information Technology Designated Assets</th>
      <th>Total Fixed Assets</th>
      <th>Investments</th>
      <th>Other Assets</th>
      <th>Total Other Assets</th>
      <th>Total Assets</th>
      <th>Accounts Payable</th>
      <th>Salaries, Wages, and Fees Payable</th>
      <th>Payroll Taxes Payable</th>
      <th>Notes and Loans Payable (Short Term)</th>
      <th>Deferred Income</th>
      <th>Other Current Liabilities</th>
      <th>Total Current Liabilities</th>
      <th>Mortgage Payable</th>
      <th>Notes Payable</th>
      <th>Unsecured Loans</th>
      <th>Other Long Term Liabilities</th>
      <th>Total Long Term Liabilities</th>
      <th>Total Liabilities</th>
      <th>General Fund Balance</th>
      <th>Total Fund Balances</th>
      <th>Total Liabilities and Fund Balances</th>
      <th>DRG Amounts Other Than Outlier Payments</th>
      <th>DRG Amounts Before October 1</th>
      <th>DRG Amounts After October 1</th>
      <th>Outlier Payments For Discharges</th>
      <th>Disproportionate Share Adjustment</th>
      <th>Allowable DSH Percentage</th>
      <th>Managed Care Simulated Payments</th>
      <th>Total IME Payment</th>
      <th>Inpatient Revenue</th>
      <th>Outpatient Revenue</th>
      <th>Total Patient Revenue</th>
      <th>Less Contractual Allowance and Discounts on Patients' Accounts</th>
      <th>Net Patient Revenue</th>
      <th>Less Total Operating Expense</th>
      <th>Net Income from Service to Patients</th>
      <th>Total Other Income</th>
      <th>Total Income</th>
      <th>Total Other Expenses</th>
      <th>Net Income</th>
      <th>Cost To Charge Ratio</th>
      <th>Net Revenue from Medicaid</th>
      <th>Medicaid Charges</th>
      <th>Net Revenue from Stand-Alone CHIP</th>
      <th>Stand-Alone CHIP Charges</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>751</th>
      <td>772302</td>
      <td>360189</td>
      <td>MADISON HEALTH</td>
      <td>210 NORTH MAIN STREET</td>
      <td>LONDON</td>
      <td>OH</td>
      <td>43140-</td>
      <td>MADISON</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>240.91</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>837.0</td>
      <td>41.0</td>
      <td>3398.0</td>
      <td>45.0</td>
      <td>16425.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>45.0</td>
      <td>NaN</td>
      <td>464.0</td>
      <td>28.0</td>
      <td>1990.0</td>
      <td>32.0</td>
      <td>11680.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>496204.0</td>
      <td>5407503.0</td>
      <td>1741928.0</td>
      <td>5319204.0</td>
      <td>18010729.0</td>
      <td>3.367992e+07</td>
      <td>5293848.0</td>
      <td>4.602876e+07</td>
      <td>2.958593e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>5182408.0</td>
      <td>NaN</td>
      <td>18010729.0</td>
      <td>1154149.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2664688.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7969832.0</td>
      <td>NaN</td>
      <td>1161089.0</td>
      <td>1543583.0</td>
      <td>NaN</td>
      <td>16694600.0</td>
      <td>2058728.0</td>
      <td>1432397.0</td>
      <td>4.912698e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>28774601.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.575774e+07</td>
      <td>3.707201e+07</td>
      <td>3870344.0</td>
      <td>4.094236e+07</td>
      <td>9.339470e+07</td>
      <td>2216194.0</td>
      <td>3060674.0</td>
      <td>NaN</td>
      <td>1620663.0</td>
      <td>NaN</td>
      <td>1974927.0</td>
      <td>8872458.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.599493e+07</td>
      <td>3.599493e+07</td>
      <td>4.486739e+07</td>
      <td>4.852731e+07</td>
      <td>4.852731e+07</td>
      <td>9.339470e+07</td>
      <td>NaN</td>
      <td>1399457.0</td>
      <td>380850.0</td>
      <td>NaN</td>
      <td>53410.0</td>
      <td>0.1200</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.958594e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>1.413727e+08</td>
      <td>6.025978e+07</td>
      <td>5.101758e+07</td>
      <td>9242202.0</td>
      <td>-2053858.0</td>
      <td>7188344.0</td>
      <td>-680.0</td>
      <td>7189024.0</td>
      <td>0.228281</td>
      <td>4628233.0</td>
      <td>3.594478e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>752</th>
      <td>772303</td>
      <td>360351</td>
      <td>CRYSTAL CLINIC ORTHOPAEDIC CENTER</td>
      <td>444 N. MAIN STREET</td>
      <td>AKRON</td>
      <td>OH</td>
      <td>44310</td>
      <td>SUMMIT</td>
      <td>10420.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>4</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>829.28</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>59.0</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>NaN</td>
      <td>4966858.0</td>
      <td>1025756.0</td>
      <td>4491088.0</td>
      <td>59842683.0</td>
      <td>1.410437e+08</td>
      <td>19791461.0</td>
      <td>1.757999e+08</td>
      <td>1.723140e+08</td>
      <td>6.789364e+08</td>
      <td>8.512503e+08</td>
      <td>16227538.0</td>
      <td>NaN</td>
      <td>59842683.0</td>
      <td>2833456.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20226359.0</td>
      <td>NaN</td>
      <td>91445.0</td>
      <td>143984935.0</td>
      <td>-115969987.0</td>
      <td>4254008.0</td>
      <td>5590825.0</td>
      <td>364672.0</td>
      <td>58542257.0</td>
      <td>1797791.0</td>
      <td>972311.0</td>
      <td>7.353677e+06</td>
      <td>14842928.0</td>
      <td>5829690.0</td>
      <td>40446507.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.777400e+07</td>
      <td>NaN</td>
      <td>116070299.0</td>
      <td>1.160703e+08</td>
      <td>2.123866e+08</td>
      <td>5248828.0</td>
      <td>5287289.0</td>
      <td>NaN</td>
      <td>15147407.0</td>
      <td>NaN</td>
      <td>13317765.0</td>
      <td>39001289.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.039823e+08</td>
      <td>1.039823e+08</td>
      <td>1.429836e+08</td>
      <td>6.940295e+07</td>
      <td>6.940295e+07</td>
      <td>2.123866e+08</td>
      <td>NaN</td>
      <td>8019249.0</td>
      <td>2943604.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.723155e+08</td>
      <td>7.043064e+08</td>
      <td>8.766219e+08</td>
      <td>6.728033e+08</td>
      <td>2.038185e+08</td>
      <td>2.008864e+08</td>
      <td>2932156.0</td>
      <td>4699468.0</td>
      <td>7631624.0</td>
      <td>NaN</td>
      <td>7631624.0</td>
      <td>0.206520</td>
      <td>6048085.0</td>
      <td>4.606535e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>907</th>
      <td>773604</td>
      <td>360092</td>
      <td>MEMORIAL HOSPITAL OF UNION COUNTY</td>
      <td>500 LONDON AVENUE</td>
      <td>MARYSVILLE</td>
      <td>OH</td>
      <td>43040-</td>
      <td>UNION</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>9</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>715.78</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1888.0</td>
      <td>466.0</td>
      <td>8688.0</td>
      <td>51.0</td>
      <td>18615.0</td>
      <td>NaN</td>
      <td>664.0</td>
      <td>55.0</td>
      <td>2719.0</td>
      <td>51.0</td>
      <td>NaN</td>
      <td>1784.0</td>
      <td>83.0</td>
      <td>7310.0</td>
      <td>39.0</td>
      <td>14235.0</td>
      <td>NaN</td>
      <td>664.0</td>
      <td>55.0</td>
      <td>2719.0</td>
      <td>1296612.0</td>
      <td>10184707.0</td>
      <td>4471898.0</td>
      <td>10932284.0</td>
      <td>60532285.0</td>
      <td>1.020931e+08</td>
      <td>9549895.0</td>
      <td>1.336948e+08</td>
      <td>7.755640e+07</td>
      <td>3.522619e+08</td>
      <td>4.298183e+08</td>
      <td>16558853.0</td>
      <td>NaN</td>
      <td>60532285.0</td>
      <td>1694453.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>39553623.0</td>
      <td>13286590.0</td>
      <td>NaN</td>
      <td>21815875.0</td>
      <td>NaN</td>
      <td>1954919.0</td>
      <td>2096449.0</td>
      <td>1011916.0</td>
      <td>85393958.0</td>
      <td>3017141.0</td>
      <td>5246439.0</td>
      <td>1.162705e+08</td>
      <td>NaN</td>
      <td>2737700.0</td>
      <td>87307904.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.282003e+08</td>
      <td>7.960842e+07</td>
      <td>47234308.0</td>
      <td>1.268427e+08</td>
      <td>3.404370e+08</td>
      <td>11247442.0</td>
      <td>12095547.0</td>
      <td>NaN</td>
      <td>28559091.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>52567080.0</td>
      <td>NaN</td>
      <td>6.777074e+07</td>
      <td>NaN</td>
      <td>9.047551e+07</td>
      <td>1.582462e+08</td>
      <td>2.108133e+08</td>
      <td>1.296237e+08</td>
      <td>1.296237e+08</td>
      <td>3.404370e+08</td>
      <td>NaN</td>
      <td>3889441.0</td>
      <td>1652815.0</td>
      <td>NaN</td>
      <td>80086.0</td>
      <td>0.0578</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.770045e+07</td>
      <td>3.680071e+08</td>
      <td>4.457075e+08</td>
      <td>2.731381e+08</td>
      <td>1.725695e+08</td>
      <td>1.755439e+08</td>
      <td>-2974447.0</td>
      <td>12398185.0</td>
      <td>9423738.0</td>
      <td>133399.0</td>
      <td>9290339.0</td>
      <td>0.311050</td>
      <td>7711324.0</td>
      <td>5.137945e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>908</th>
      <td>773606</td>
      <td>360263</td>
      <td>INSTITUTE FOR ORTHOPAEDIC SURGERY</td>
      <td>801 MEDICAL DRIVE</td>
      <td>LIMA</td>
      <td>OH</td>
      <td>45804</td>
      <td>ALLEN</td>
      <td>30620.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>6</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>175.06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>645.0</td>
      <td>18.0</td>
      <td>1230.0</td>
      <td>12.0</td>
      <td>4380.0</td>
      <td>NaN</td>
      <td>284.0</td>
      <td>12.0</td>
      <td>581.0</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>645.0</td>
      <td>18.0</td>
      <td>1230.0</td>
      <td>12.0</td>
      <td>4380.0</td>
      <td>NaN</td>
      <td>284.0</td>
      <td>12.0</td>
      <td>581.0</td>
      <td>NaN</td>
      <td>2620740.0</td>
      <td>419156.0</td>
      <td>683481.0</td>
      <td>11308402.0</td>
      <td>3.003173e+07</td>
      <td>-4154.0</td>
      <td>3.649592e+07</td>
      <td>1.228750e+08</td>
      <td>1.074157e+08</td>
      <td>2.302907e+08</td>
      <td>3573493.0</td>
      <td>NaN</td>
      <td>11308402.0</td>
      <td>103036.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1164259.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9391865.0</td>
      <td>-1858489.0</td>
      <td>1443630.0</td>
      <td>284126.0</td>
      <td>NaN</td>
      <td>10425391.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>104120.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.042539e+07</td>
      <td>2730598.0</td>
      <td>492461.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>330076.0</td>
      <td>3553135.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.500000e+05</td>
      <td>2.500000e+05</td>
      <td>3.803135e+06</td>
      <td>6.622256e+06</td>
      <td>6.622256e+06</td>
      <td>1.042539e+07</td>
      <td>NaN</td>
      <td>2949645.0</td>
      <td>983215.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.228750e+08</td>
      <td>1.074157e+08</td>
      <td>2.302907e+08</td>
      <td>1.676803e+08</td>
      <td>6.261041e+07</td>
      <td>4.134013e+07</td>
      <td>21270276.0</td>
      <td>3228154.0</td>
      <td>24498430.0</td>
      <td>NaN</td>
      <td>24498430.0</td>
      <td>0.158478</td>
      <td>2504429.0</td>
      <td>1.368459e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1072</th>
      <td>774171</td>
      <td>360091</td>
      <td>MEDINA HOSPITAL</td>
      <td>1000 E. WASHINGTON STREET</td>
      <td>MEDINA</td>
      <td>OH</td>
      <td>44256-</td>
      <td>MEDINA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>724.89</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9657.0</td>
      <td>304.0</td>
      <td>33651.0</td>
      <td>148.0</td>
      <td>54020.0</td>
      <td>NaN</td>
      <td>2178.0</td>
      <td>66.0</td>
      <td>7764.0</td>
      <td>148.0</td>
      <td>NaN</td>
      <td>8790.0</td>
      <td>246.0</td>
      <td>30521.0</td>
      <td>136.0</td>
      <td>49640.0</td>
      <td>NaN</td>
      <td>2178.0</td>
      <td>66.0</td>
      <td>7764.0</td>
      <td>3315241.0</td>
      <td>4945504.0</td>
      <td>4447134.0</td>
      <td>10292294.0</td>
      <td>62399059.0</td>
      <td>1.020755e+08</td>
      <td>8765794.0</td>
      <td>1.459961e+08</td>
      <td>2.700763e+08</td>
      <td>3.988384e+08</td>
      <td>6.689147e+08</td>
      <td>14818214.0</td>
      <td>470095.0</td>
      <td>62399059.0</td>
      <td>178769.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1186251.0</td>
      <td>15856930.0</td>
      <td>NaN</td>
      <td>31825503.0</td>
      <td>-8732284.0</td>
      <td>3800471.0</td>
      <td>192896.0</td>
      <td>NaN</td>
      <td>45236434.0</td>
      <td>1225994.0</td>
      <td>3022719.0</td>
      <td>1.403456e+08</td>
      <td>NaN</td>
      <td>1204751.0</td>
      <td>30621442.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.032573e+07</td>
      <td>1.753343e+08</td>
      <td>932868.0</td>
      <td>1.762671e+08</td>
      <td>2.818293e+08</td>
      <td>4444238.0</td>
      <td>5664249.0</td>
      <td>138407.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2117910.0</td>
      <td>12364804.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.944760e+05</td>
      <td>2.944760e+05</td>
      <td>1.265928e+07</td>
      <td>2.691700e+08</td>
      <td>2.691700e+08</td>
      <td>2.818293e+08</td>
      <td>NaN</td>
      <td>13574247.0</td>
      <td>5042413.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.700763e+08</td>
      <td>3.988384e+08</td>
      <td>6.689147e+08</td>
      <td>4.857001e+08</td>
      <td>1.832147e+08</td>
      <td>1.644745e+08</td>
      <td>18740119.0</td>
      <td>18683312.0</td>
      <td>37423431.0</td>
      <td>NaN</td>
      <td>37423431.0</td>
      <td>0.218258</td>
      <td>9212941.0</td>
      <td>6.387463e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>5862</th>
      <td>803874</td>
      <td>360077</td>
      <td>FAIRVIEW HOSPITAL</td>
      <td>18101 LORAIN AVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44111-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>2421.00</td>
      <td>80.0</td>
      <td>NaN</td>
      <td>21348.0</td>
      <td>6859.0</td>
      <td>122041.0</td>
      <td>466.0</td>
      <td>170090.0</td>
      <td>NaN</td>
      <td>4400.0</td>
      <td>401.0</td>
      <td>25124.0</td>
      <td>466.0</td>
      <td>NaN</td>
      <td>18091.0</td>
      <td>5310.0</td>
      <td>84810.0</td>
      <td>376.0</td>
      <td>137240.0</td>
      <td>NaN</td>
      <td>4400.0</td>
      <td>401.0</td>
      <td>25124.0</td>
      <td>11522919.0</td>
      <td>13926609.0</td>
      <td>14791492.0</td>
      <td>31185546.0</td>
      <td>202255263.0</td>
      <td>3.496126e+08</td>
      <td>20823064.0</td>
      <td>5.016847e+08</td>
      <td>1.093822e+09</td>
      <td>1.171575e+09</td>
      <td>2.265396e+09</td>
      <td>49903087.0</td>
      <td>NaN</td>
      <td>202255263.0</td>
      <td>18263738.0</td>
      <td>7784.0</td>
      <td>938801.0</td>
      <td>4995647.0</td>
      <td>62939122.0</td>
      <td>NaN</td>
      <td>107257170.0</td>
      <td>-32543024.0</td>
      <td>14131157.0</td>
      <td>544859.0</td>
      <td>NaN</td>
      <td>177035687.0</td>
      <td>2525153.0</td>
      <td>8692729.0</td>
      <td>3.008051e+08</td>
      <td>2359410.0</td>
      <td>7866114.0</td>
      <td>99709100.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.332000e+08</td>
      <td>2.570368e+09</td>
      <td>3184457.0</td>
      <td>2.573552e+09</td>
      <td>2.883788e+09</td>
      <td>14615894.0</td>
      <td>18452497.0</td>
      <td>447045.0</td>
      <td>14247049.0</td>
      <td>NaN</td>
      <td>13749118.0</td>
      <td>61511603.0</td>
      <td>NaN</td>
      <td>7.373888e+07</td>
      <td>NaN</td>
      <td>7.535950e+05</td>
      <td>7.449248e+07</td>
      <td>1.360041e+08</td>
      <td>2.747784e+09</td>
      <td>2.747784e+09</td>
      <td>2.883788e+09</td>
      <td>NaN</td>
      <td>34674889.0</td>
      <td>11462474.0</td>
      <td>NaN</td>
      <td>1912394.0</td>
      <td>0.0000</td>
      <td>67998993.0</td>
      <td>3209453.0</td>
      <td>1.105629e+09</td>
      <td>1.180188e+09</td>
      <td>2.285817e+09</td>
      <td>1.614905e+09</td>
      <td>6.709122e+08</td>
      <td>5.518678e+08</td>
      <td>119044353.0</td>
      <td>190097143.0</td>
      <td>309141496.0</td>
      <td>NaN</td>
      <td>309141496.0</td>
      <td>0.000000</td>
      <td>67817475.0</td>
      <td>4.180697e+08</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5868</th>
      <td>804003</td>
      <td>360143</td>
      <td>MARYMOUNT HOSPITAL</td>
      <td>12300 MCCRACKEN ROAD</td>
      <td>GARFIELD HTS.</td>
      <td>OH</td>
      <td>44125-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>743.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7617.0</td>
      <td>1004.0</td>
      <td>32016.0</td>
      <td>188.0</td>
      <td>68620.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>262.0</td>
      <td>NaN</td>
      <td>6670.0</td>
      <td>864.0</td>
      <td>28081.0</td>
      <td>160.0</td>
      <td>58400.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>4960258.0</td>
      <td>6005537.0</td>
      <td>6610489.0</td>
      <td>20288869.0</td>
      <td>68760998.0</td>
      <td>1.288689e+08</td>
      <td>13004822.0</td>
      <td>1.861900e+08</td>
      <td>2.915091e+08</td>
      <td>4.133701e+08</td>
      <td>7.048792e+08</td>
      <td>15485875.0</td>
      <td>NaN</td>
      <td>68760998.0</td>
      <td>10372586.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3327.0</td>
      <td>8750189.0</td>
      <td>NaN</td>
      <td>35798654.0</td>
      <td>-12021126.0</td>
      <td>5908241.0</td>
      <td>187265.0</td>
      <td>NaN</td>
      <td>40704523.0</td>
      <td>2156995.0</td>
      <td>9811905.0</td>
      <td>1.891104e+08</td>
      <td>2497691.0</td>
      <td>604085.0</td>
      <td>47685000.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9.535494e+07</td>
      <td>3.978384e+07</td>
      <td>3642514.0</td>
      <td>4.342636e+07</td>
      <td>1.794858e+08</td>
      <td>8567580.0</td>
      <td>6329099.0</td>
      <td>160114.0</td>
      <td>11316159.0</td>
      <td>NaN</td>
      <td>1607638.0</td>
      <td>27980590.0</td>
      <td>NaN</td>
      <td>3.013659e+07</td>
      <td>NaN</td>
      <td>-2.380000e+04</td>
      <td>3.011279e+07</td>
      <td>5.809338e+07</td>
      <td>1.213924e+08</td>
      <td>1.213924e+08</td>
      <td>1.794858e+08</td>
      <td>NaN</td>
      <td>9998352.0</td>
      <td>3597148.0</td>
      <td>NaN</td>
      <td>294682.0</td>
      <td>0.0000</td>
      <td>23296909.0</td>
      <td>NaN</td>
      <td>2.919227e+08</td>
      <td>4.143265e+08</td>
      <td>7.062492e+08</td>
      <td>5.214664e+08</td>
      <td>1.847829e+08</td>
      <td>1.976299e+08</td>
      <td>-12847074.0</td>
      <td>13090602.0</td>
      <td>243528.0</td>
      <td>NaN</td>
      <td>243528.0</td>
      <td>0.000000</td>
      <td>23534379.0</td>
      <td>1.543868e+08</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5877</th>
      <td>804173</td>
      <td>360348</td>
      <td>DUBLIN METHODIST HOSPITAL</td>
      <td>7500 HOSPITAL DRIVE</td>
      <td>DUBLIN</td>
      <td>OH</td>
      <td>43016</td>
      <td>FRANKLIN</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>07/01/2023</td>
      <td>06/30/2024</td>
      <td>859.00</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1840.0</td>
      <td>31253.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>110.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1544.0</td>
      <td>26218.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>8662644.0</td>
      <td>6529247.0</td>
      <td>9971937.0</td>
      <td>18212017.0</td>
      <td>90872508.0</td>
      <td>1.670756e+08</td>
      <td>3714520.0</td>
      <td>2.098559e+08</td>
      <td>3.923512e+08</td>
      <td>6.831627e+08</td>
      <td>1.075514e+09</td>
      <td>18520085.0</td>
      <td>NaN</td>
      <td>90076936.0</td>
      <td>6895971.0</td>
      <td>NaN</td>
      <td>284692.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>213365159.0</td>
      <td>-158441459.0</td>
      <td>4583939.0</td>
      <td>NaN</td>
      <td>1826117.0</td>
      <td>62663175.0</td>
      <td>12002054.0</td>
      <td>4304133.0</td>
      <td>1.064236e+08</td>
      <td>NaN</td>
      <td>57315630.0</td>
      <td>36133457.0</td>
      <td>5318246.0</td>
      <td>NaN</td>
      <td>9.830465e+07</td>
      <td>NaN</td>
      <td>5493960.0</td>
      <td>5.493960e+06</td>
      <td>1.664618e+08</td>
      <td>7361901.0</td>
      <td>7402489.0</td>
      <td>NaN</td>
      <td>22046460.0</td>
      <td>NaN</td>
      <td>15200134.0</td>
      <td>52010984.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.901896e+08</td>
      <td>1.901896e+08</td>
      <td>2.422006e+08</td>
      <td>-7.573878e+07</td>
      <td>-7.573878e+07</td>
      <td>1.664618e+08</td>
      <td>NaN</td>
      <td>3886533.0</td>
      <td>13695949.0</td>
      <td>NaN</td>
      <td>208793.0</td>
      <td>0.0000</td>
      <td>18207187.0</td>
      <td>1329710.0</td>
      <td>3.923885e+08</td>
      <td>6.831627e+08</td>
      <td>1.075551e+09</td>
      <td>7.004998e+08</td>
      <td>3.750514e+08</td>
      <td>2.579481e+08</td>
      <td>117103275.0</td>
      <td>3609144.0</td>
      <td>120712419.0</td>
      <td>NaN</td>
      <td>120712419.0</td>
      <td>0.000000</td>
      <td>9424320.0</td>
      <td>9.308563e+07</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6015</th>
      <td>806349</td>
      <td>360144</td>
      <td>SOUTH POINTE HOSPITAL</td>
      <td>4110 WARRENSVILLE CENTER ROAD</td>
      <td>WARRENSVILLE HEIGHTS</td>
      <td>OH</td>
      <td>44122-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>681.00</td>
      <td>32.0</td>
      <td>NaN</td>
      <td>7495.0</td>
      <td>1723.0</td>
      <td>30896.0</td>
      <td>138.0</td>
      <td>51424.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>138.0</td>
      <td>NaN</td>
      <td>6763.0</td>
      <td>1146.0</td>
      <td>22962.0</td>
      <td>96.0</td>
      <td>36094.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>3404647.0</td>
      <td>5056528.0</td>
      <td>4612672.0</td>
      <td>9297780.0</td>
      <td>57312306.0</td>
      <td>9.714770e+07</td>
      <td>9197783.0</td>
      <td>1.297566e+08</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>12323638.0</td>
      <td>NaN</td>
      <td>59365336.0</td>
      <td>13294493.0</td>
      <td>20052.0</td>
      <td>1077300.0</td>
      <td>2041.0</td>
      <td>-110582469.0</td>
      <td>NaN</td>
      <td>25837032.0</td>
      <td>-10247255.0</td>
      <td>4513176.0</td>
      <td>180759.0</td>
      <td>NaN</td>
      <td>-88970100.0</td>
      <td>4703177.0</td>
      <td>8196400.0</td>
      <td>1.427239e+08</td>
      <td>24966.0</td>
      <td>2244703.0</td>
      <td>29978152.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.180659e+07</td>
      <td>NaN</td>
      <td>4059481.0</td>
      <td>4.059481e+06</td>
      <td>-2.310403e+07</td>
      <td>5085976.0</td>
      <td>3691350.0</td>
      <td>NaN</td>
      <td>5419373.0</td>
      <td>NaN</td>
      <td>969652.0</td>
      <td>15166351.0</td>
      <td>NaN</td>
      <td>1.737651e+07</td>
      <td>NaN</td>
      <td>1.936435e+06</td>
      <td>1.931295e+07</td>
      <td>3.447930e+07</td>
      <td>-5.758333e+07</td>
      <td>-5.758333e+07</td>
      <td>-2.310403e+07</td>
      <td>NaN</td>
      <td>9785083.0</td>
      <td>3206009.0</td>
      <td>NaN</td>
      <td>347512.0</td>
      <td>0.0000</td>
      <td>21935652.0</td>
      <td>1393594.0</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>4.463686e+08</td>
      <td>1.428610e+08</td>
      <td>1.544600e+08</td>
      <td>-11598964.0</td>
      <td>3247968.0</td>
      <td>-8350996.0</td>
      <td>NaN</td>
      <td>-8350996.0</td>
      <td>0.000000</td>
      <td>21682032.0</td>
      <td>1.265699e+08</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6085</th>
      <td>807149</td>
      <td>360059</td>
      <td>METROHEALTH MEDICAL CENTER</td>
      <td>2500 METROHEALTH DRIVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44109</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>13</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>7711.00</td>
      <td>400.0</td>
      <td>NaN</td>
      <td>13400.0</td>
      <td>7587.0</td>
      <td>113599.0</td>
      <td>501.0</td>
      <td>182865.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>670.0</td>
      <td>NaN</td>
      <td>11346.0</td>
      <td>5024.0</td>
      <td>82749.0</td>
      <td>398.0</td>
      <td>145270.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>52249491.0</td>
      <td>41241147.0</td>
      <td>64768232.0</td>
      <td>172613758.0</td>
      <td>815495894.0</td>
      <td>1.022078e+09</td>
      <td>122305389.0</td>
      <td>1.144066e+09</td>
      <td>1.305561e+09</td>
      <td>2.477536e+09</td>
      <td>3.783097e+09</td>
      <td>151234382.0</td>
      <td>NaN</td>
      <td>815495894.0</td>
      <td>4095473.0</td>
      <td>2234972.0</td>
      <td>6887728.0</td>
      <td>167167876.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>181964719.0</td>
      <td>-32420355.0</td>
      <td>28286678.0</td>
      <td>18745013.0</td>
      <td>NaN</td>
      <td>451274662.0</td>
      <td>274381921.0</td>
      <td>25832250.0</td>
      <td>1.035162e+09</td>
      <td>17809023.0</td>
      <td>398974483.0</td>
      <td>259449588.0</td>
      <td>2564590.0</td>
      <td>NaN</td>
      <td>1.234442e+09</td>
      <td>5.369092e+08</td>
      <td>734717506.0</td>
      <td>1.271627e+09</td>
      <td>2.957343e+09</td>
      <td>89655513.0</td>
      <td>122910887.0</td>
      <td>NaN</td>
      <td>24192974.0</td>
      <td>NaN</td>
      <td>32359137.0</td>
      <td>270430031.0</td>
      <td>NaN</td>
      <td>1.090432e+09</td>
      <td>NaN</td>
      <td>1.183095e+09</td>
      <td>2.273527e+09</td>
      <td>2.543957e+09</td>
      <td>4.133858e+08</td>
      <td>4.133858e+08</td>
      <td>2.957343e+09</td>
      <td>NaN</td>
      <td>19277875.0</td>
      <td>6847645.0</td>
      <td>NaN</td>
      <td>2427061.0</td>
      <td>0.0000</td>
      <td>57246922.0</td>
      <td>7608953.0</td>
      <td>1.512498e+09</td>
      <td>3.187045e+09</td>
      <td>4.699543e+09</td>
      <td>3.424704e+09</td>
      <td>1.274839e+09</td>
      <td>1.842426e+09</td>
      <td>-567586421.0</td>
      <td>598744604.0</td>
      <td>31158183.0</td>
      <td>NaN</td>
      <td>31158183.0</td>
      <td>0.000000</td>
      <td>276594217.0</td>
      <td>1.271232e+09</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>68 rows × 117 columns</p>
</div>



```python
cms_ccr_oh_u['Cost To Charge Ratio'].mean()

cms_ccr_oh_u["Cost To Charge Ratio"].describe()
```




    count    68.000000
    mean      0.225346
    std       0.167976
    min       0.000000
    25%       0.159138
    50%       0.208326
    75%       0.258645
    max       1.075599
    Name: Cost To Charge Ratio, dtype: float64




```python
# LOAD CMS WAGE INDEX (CMS-1771-F)

wage_index2023 = pd.read_excel('/Users/abdulrahmanalali/Desktop/GitHub Projects/CMS Project/CMS-1771-F Tables 2, 3, 4A, 4B/CMS-1771-F Tables 2, 3, 4A, 4B.xlsx',
                              sheet_name = 0)

display(wage_index2023)
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CCN</th>
      <th>2Case-Mix Indexes for  Discharges Occurring in Federal Fiscal Year 2021</th>
      <th>FY 2022 Wage Index</th>
      <th>8FY 2022 Wage Index Differs from FY 2022 CN Table 2</th>
      <th>6FY 2023 Wage Index Prior to Quartile and Cap</th>
      <th>6FY 2023 Wage Index With Quartile</th>
      <th>FY 2023 Wage Index With Quartile and Cap</th>
      <th>4Average Hourly Wage FY 2021</th>
      <th>4Average Hourly Wage FY 2022</th>
      <th>4Average Hourly Wage FY 2023</th>
      <th>43-Year Average Hourly Wage (2021, 2022, 2023)</th>
      <th>Geographic CBSA</th>
      <th>7Wage Index Payment CBSA</th>
      <th>Lugar/ NECMA</th>
      <th>MGCRB Reclass</th>
      <th>Rural CBSA if Hospital is Reclassified Under Section 1886(d)(8)(E)of the Act (412.103)</th>
      <th>5Out-Migration Adjustment</th>
      <th>County Name</th>
      <th>FIPS County Code</th>
      <th>Dual Status 412.103 and MGCRB/ LUGAR</th>
      <th>MGCRB Reclass to Home</th>
      <th>Hospitals that Waive LUGAR to Receive Out-Migration Adjustment</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>010001</td>
      <td>2.0375</td>
      <td>0.8560</td>
      <td>NaN</td>
      <td>0.7999</td>
      <td>0.8213</td>
      <td>0.8213</td>
      <td>31.7841</td>
      <td>33.2423</td>
      <td>34.0614</td>
      <td>33.0435</td>
      <td>20020</td>
      <td>18880.0</td>
      <td>NaN</td>
      <td>18880.0</td>
      <td>1.0</td>
      <td>NaN</td>
      <td>HOUSTON</td>
      <td>1069</td>
      <td>Y</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>010005</td>
      <td>1.6854</td>
      <td>0.8070</td>
      <td>NaN</td>
      <td>0.7606</td>
      <td>0.8017</td>
      <td>0.8017</td>
      <td>29.6853</td>
      <td>29.3854</td>
      <td>28.8232</td>
      <td>29.2886</td>
      <td>1</td>
      <td>13820.0</td>
      <td>NaN</td>
      <td>13820.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>MARSHALL</td>
      <td>1095</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>010006</td>
      <td>1.9148</td>
      <td>0.8113</td>
      <td>NaN</td>
      <td>0.7382</td>
      <td>0.7905</td>
      <td>0.7905</td>
      <td>28.6196</td>
      <td>29.5675</td>
      <td>30.6347</td>
      <td>29.6118</td>
      <td>22520</td>
      <td>25.0</td>
      <td>NaN</td>
      <td>25.0</td>
      <td>1.0</td>
      <td>NaN</td>
      <td>LAUDERDALE</td>
      <td>1077</td>
      <td>Y</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>010007</td>
      <td>1.5171</td>
      <td>0.7461</td>
      <td>NaN</td>
      <td>0.6551</td>
      <td>0.7489</td>
      <td>0.7489</td>
      <td>25.2267</td>
      <td>26.7966</td>
      <td>29.2463</td>
      <td>27.0504</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>COVINGTON</td>
      <td>1039</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>010008</td>
      <td>1.1914</td>
      <td>0.7461</td>
      <td>NaN</td>
      <td>0.6551</td>
      <td>0.7489</td>
      <td>0.7489</td>
      <td>25.2532</td>
      <td>25.0009</td>
      <td>26.6746</td>
      <td>25.6347</td>
      <td>1</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>CRENSHAW</td>
      <td>1041</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3391</th>
      <td>670300</td>
      <td>1.5795</td>
      <td>0.9552</td>
      <td>NaN</td>
      <td>0.9528</td>
      <td>0.9528</td>
      <td>0.9528</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>19124</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>ELLIS</td>
      <td>48139</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3392</th>
      <td>670309</td>
      <td>1.6487</td>
      <td>0.9587</td>
      <td>NaN</td>
      <td>0.9555</td>
      <td>0.9555</td>
      <td>0.9555</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>23104</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>JOHNSON</td>
      <td>48251</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3393</th>
      <td>670310</td>
      <td>1.0710</td>
      <td>0.9873</td>
      <td>NaN</td>
      <td>0.9925</td>
      <td>0.9925</td>
      <td>0.9925</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>26420</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>HARRIS</td>
      <td>48201</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3394</th>
      <td>67B062</td>
      <td>NaN</td>
      <td>0.9552</td>
      <td>NaN</td>
      <td>0.9562</td>
      <td>0.9562</td>
      <td>0.9562</td>
      <td>36.7879</td>
      <td>42.2232</td>
      <td>39.5678</td>
      <td>39.5170</td>
      <td>23104</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.0007</td>
      <td>TARRANT</td>
      <td>48439</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3395</th>
      <td>67B107</td>
      <td>NaN</td>
      <td>0.9552</td>
      <td>NaN</td>
      <td>0.9528</td>
      <td>0.9528</td>
      <td>0.9528</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>40.3478</td>
      <td>40.3478</td>
      <td>19124</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>DALLAS</td>
      <td>48113</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>3396 rows × 22 columns</p>
</div>



```python
# STANDARDIZE CCN + CLEAN COLUMN NAMES
# Make CCN a clean 6-digit string (leading zeros preserved)

wage_index2023['CCN'] = wage_index2023['CCN'].astype(str).str.zfill(6)
cms_ccr_oh_u['Provider CCN'] = cms_ccr_oh_u['Provider CCN'].astype(str).str.zfill(6)
```


```python
# Clean weird hidden spaces in column names (Excel sometimes has these)
wage_index2023.columns = (
    wage_index2023.columns
    .str.replace("\xa0", " ", regex=False)   # remove non-breaking spaces
    .str.strip()                              # remove leading/trailing spaces
)

# Quick check
wage_index2023.columns
```




    Index(['CCN',
           '2Case-Mix Indexes for  Discharges Occurring in Federal Fiscal Year 2021',
           'FY 2022 Wage Index',
           '8FY 2022 Wage Index Differs from FY 2022 CN Table 2',
           '6FY 2023 Wage Index Prior to Quartile and Cap',
           '6FY 2023 Wage Index With Quartile',
           'FY 2023 Wage Index With Quartile and Cap',
           '4Average Hourly Wage FY 2021', '4Average Hourly Wage FY 2022',
           '4Average Hourly Wage FY 2023',
           '43-Year Average Hourly Wage (2021, 2022, 2023)', 'Geographic CBSA',
           '7Wage Index Payment CBSA', 'Lugar/ NECMA', 'MGCRB Reclass',
           'Rural CBSA if Hospital is Reclassified Under Section 1886(d)(8)(E)of the Act (412.103)',
           '5Out-Migration Adjustment', 'County Name', 'FIPS County Code',
           'Dual Status 412.103 and MGCRB/ LUGAR', 'MGCRB Reclass to Home',
           'Hospitals that Waive LUGAR to Receive Out-Migration Adjustment'],
          dtype='object')




```python
# CREATE WAGE INDEX LOOKUP TABLE (CCN → WAGE INDEX 2023)

wage_index2023s = wage_index2023[['CCN','FY 2023 Wage Index With Quartile and Cap']].copy()
wage_index2023s = wage_index2023s.rename(columns={'FY 2023 Wage Index With Quartile and Cap' : 'Wage Index 2023'})

display(wage_index2023s)
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>CCN</th>
      <th>Wage Index 2023</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>010001</td>
      <td>0.8213</td>
    </tr>
    <tr>
      <th>1</th>
      <td>010005</td>
      <td>0.8017</td>
    </tr>
    <tr>
      <th>2</th>
      <td>010006</td>
      <td>0.7905</td>
    </tr>
    <tr>
      <th>3</th>
      <td>010007</td>
      <td>0.7489</td>
    </tr>
    <tr>
      <th>4</th>
      <td>010008</td>
      <td>0.7489</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3391</th>
      <td>670300</td>
      <td>0.9528</td>
    </tr>
    <tr>
      <th>3392</th>
      <td>670309</td>
      <td>0.9555</td>
    </tr>
    <tr>
      <th>3393</th>
      <td>670310</td>
      <td>0.9925</td>
    </tr>
    <tr>
      <th>3394</th>
      <td>67B062</td>
      <td>0.9562</td>
    </tr>
    <tr>
      <th>3395</th>
      <td>67B107</td>
      <td>0.9528</td>
    </tr>
  </tbody>
</table>
<p>3396 rows × 2 columns</p>
</div>



```python
# Merge wage index into the cost report table

cms_ccr_oh_u_ccn = cms_ccr_oh_u.merge(
    wage_index2023s,
    left_on="Provider CCN",
    right_on="CCN",
    how="left"
)

display(cms_ccr_oh_u_ccn)
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rpt_rec_num</th>
      <th>Provider CCN</th>
      <th>Hospital Name</th>
      <th>Street Address</th>
      <th>City</th>
      <th>State Code</th>
      <th>Zip Code</th>
      <th>County</th>
      <th>Medicare CBSA Number</th>
      <th>Rural Versus Urban</th>
      <th>CCN Facility Type</th>
      <th>Provider Type</th>
      <th>Type of Control</th>
      <th>Fiscal Year Begin Date</th>
      <th>Fiscal Year End Date</th>
      <th>FTE - Employees on Payroll</th>
      <th>Number of Interns and Residents (FTE)</th>
      <th>Total Days Title V</th>
      <th>Total Days Title XVIII</th>
      <th>Total Days Title XIX</th>
      <th>Total Days (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds</th>
      <th>Total Bed Days Available</th>
      <th>Total Discharges Title V</th>
      <th>Total Discharges Title XVIII</th>
      <th>Total Discharges Title XIX</th>
      <th>Total Discharges (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds + Total for all Subproviders</th>
      <th>Hospital Total Days Title V For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Days (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Hospital Number of Beds For Adults &amp; Peds</th>
      <th>Hospital Total Bed Days Available For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title V For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Discharges (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Cost of Charity Care</th>
      <th>Total Bad Debt Expense</th>
      <th>Cost of Uncompensated Care</th>
      <th>Total Unreimbursed and Uncompensated Care</th>
      <th>Total Salaries From Worksheet A</th>
      <th>Overhead Non-Salary Costs</th>
      <th>Depreciation Cost</th>
      <th>Total Costs</th>
      <th>Inpatient Total Charges</th>
      <th>Outpatient Total Charges</th>
      <th>Combined Outpatient + Inpatient Total Charges</th>
      <th>Wage-Related Costs (Core)</th>
      <th>Wage-Related Costs (RHC/FQHC)</th>
      <th>Total Salaries (adjusted)</th>
      <th>Contract Labor: Direct Patient Care</th>
      <th>Wage Related Costs for Part - A Teaching Physicians</th>
      <th>Wage Related Costs for Interns and Residents</th>
      <th>Cash on Hand and in Banks</th>
      <th>Temporary Investments</th>
      <th>Notes Receivable</th>
      <th>Accounts Receivable</th>
      <th>Less: Allowances for Uncollectible Notes and Accounts Receivable</th>
      <th>Inventory</th>
      <th>Prepaid Expenses</th>
      <th>Other Current Assets</th>
      <th>Total Current Assets</th>
      <th>Land</th>
      <th>Land Improvements</th>
      <th>Buildings</th>
      <th>Leasehold Improvements</th>
      <th>Fixed Equipment</th>
      <th>Major Movable Equipment</th>
      <th>Minor Equipment Depreciable</th>
      <th>Health Information Technology Designated Assets</th>
      <th>Total Fixed Assets</th>
      <th>Investments</th>
      <th>Other Assets</th>
      <th>Total Other Assets</th>
      <th>Total Assets</th>
      <th>Accounts Payable</th>
      <th>Salaries, Wages, and Fees Payable</th>
      <th>Payroll Taxes Payable</th>
      <th>Notes and Loans Payable (Short Term)</th>
      <th>Deferred Income</th>
      <th>Other Current Liabilities</th>
      <th>Total Current Liabilities</th>
      <th>Mortgage Payable</th>
      <th>Notes Payable</th>
      <th>Unsecured Loans</th>
      <th>Other Long Term Liabilities</th>
      <th>Total Long Term Liabilities</th>
      <th>Total Liabilities</th>
      <th>General Fund Balance</th>
      <th>Total Fund Balances</th>
      <th>Total Liabilities and Fund Balances</th>
      <th>DRG Amounts Other Than Outlier Payments</th>
      <th>DRG Amounts Before October 1</th>
      <th>DRG Amounts After October 1</th>
      <th>Outlier Payments For Discharges</th>
      <th>Disproportionate Share Adjustment</th>
      <th>Allowable DSH Percentage</th>
      <th>Managed Care Simulated Payments</th>
      <th>Total IME Payment</th>
      <th>Inpatient Revenue</th>
      <th>Outpatient Revenue</th>
      <th>Total Patient Revenue</th>
      <th>Less Contractual Allowance and Discounts on Patients' Accounts</th>
      <th>Net Patient Revenue</th>
      <th>Less Total Operating Expense</th>
      <th>Net Income from Service to Patients</th>
      <th>Total Other Income</th>
      <th>Total Income</th>
      <th>Total Other Expenses</th>
      <th>Net Income</th>
      <th>Cost To Charge Ratio</th>
      <th>Net Revenue from Medicaid</th>
      <th>Medicaid Charges</th>
      <th>Net Revenue from Stand-Alone CHIP</th>
      <th>Stand-Alone CHIP Charges</th>
      <th>CCN</th>
      <th>Wage Index 2023</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>772302</td>
      <td>360189</td>
      <td>MADISON HEALTH</td>
      <td>210 NORTH MAIN STREET</td>
      <td>LONDON</td>
      <td>OH</td>
      <td>43140-</td>
      <td>MADISON</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>240.91</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>837.0</td>
      <td>41.0</td>
      <td>3398.0</td>
      <td>45.0</td>
      <td>16425.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>45.0</td>
      <td>NaN</td>
      <td>464.0</td>
      <td>28.0</td>
      <td>1990.0</td>
      <td>32.0</td>
      <td>11680.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>496204.0</td>
      <td>5407503.0</td>
      <td>1741928.0</td>
      <td>5319204.0</td>
      <td>18010729.0</td>
      <td>3.367992e+07</td>
      <td>5293848.0</td>
      <td>4.602876e+07</td>
      <td>2.958593e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>5182408.0</td>
      <td>NaN</td>
      <td>18010729.0</td>
      <td>1154149.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2664688.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7969832.0</td>
      <td>NaN</td>
      <td>1161089.0</td>
      <td>1543583.0</td>
      <td>NaN</td>
      <td>16694600.0</td>
      <td>2058728.0</td>
      <td>1432397.0</td>
      <td>4.912698e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>28774601.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.575774e+07</td>
      <td>3.707201e+07</td>
      <td>3870344.0</td>
      <td>4.094236e+07</td>
      <td>9.339470e+07</td>
      <td>2216194.0</td>
      <td>3060674.0</td>
      <td>NaN</td>
      <td>1620663.0</td>
      <td>NaN</td>
      <td>1974927.0</td>
      <td>8872458.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.599493e+07</td>
      <td>3.599493e+07</td>
      <td>4.486739e+07</td>
      <td>4.852731e+07</td>
      <td>4.852731e+07</td>
      <td>9.339470e+07</td>
      <td>NaN</td>
      <td>1399457.0</td>
      <td>380850.0</td>
      <td>NaN</td>
      <td>53410.0</td>
      <td>0.1200</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.958594e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>1.413727e+08</td>
      <td>6.025978e+07</td>
      <td>5.101758e+07</td>
      <td>9242202.0</td>
      <td>-2053858.0</td>
      <td>7188344.0</td>
      <td>-680.0</td>
      <td>7189024.0</td>
      <td>0.228281</td>
      <td>4628233.0</td>
      <td>3.594478e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360189</td>
      <td>0.9346</td>
    </tr>
    <tr>
      <th>1</th>
      <td>772303</td>
      <td>360351</td>
      <td>CRYSTAL CLINIC ORTHOPAEDIC CENTER</td>
      <td>444 N. MAIN STREET</td>
      <td>AKRON</td>
      <td>OH</td>
      <td>44310</td>
      <td>SUMMIT</td>
      <td>10420.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>4</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>829.28</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>59.0</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>NaN</td>
      <td>4966858.0</td>
      <td>1025756.0</td>
      <td>4491088.0</td>
      <td>59842683.0</td>
      <td>1.410437e+08</td>
      <td>19791461.0</td>
      <td>1.757999e+08</td>
      <td>1.723140e+08</td>
      <td>6.789364e+08</td>
      <td>8.512503e+08</td>
      <td>16227538.0</td>
      <td>NaN</td>
      <td>59842683.0</td>
      <td>2833456.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20226359.0</td>
      <td>NaN</td>
      <td>91445.0</td>
      <td>143984935.0</td>
      <td>-115969987.0</td>
      <td>4254008.0</td>
      <td>5590825.0</td>
      <td>364672.0</td>
      <td>58542257.0</td>
      <td>1797791.0</td>
      <td>972311.0</td>
      <td>7.353677e+06</td>
      <td>14842928.0</td>
      <td>5829690.0</td>
      <td>40446507.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.777400e+07</td>
      <td>NaN</td>
      <td>116070299.0</td>
      <td>1.160703e+08</td>
      <td>2.123866e+08</td>
      <td>5248828.0</td>
      <td>5287289.0</td>
      <td>NaN</td>
      <td>15147407.0</td>
      <td>NaN</td>
      <td>13317765.0</td>
      <td>39001289.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.039823e+08</td>
      <td>1.039823e+08</td>
      <td>1.429836e+08</td>
      <td>6.940295e+07</td>
      <td>6.940295e+07</td>
      <td>2.123866e+08</td>
      <td>NaN</td>
      <td>8019249.0</td>
      <td>2943604.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.723155e+08</td>
      <td>7.043064e+08</td>
      <td>8.766219e+08</td>
      <td>6.728033e+08</td>
      <td>2.038185e+08</td>
      <td>2.008864e+08</td>
      <td>2932156.0</td>
      <td>4699468.0</td>
      <td>7631624.0</td>
      <td>NaN</td>
      <td>7631624.0</td>
      <td>0.206520</td>
      <td>6048085.0</td>
      <td>4.606535e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360351</td>
      <td>0.8360</td>
    </tr>
    <tr>
      <th>2</th>
      <td>773604</td>
      <td>360092</td>
      <td>MEMORIAL HOSPITAL OF UNION COUNTY</td>
      <td>500 LONDON AVENUE</td>
      <td>MARYSVILLE</td>
      <td>OH</td>
      <td>43040-</td>
      <td>UNION</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>9</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>715.78</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1888.0</td>
      <td>466.0</td>
      <td>8688.0</td>
      <td>51.0</td>
      <td>18615.0</td>
      <td>NaN</td>
      <td>664.0</td>
      <td>55.0</td>
      <td>2719.0</td>
      <td>51.0</td>
      <td>NaN</td>
      <td>1784.0</td>
      <td>83.0</td>
      <td>7310.0</td>
      <td>39.0</td>
      <td>14235.0</td>
      <td>NaN</td>
      <td>664.0</td>
      <td>55.0</td>
      <td>2719.0</td>
      <td>1296612.0</td>
      <td>10184707.0</td>
      <td>4471898.0</td>
      <td>10932284.0</td>
      <td>60532285.0</td>
      <td>1.020931e+08</td>
      <td>9549895.0</td>
      <td>1.336948e+08</td>
      <td>7.755640e+07</td>
      <td>3.522619e+08</td>
      <td>4.298183e+08</td>
      <td>16558853.0</td>
      <td>NaN</td>
      <td>60532285.0</td>
      <td>1694453.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>39553623.0</td>
      <td>13286590.0</td>
      <td>NaN</td>
      <td>21815875.0</td>
      <td>NaN</td>
      <td>1954919.0</td>
      <td>2096449.0</td>
      <td>1011916.0</td>
      <td>85393958.0</td>
      <td>3017141.0</td>
      <td>5246439.0</td>
      <td>1.162705e+08</td>
      <td>NaN</td>
      <td>2737700.0</td>
      <td>87307904.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.282003e+08</td>
      <td>7.960842e+07</td>
      <td>47234308.0</td>
      <td>1.268427e+08</td>
      <td>3.404370e+08</td>
      <td>11247442.0</td>
      <td>12095547.0</td>
      <td>NaN</td>
      <td>28559091.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>52567080.0</td>
      <td>NaN</td>
      <td>6.777074e+07</td>
      <td>NaN</td>
      <td>9.047551e+07</td>
      <td>1.582462e+08</td>
      <td>2.108133e+08</td>
      <td>1.296237e+08</td>
      <td>1.296237e+08</td>
      <td>3.404370e+08</td>
      <td>NaN</td>
      <td>3889441.0</td>
      <td>1652815.0</td>
      <td>NaN</td>
      <td>80086.0</td>
      <td>0.0578</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.770045e+07</td>
      <td>3.680071e+08</td>
      <td>4.457075e+08</td>
      <td>2.731381e+08</td>
      <td>1.725695e+08</td>
      <td>1.755439e+08</td>
      <td>-2974447.0</td>
      <td>12398185.0</td>
      <td>9423738.0</td>
      <td>133399.0</td>
      <td>9290339.0</td>
      <td>0.311050</td>
      <td>7711324.0</td>
      <td>5.137945e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360092</td>
      <td>0.9346</td>
    </tr>
    <tr>
      <th>3</th>
      <td>773606</td>
      <td>360263</td>
      <td>INSTITUTE FOR ORTHOPAEDIC SURGERY</td>
      <td>801 MEDICAL DRIVE</td>
      <td>LIMA</td>
      <td>OH</td>
      <td>45804</td>
      <td>ALLEN</td>
      <td>30620.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>6</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>175.06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>645.0</td>
      <td>18.0</td>
      <td>1230.0</td>
      <td>12.0</td>
      <td>4380.0</td>
      <td>NaN</td>
      <td>284.0</td>
      <td>12.0</td>
      <td>581.0</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>645.0</td>
      <td>18.0</td>
      <td>1230.0</td>
      <td>12.0</td>
      <td>4380.0</td>
      <td>NaN</td>
      <td>284.0</td>
      <td>12.0</td>
      <td>581.0</td>
      <td>NaN</td>
      <td>2620740.0</td>
      <td>419156.0</td>
      <td>683481.0</td>
      <td>11308402.0</td>
      <td>3.003173e+07</td>
      <td>-4154.0</td>
      <td>3.649592e+07</td>
      <td>1.228750e+08</td>
      <td>1.074157e+08</td>
      <td>2.302907e+08</td>
      <td>3573493.0</td>
      <td>NaN</td>
      <td>11308402.0</td>
      <td>103036.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1164259.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9391865.0</td>
      <td>-1858489.0</td>
      <td>1443630.0</td>
      <td>284126.0</td>
      <td>NaN</td>
      <td>10425391.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>104120.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.042539e+07</td>
      <td>2730598.0</td>
      <td>492461.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>330076.0</td>
      <td>3553135.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.500000e+05</td>
      <td>2.500000e+05</td>
      <td>3.803135e+06</td>
      <td>6.622256e+06</td>
      <td>6.622256e+06</td>
      <td>1.042539e+07</td>
      <td>NaN</td>
      <td>2949645.0</td>
      <td>983215.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.228750e+08</td>
      <td>1.074157e+08</td>
      <td>2.302907e+08</td>
      <td>1.676803e+08</td>
      <td>6.261041e+07</td>
      <td>4.134013e+07</td>
      <td>21270276.0</td>
      <td>3228154.0</td>
      <td>24498430.0</td>
      <td>NaN</td>
      <td>24498430.0</td>
      <td>0.158478</td>
      <td>2504429.0</td>
      <td>1.368459e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360263</td>
      <td>0.8371</td>
    </tr>
    <tr>
      <th>4</th>
      <td>774171</td>
      <td>360091</td>
      <td>MEDINA HOSPITAL</td>
      <td>1000 E. WASHINGTON STREET</td>
      <td>MEDINA</td>
      <td>OH</td>
      <td>44256-</td>
      <td>MEDINA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>724.89</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9657.0</td>
      <td>304.0</td>
      <td>33651.0</td>
      <td>148.0</td>
      <td>54020.0</td>
      <td>NaN</td>
      <td>2178.0</td>
      <td>66.0</td>
      <td>7764.0</td>
      <td>148.0</td>
      <td>NaN</td>
      <td>8790.0</td>
      <td>246.0</td>
      <td>30521.0</td>
      <td>136.0</td>
      <td>49640.0</td>
      <td>NaN</td>
      <td>2178.0</td>
      <td>66.0</td>
      <td>7764.0</td>
      <td>3315241.0</td>
      <td>4945504.0</td>
      <td>4447134.0</td>
      <td>10292294.0</td>
      <td>62399059.0</td>
      <td>1.020755e+08</td>
      <td>8765794.0</td>
      <td>1.459961e+08</td>
      <td>2.700763e+08</td>
      <td>3.988384e+08</td>
      <td>6.689147e+08</td>
      <td>14818214.0</td>
      <td>470095.0</td>
      <td>62399059.0</td>
      <td>178769.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1186251.0</td>
      <td>15856930.0</td>
      <td>NaN</td>
      <td>31825503.0</td>
      <td>-8732284.0</td>
      <td>3800471.0</td>
      <td>192896.0</td>
      <td>NaN</td>
      <td>45236434.0</td>
      <td>1225994.0</td>
      <td>3022719.0</td>
      <td>1.403456e+08</td>
      <td>NaN</td>
      <td>1204751.0</td>
      <td>30621442.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.032573e+07</td>
      <td>1.753343e+08</td>
      <td>932868.0</td>
      <td>1.762671e+08</td>
      <td>2.818293e+08</td>
      <td>4444238.0</td>
      <td>5664249.0</td>
      <td>138407.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2117910.0</td>
      <td>12364804.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.944760e+05</td>
      <td>2.944760e+05</td>
      <td>1.265928e+07</td>
      <td>2.691700e+08</td>
      <td>2.691700e+08</td>
      <td>2.818293e+08</td>
      <td>NaN</td>
      <td>13574247.0</td>
      <td>5042413.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.700763e+08</td>
      <td>3.988384e+08</td>
      <td>6.689147e+08</td>
      <td>4.857001e+08</td>
      <td>1.832147e+08</td>
      <td>1.644745e+08</td>
      <td>18740119.0</td>
      <td>18683312.0</td>
      <td>37423431.0</td>
      <td>NaN</td>
      <td>37423431.0</td>
      <td>0.218258</td>
      <td>9212941.0</td>
      <td>6.387463e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360091</td>
      <td>0.8786</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>63</th>
      <td>803874</td>
      <td>360077</td>
      <td>FAIRVIEW HOSPITAL</td>
      <td>18101 LORAIN AVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44111-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>2421.00</td>
      <td>80.0</td>
      <td>NaN</td>
      <td>21348.0</td>
      <td>6859.0</td>
      <td>122041.0</td>
      <td>466.0</td>
      <td>170090.0</td>
      <td>NaN</td>
      <td>4400.0</td>
      <td>401.0</td>
      <td>25124.0</td>
      <td>466.0</td>
      <td>NaN</td>
      <td>18091.0</td>
      <td>5310.0</td>
      <td>84810.0</td>
      <td>376.0</td>
      <td>137240.0</td>
      <td>NaN</td>
      <td>4400.0</td>
      <td>401.0</td>
      <td>25124.0</td>
      <td>11522919.0</td>
      <td>13926609.0</td>
      <td>14791492.0</td>
      <td>31185546.0</td>
      <td>202255263.0</td>
      <td>3.496126e+08</td>
      <td>20823064.0</td>
      <td>5.016847e+08</td>
      <td>1.093822e+09</td>
      <td>1.171575e+09</td>
      <td>2.265396e+09</td>
      <td>49903087.0</td>
      <td>NaN</td>
      <td>202255263.0</td>
      <td>18263738.0</td>
      <td>7784.0</td>
      <td>938801.0</td>
      <td>4995647.0</td>
      <td>62939122.0</td>
      <td>NaN</td>
      <td>107257170.0</td>
      <td>-32543024.0</td>
      <td>14131157.0</td>
      <td>544859.0</td>
      <td>NaN</td>
      <td>177035687.0</td>
      <td>2525153.0</td>
      <td>8692729.0</td>
      <td>3.008051e+08</td>
      <td>2359410.0</td>
      <td>7866114.0</td>
      <td>99709100.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.332000e+08</td>
      <td>2.570368e+09</td>
      <td>3184457.0</td>
      <td>2.573552e+09</td>
      <td>2.883788e+09</td>
      <td>14615894.0</td>
      <td>18452497.0</td>
      <td>447045.0</td>
      <td>14247049.0</td>
      <td>NaN</td>
      <td>13749118.0</td>
      <td>61511603.0</td>
      <td>NaN</td>
      <td>7.373888e+07</td>
      <td>NaN</td>
      <td>7.535950e+05</td>
      <td>7.449248e+07</td>
      <td>1.360041e+08</td>
      <td>2.747784e+09</td>
      <td>2.747784e+09</td>
      <td>2.883788e+09</td>
      <td>NaN</td>
      <td>34674889.0</td>
      <td>11462474.0</td>
      <td>NaN</td>
      <td>1912394.0</td>
      <td>0.0000</td>
      <td>67998993.0</td>
      <td>3209453.0</td>
      <td>1.105629e+09</td>
      <td>1.180188e+09</td>
      <td>2.285817e+09</td>
      <td>1.614905e+09</td>
      <td>6.709122e+08</td>
      <td>5.518678e+08</td>
      <td>119044353.0</td>
      <td>190097143.0</td>
      <td>309141496.0</td>
      <td>NaN</td>
      <td>309141496.0</td>
      <td>0.000000</td>
      <td>67817475.0</td>
      <td>4.180697e+08</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360077</td>
      <td>0.8786</td>
    </tr>
    <tr>
      <th>64</th>
      <td>804003</td>
      <td>360143</td>
      <td>MARYMOUNT HOSPITAL</td>
      <td>12300 MCCRACKEN ROAD</td>
      <td>GARFIELD HTS.</td>
      <td>OH</td>
      <td>44125-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>743.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7617.0</td>
      <td>1004.0</td>
      <td>32016.0</td>
      <td>188.0</td>
      <td>68620.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>262.0</td>
      <td>NaN</td>
      <td>6670.0</td>
      <td>864.0</td>
      <td>28081.0</td>
      <td>160.0</td>
      <td>58400.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>4960258.0</td>
      <td>6005537.0</td>
      <td>6610489.0</td>
      <td>20288869.0</td>
      <td>68760998.0</td>
      <td>1.288689e+08</td>
      <td>13004822.0</td>
      <td>1.861900e+08</td>
      <td>2.915091e+08</td>
      <td>4.133701e+08</td>
      <td>7.048792e+08</td>
      <td>15485875.0</td>
      <td>NaN</td>
      <td>68760998.0</td>
      <td>10372586.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3327.0</td>
      <td>8750189.0</td>
      <td>NaN</td>
      <td>35798654.0</td>
      <td>-12021126.0</td>
      <td>5908241.0</td>
      <td>187265.0</td>
      <td>NaN</td>
      <td>40704523.0</td>
      <td>2156995.0</td>
      <td>9811905.0</td>
      <td>1.891104e+08</td>
      <td>2497691.0</td>
      <td>604085.0</td>
      <td>47685000.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9.535494e+07</td>
      <td>3.978384e+07</td>
      <td>3642514.0</td>
      <td>4.342636e+07</td>
      <td>1.794858e+08</td>
      <td>8567580.0</td>
      <td>6329099.0</td>
      <td>160114.0</td>
      <td>11316159.0</td>
      <td>NaN</td>
      <td>1607638.0</td>
      <td>27980590.0</td>
      <td>NaN</td>
      <td>3.013659e+07</td>
      <td>NaN</td>
      <td>-2.380000e+04</td>
      <td>3.011279e+07</td>
      <td>5.809338e+07</td>
      <td>1.213924e+08</td>
      <td>1.213924e+08</td>
      <td>1.794858e+08</td>
      <td>NaN</td>
      <td>9998352.0</td>
      <td>3597148.0</td>
      <td>NaN</td>
      <td>294682.0</td>
      <td>0.0000</td>
      <td>23296909.0</td>
      <td>NaN</td>
      <td>2.919227e+08</td>
      <td>4.143265e+08</td>
      <td>7.062492e+08</td>
      <td>5.214664e+08</td>
      <td>1.847829e+08</td>
      <td>1.976299e+08</td>
      <td>-12847074.0</td>
      <td>13090602.0</td>
      <td>243528.0</td>
      <td>NaN</td>
      <td>243528.0</td>
      <td>0.000000</td>
      <td>23534379.0</td>
      <td>1.543868e+08</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360143</td>
      <td>0.8786</td>
    </tr>
    <tr>
      <th>65</th>
      <td>804173</td>
      <td>360348</td>
      <td>DUBLIN METHODIST HOSPITAL</td>
      <td>7500 HOSPITAL DRIVE</td>
      <td>DUBLIN</td>
      <td>OH</td>
      <td>43016</td>
      <td>FRANKLIN</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>07/01/2023</td>
      <td>06/30/2024</td>
      <td>859.00</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1840.0</td>
      <td>31253.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>110.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1544.0</td>
      <td>26218.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>8662644.0</td>
      <td>6529247.0</td>
      <td>9971937.0</td>
      <td>18212017.0</td>
      <td>90872508.0</td>
      <td>1.670756e+08</td>
      <td>3714520.0</td>
      <td>2.098559e+08</td>
      <td>3.923512e+08</td>
      <td>6.831627e+08</td>
      <td>1.075514e+09</td>
      <td>18520085.0</td>
      <td>NaN</td>
      <td>90076936.0</td>
      <td>6895971.0</td>
      <td>NaN</td>
      <td>284692.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>213365159.0</td>
      <td>-158441459.0</td>
      <td>4583939.0</td>
      <td>NaN</td>
      <td>1826117.0</td>
      <td>62663175.0</td>
      <td>12002054.0</td>
      <td>4304133.0</td>
      <td>1.064236e+08</td>
      <td>NaN</td>
      <td>57315630.0</td>
      <td>36133457.0</td>
      <td>5318246.0</td>
      <td>NaN</td>
      <td>9.830465e+07</td>
      <td>NaN</td>
      <td>5493960.0</td>
      <td>5.493960e+06</td>
      <td>1.664618e+08</td>
      <td>7361901.0</td>
      <td>7402489.0</td>
      <td>NaN</td>
      <td>22046460.0</td>
      <td>NaN</td>
      <td>15200134.0</td>
      <td>52010984.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.901896e+08</td>
      <td>1.901896e+08</td>
      <td>2.422006e+08</td>
      <td>-7.573878e+07</td>
      <td>-7.573878e+07</td>
      <td>1.664618e+08</td>
      <td>NaN</td>
      <td>3886533.0</td>
      <td>13695949.0</td>
      <td>NaN</td>
      <td>208793.0</td>
      <td>0.0000</td>
      <td>18207187.0</td>
      <td>1329710.0</td>
      <td>3.923885e+08</td>
      <td>6.831627e+08</td>
      <td>1.075551e+09</td>
      <td>7.004998e+08</td>
      <td>3.750514e+08</td>
      <td>2.579481e+08</td>
      <td>117103275.0</td>
      <td>3609144.0</td>
      <td>120712419.0</td>
      <td>NaN</td>
      <td>120712419.0</td>
      <td>0.000000</td>
      <td>9424320.0</td>
      <td>9.308563e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360348</td>
      <td>0.9346</td>
    </tr>
    <tr>
      <th>66</th>
      <td>806349</td>
      <td>360144</td>
      <td>SOUTH POINTE HOSPITAL</td>
      <td>4110 WARRENSVILLE CENTER ROAD</td>
      <td>WARRENSVILLE HEIGHTS</td>
      <td>OH</td>
      <td>44122-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>681.00</td>
      <td>32.0</td>
      <td>NaN</td>
      <td>7495.0</td>
      <td>1723.0</td>
      <td>30896.0</td>
      <td>138.0</td>
      <td>51424.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>138.0</td>
      <td>NaN</td>
      <td>6763.0</td>
      <td>1146.0</td>
      <td>22962.0</td>
      <td>96.0</td>
      <td>36094.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>3404647.0</td>
      <td>5056528.0</td>
      <td>4612672.0</td>
      <td>9297780.0</td>
      <td>57312306.0</td>
      <td>9.714770e+07</td>
      <td>9197783.0</td>
      <td>1.297566e+08</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>12323638.0</td>
      <td>NaN</td>
      <td>59365336.0</td>
      <td>13294493.0</td>
      <td>20052.0</td>
      <td>1077300.0</td>
      <td>2041.0</td>
      <td>-110582469.0</td>
      <td>NaN</td>
      <td>25837032.0</td>
      <td>-10247255.0</td>
      <td>4513176.0</td>
      <td>180759.0</td>
      <td>NaN</td>
      <td>-88970100.0</td>
      <td>4703177.0</td>
      <td>8196400.0</td>
      <td>1.427239e+08</td>
      <td>24966.0</td>
      <td>2244703.0</td>
      <td>29978152.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.180659e+07</td>
      <td>NaN</td>
      <td>4059481.0</td>
      <td>4.059481e+06</td>
      <td>-2.310403e+07</td>
      <td>5085976.0</td>
      <td>3691350.0</td>
      <td>NaN</td>
      <td>5419373.0</td>
      <td>NaN</td>
      <td>969652.0</td>
      <td>15166351.0</td>
      <td>NaN</td>
      <td>1.737651e+07</td>
      <td>NaN</td>
      <td>1.936435e+06</td>
      <td>1.931295e+07</td>
      <td>3.447930e+07</td>
      <td>-5.758333e+07</td>
      <td>-5.758333e+07</td>
      <td>-2.310403e+07</td>
      <td>NaN</td>
      <td>9785083.0</td>
      <td>3206009.0</td>
      <td>NaN</td>
      <td>347512.0</td>
      <td>0.0000</td>
      <td>21935652.0</td>
      <td>1393594.0</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>4.463686e+08</td>
      <td>1.428610e+08</td>
      <td>1.544600e+08</td>
      <td>-11598964.0</td>
      <td>3247968.0</td>
      <td>-8350996.0</td>
      <td>NaN</td>
      <td>-8350996.0</td>
      <td>0.000000</td>
      <td>21682032.0</td>
      <td>1.265699e+08</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360144</td>
      <td>0.8786</td>
    </tr>
    <tr>
      <th>67</th>
      <td>807149</td>
      <td>360059</td>
      <td>METROHEALTH MEDICAL CENTER</td>
      <td>2500 METROHEALTH DRIVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44109</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>13</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>7711.00</td>
      <td>400.0</td>
      <td>NaN</td>
      <td>13400.0</td>
      <td>7587.0</td>
      <td>113599.0</td>
      <td>501.0</td>
      <td>182865.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>670.0</td>
      <td>NaN</td>
      <td>11346.0</td>
      <td>5024.0</td>
      <td>82749.0</td>
      <td>398.0</td>
      <td>145270.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>52249491.0</td>
      <td>41241147.0</td>
      <td>64768232.0</td>
      <td>172613758.0</td>
      <td>815495894.0</td>
      <td>1.022078e+09</td>
      <td>122305389.0</td>
      <td>1.144066e+09</td>
      <td>1.305561e+09</td>
      <td>2.477536e+09</td>
      <td>3.783097e+09</td>
      <td>151234382.0</td>
      <td>NaN</td>
      <td>815495894.0</td>
      <td>4095473.0</td>
      <td>2234972.0</td>
      <td>6887728.0</td>
      <td>167167876.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>181964719.0</td>
      <td>-32420355.0</td>
      <td>28286678.0</td>
      <td>18745013.0</td>
      <td>NaN</td>
      <td>451274662.0</td>
      <td>274381921.0</td>
      <td>25832250.0</td>
      <td>1.035162e+09</td>
      <td>17809023.0</td>
      <td>398974483.0</td>
      <td>259449588.0</td>
      <td>2564590.0</td>
      <td>NaN</td>
      <td>1.234442e+09</td>
      <td>5.369092e+08</td>
      <td>734717506.0</td>
      <td>1.271627e+09</td>
      <td>2.957343e+09</td>
      <td>89655513.0</td>
      <td>122910887.0</td>
      <td>NaN</td>
      <td>24192974.0</td>
      <td>NaN</td>
      <td>32359137.0</td>
      <td>270430031.0</td>
      <td>NaN</td>
      <td>1.090432e+09</td>
      <td>NaN</td>
      <td>1.183095e+09</td>
      <td>2.273527e+09</td>
      <td>2.543957e+09</td>
      <td>4.133858e+08</td>
      <td>4.133858e+08</td>
      <td>2.957343e+09</td>
      <td>NaN</td>
      <td>19277875.0</td>
      <td>6847645.0</td>
      <td>NaN</td>
      <td>2427061.0</td>
      <td>0.0000</td>
      <td>57246922.0</td>
      <td>7608953.0</td>
      <td>1.512498e+09</td>
      <td>3.187045e+09</td>
      <td>4.699543e+09</td>
      <td>3.424704e+09</td>
      <td>1.274839e+09</td>
      <td>1.842426e+09</td>
      <td>-567586421.0</td>
      <td>598744604.0</td>
      <td>31158183.0</td>
      <td>NaN</td>
      <td>31158183.0</td>
      <td>0.000000</td>
      <td>276594217.0</td>
      <td>1.271232e+09</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360059</td>
      <td>0.8786</td>
    </tr>
  </tbody>
</table>
<p>68 rows × 119 columns</p>
</div>



```python

# CALCULATE WAGE INDEX ADJUSTMENT FACTOR (LABOR SHARE METHOD)

# Why this matters: CMS adjusts DRG payments to reflect local labor cost differences across regions.
# Only the "labor-related" portion of payment is wage-adjusted (not the full payment).

# Formula: WI Adjustment Factor = (Labor Share × Wage Index) + (1 − Labor Share)

# Interpretation:
# - If Wage Index =< 1.00 → factor = 1.00 (no change)
# - If Wage Index > 1.00 → payments increase

labor_share = 0.68

cms_ccr_oh_u_ccn["WI Adjustment Factor"] = (
    labor_share * cms_ccr_oh_u_ccn["Wage Index 2023"]
) + (1 - labor_share)

display(cms_ccr_oh_u_ccn)
```


<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>rpt_rec_num</th>
      <th>Provider CCN</th>
      <th>Hospital Name</th>
      <th>Street Address</th>
      <th>City</th>
      <th>State Code</th>
      <th>Zip Code</th>
      <th>County</th>
      <th>Medicare CBSA Number</th>
      <th>Rural Versus Urban</th>
      <th>CCN Facility Type</th>
      <th>Provider Type</th>
      <th>Type of Control</th>
      <th>Fiscal Year Begin Date</th>
      <th>Fiscal Year End Date</th>
      <th>FTE - Employees on Payroll</th>
      <th>Number of Interns and Residents (FTE)</th>
      <th>Total Days Title V</th>
      <th>Total Days Title XVIII</th>
      <th>Total Days Title XIX</th>
      <th>Total Days (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds</th>
      <th>Total Bed Days Available</th>
      <th>Total Discharges Title V</th>
      <th>Total Discharges Title XVIII</th>
      <th>Total Discharges Title XIX</th>
      <th>Total Discharges (V + XVIII + XIX + Unknown)</th>
      <th>Number of Beds + Total for all Subproviders</th>
      <th>Hospital Total Days Title V For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Days Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Days (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Hospital Number of Beds For Adults &amp; Peds</th>
      <th>Hospital Total Bed Days Available For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title V For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XVIII For Adults &amp; Peds</th>
      <th>Hospital Total Discharges Title XIX For Adults &amp; Peds</th>
      <th>Hospital Total Discharges (V + XVIII + XIX + Unknown) For Adults &amp; Peds</th>
      <th>Cost of Charity Care</th>
      <th>Total Bad Debt Expense</th>
      <th>Cost of Uncompensated Care</th>
      <th>Total Unreimbursed and Uncompensated Care</th>
      <th>Total Salaries From Worksheet A</th>
      <th>Overhead Non-Salary Costs</th>
      <th>Depreciation Cost</th>
      <th>Total Costs</th>
      <th>Inpatient Total Charges</th>
      <th>Outpatient Total Charges</th>
      <th>Combined Outpatient + Inpatient Total Charges</th>
      <th>Wage-Related Costs (Core)</th>
      <th>Wage-Related Costs (RHC/FQHC)</th>
      <th>Total Salaries (adjusted)</th>
      <th>Contract Labor: Direct Patient Care</th>
      <th>Wage Related Costs for Part - A Teaching Physicians</th>
      <th>Wage Related Costs for Interns and Residents</th>
      <th>Cash on Hand and in Banks</th>
      <th>Temporary Investments</th>
      <th>Notes Receivable</th>
      <th>Accounts Receivable</th>
      <th>Less: Allowances for Uncollectible Notes and Accounts Receivable</th>
      <th>Inventory</th>
      <th>Prepaid Expenses</th>
      <th>Other Current Assets</th>
      <th>Total Current Assets</th>
      <th>Land</th>
      <th>Land Improvements</th>
      <th>Buildings</th>
      <th>Leasehold Improvements</th>
      <th>Fixed Equipment</th>
      <th>Major Movable Equipment</th>
      <th>Minor Equipment Depreciable</th>
      <th>Health Information Technology Designated Assets</th>
      <th>Total Fixed Assets</th>
      <th>Investments</th>
      <th>Other Assets</th>
      <th>Total Other Assets</th>
      <th>Total Assets</th>
      <th>Accounts Payable</th>
      <th>Salaries, Wages, and Fees Payable</th>
      <th>Payroll Taxes Payable</th>
      <th>Notes and Loans Payable (Short Term)</th>
      <th>Deferred Income</th>
      <th>Other Current Liabilities</th>
      <th>Total Current Liabilities</th>
      <th>Mortgage Payable</th>
      <th>Notes Payable</th>
      <th>Unsecured Loans</th>
      <th>Other Long Term Liabilities</th>
      <th>Total Long Term Liabilities</th>
      <th>Total Liabilities</th>
      <th>General Fund Balance</th>
      <th>Total Fund Balances</th>
      <th>Total Liabilities and Fund Balances</th>
      <th>DRG Amounts Other Than Outlier Payments</th>
      <th>DRG Amounts Before October 1</th>
      <th>DRG Amounts After October 1</th>
      <th>Outlier Payments For Discharges</th>
      <th>Disproportionate Share Adjustment</th>
      <th>Allowable DSH Percentage</th>
      <th>Managed Care Simulated Payments</th>
      <th>Total IME Payment</th>
      <th>Inpatient Revenue</th>
      <th>Outpatient Revenue</th>
      <th>Total Patient Revenue</th>
      <th>Less Contractual Allowance and Discounts on Patients' Accounts</th>
      <th>Net Patient Revenue</th>
      <th>Less Total Operating Expense</th>
      <th>Net Income from Service to Patients</th>
      <th>Total Other Income</th>
      <th>Total Income</th>
      <th>Total Other Expenses</th>
      <th>Net Income</th>
      <th>Cost To Charge Ratio</th>
      <th>Net Revenue from Medicaid</th>
      <th>Medicaid Charges</th>
      <th>Net Revenue from Stand-Alone CHIP</th>
      <th>Stand-Alone CHIP Charges</th>
      <th>CCN</th>
      <th>Wage Index 2023</th>
      <th>WI Adjustment Factor</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>772302</td>
      <td>360189</td>
      <td>MADISON HEALTH</td>
      <td>210 NORTH MAIN STREET</td>
      <td>LONDON</td>
      <td>OH</td>
      <td>43140-</td>
      <td>MADISON</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>240.91</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>837.0</td>
      <td>41.0</td>
      <td>3398.0</td>
      <td>45.0</td>
      <td>16425.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>45.0</td>
      <td>NaN</td>
      <td>464.0</td>
      <td>28.0</td>
      <td>1990.0</td>
      <td>32.0</td>
      <td>11680.0</td>
      <td>NaN</td>
      <td>207.0</td>
      <td>20.0</td>
      <td>926.0</td>
      <td>496204.0</td>
      <td>5407503.0</td>
      <td>1741928.0</td>
      <td>5319204.0</td>
      <td>18010729.0</td>
      <td>3.367992e+07</td>
      <td>5293848.0</td>
      <td>4.602876e+07</td>
      <td>2.958593e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>5182408.0</td>
      <td>NaN</td>
      <td>18010729.0</td>
      <td>1154149.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2664688.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7969832.0</td>
      <td>NaN</td>
      <td>1161089.0</td>
      <td>1543583.0</td>
      <td>NaN</td>
      <td>16694600.0</td>
      <td>2058728.0</td>
      <td>1432397.0</td>
      <td>4.912698e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>28774601.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.575774e+07</td>
      <td>3.707201e+07</td>
      <td>3870344.0</td>
      <td>4.094236e+07</td>
      <td>9.339470e+07</td>
      <td>2216194.0</td>
      <td>3060674.0</td>
      <td>NaN</td>
      <td>1620663.0</td>
      <td>NaN</td>
      <td>1974927.0</td>
      <td>8872458.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.599493e+07</td>
      <td>3.599493e+07</td>
      <td>4.486739e+07</td>
      <td>4.852731e+07</td>
      <td>4.852731e+07</td>
      <td>9.339470e+07</td>
      <td>NaN</td>
      <td>1399457.0</td>
      <td>380850.0</td>
      <td>NaN</td>
      <td>53410.0</td>
      <td>0.1200</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.958594e+07</td>
      <td>1.720465e+08</td>
      <td>2.016324e+08</td>
      <td>1.413727e+08</td>
      <td>6.025978e+07</td>
      <td>5.101758e+07</td>
      <td>9242202.0</td>
      <td>-2053858.0</td>
      <td>7188344.0</td>
      <td>-680.0</td>
      <td>7189024.0</td>
      <td>0.228281</td>
      <td>4628233.0</td>
      <td>3.594478e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360189</td>
      <td>0.9346</td>
      <td>0.955528</td>
    </tr>
    <tr>
      <th>1</th>
      <td>772303</td>
      <td>360351</td>
      <td>CRYSTAL CLINIC ORTHOPAEDIC CENTER</td>
      <td>444 N. MAIN STREET</td>
      <td>AKRON</td>
      <td>OH</td>
      <td>44310</td>
      <td>SUMMIT</td>
      <td>10420.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>4</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>829.28</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>59.0</td>
      <td>NaN</td>
      <td>1535.0</td>
      <td>1.0</td>
      <td>5061.0</td>
      <td>59.0</td>
      <td>21535.0</td>
      <td>NaN</td>
      <td>754.0</td>
      <td>1.0</td>
      <td>2117.0</td>
      <td>NaN</td>
      <td>4966858.0</td>
      <td>1025756.0</td>
      <td>4491088.0</td>
      <td>59842683.0</td>
      <td>1.410437e+08</td>
      <td>19791461.0</td>
      <td>1.757999e+08</td>
      <td>1.723140e+08</td>
      <td>6.789364e+08</td>
      <td>8.512503e+08</td>
      <td>16227538.0</td>
      <td>NaN</td>
      <td>59842683.0</td>
      <td>2833456.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20226359.0</td>
      <td>NaN</td>
      <td>91445.0</td>
      <td>143984935.0</td>
      <td>-115969987.0</td>
      <td>4254008.0</td>
      <td>5590825.0</td>
      <td>364672.0</td>
      <td>58542257.0</td>
      <td>1797791.0</td>
      <td>972311.0</td>
      <td>7.353677e+06</td>
      <td>14842928.0</td>
      <td>5829690.0</td>
      <td>40446507.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.777400e+07</td>
      <td>NaN</td>
      <td>116070299.0</td>
      <td>1.160703e+08</td>
      <td>2.123866e+08</td>
      <td>5248828.0</td>
      <td>5287289.0</td>
      <td>NaN</td>
      <td>15147407.0</td>
      <td>NaN</td>
      <td>13317765.0</td>
      <td>39001289.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.039823e+08</td>
      <td>1.039823e+08</td>
      <td>1.429836e+08</td>
      <td>6.940295e+07</td>
      <td>6.940295e+07</td>
      <td>2.123866e+08</td>
      <td>NaN</td>
      <td>8019249.0</td>
      <td>2943604.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.723155e+08</td>
      <td>7.043064e+08</td>
      <td>8.766219e+08</td>
      <td>6.728033e+08</td>
      <td>2.038185e+08</td>
      <td>2.008864e+08</td>
      <td>2932156.0</td>
      <td>4699468.0</td>
      <td>7631624.0</td>
      <td>NaN</td>
      <td>7631624.0</td>
      <td>0.206520</td>
      <td>6048085.0</td>
      <td>4.606535e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360351</td>
      <td>0.8360</td>
      <td>0.888480</td>
    </tr>
    <tr>
      <th>2</th>
      <td>773604</td>
      <td>360092</td>
      <td>MEMORIAL HOSPITAL OF UNION COUNTY</td>
      <td>500 LONDON AVENUE</td>
      <td>MARYSVILLE</td>
      <td>OH</td>
      <td>43040-</td>
      <td>UNION</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>9</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>715.78</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1888.0</td>
      <td>466.0</td>
      <td>8688.0</td>
      <td>51.0</td>
      <td>18615.0</td>
      <td>NaN</td>
      <td>664.0</td>
      <td>55.0</td>
      <td>2719.0</td>
      <td>51.0</td>
      <td>NaN</td>
      <td>1784.0</td>
      <td>83.0</td>
      <td>7310.0</td>
      <td>39.0</td>
      <td>14235.0</td>
      <td>NaN</td>
      <td>664.0</td>
      <td>55.0</td>
      <td>2719.0</td>
      <td>1296612.0</td>
      <td>10184707.0</td>
      <td>4471898.0</td>
      <td>10932284.0</td>
      <td>60532285.0</td>
      <td>1.020931e+08</td>
      <td>9549895.0</td>
      <td>1.336948e+08</td>
      <td>7.755640e+07</td>
      <td>3.522619e+08</td>
      <td>4.298183e+08</td>
      <td>16558853.0</td>
      <td>NaN</td>
      <td>60532285.0</td>
      <td>1694453.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>39553623.0</td>
      <td>13286590.0</td>
      <td>NaN</td>
      <td>21815875.0</td>
      <td>NaN</td>
      <td>1954919.0</td>
      <td>2096449.0</td>
      <td>1011916.0</td>
      <td>85393958.0</td>
      <td>3017141.0</td>
      <td>5246439.0</td>
      <td>1.162705e+08</td>
      <td>NaN</td>
      <td>2737700.0</td>
      <td>87307904.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.282003e+08</td>
      <td>7.960842e+07</td>
      <td>47234308.0</td>
      <td>1.268427e+08</td>
      <td>3.404370e+08</td>
      <td>11247442.0</td>
      <td>12095547.0</td>
      <td>NaN</td>
      <td>28559091.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>52567080.0</td>
      <td>NaN</td>
      <td>6.777074e+07</td>
      <td>NaN</td>
      <td>9.047551e+07</td>
      <td>1.582462e+08</td>
      <td>2.108133e+08</td>
      <td>1.296237e+08</td>
      <td>1.296237e+08</td>
      <td>3.404370e+08</td>
      <td>NaN</td>
      <td>3889441.0</td>
      <td>1652815.0</td>
      <td>NaN</td>
      <td>80086.0</td>
      <td>0.0578</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7.770045e+07</td>
      <td>3.680071e+08</td>
      <td>4.457075e+08</td>
      <td>2.731381e+08</td>
      <td>1.725695e+08</td>
      <td>1.755439e+08</td>
      <td>-2974447.0</td>
      <td>12398185.0</td>
      <td>9423738.0</td>
      <td>133399.0</td>
      <td>9290339.0</td>
      <td>0.311050</td>
      <td>7711324.0</td>
      <td>5.137945e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360092</td>
      <td>0.9346</td>
      <td>0.955528</td>
    </tr>
    <tr>
      <th>3</th>
      <td>773606</td>
      <td>360263</td>
      <td>INSTITUTE FOR ORTHOPAEDIC SURGERY</td>
      <td>801 MEDICAL DRIVE</td>
      <td>LIMA</td>
      <td>OH</td>
      <td>45804</td>
      <td>ALLEN</td>
      <td>30620.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>6</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>175.06</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>645.0</td>
      <td>18.0</td>
      <td>1230.0</td>
      <td>12.0</td>
      <td>4380.0</td>
      <td>NaN</td>
      <td>284.0</td>
      <td>12.0</td>
      <td>581.0</td>
      <td>12.0</td>
      <td>NaN</td>
      <td>645.0</td>
      <td>18.0</td>
      <td>1230.0</td>
      <td>12.0</td>
      <td>4380.0</td>
      <td>NaN</td>
      <td>284.0</td>
      <td>12.0</td>
      <td>581.0</td>
      <td>NaN</td>
      <td>2620740.0</td>
      <td>419156.0</td>
      <td>683481.0</td>
      <td>11308402.0</td>
      <td>3.003173e+07</td>
      <td>-4154.0</td>
      <td>3.649592e+07</td>
      <td>1.228750e+08</td>
      <td>1.074157e+08</td>
      <td>2.302907e+08</td>
      <td>3573493.0</td>
      <td>NaN</td>
      <td>11308402.0</td>
      <td>103036.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1164259.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9391865.0</td>
      <td>-1858489.0</td>
      <td>1443630.0</td>
      <td>284126.0</td>
      <td>NaN</td>
      <td>10425391.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>104120.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.042539e+07</td>
      <td>2730598.0</td>
      <td>492461.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>330076.0</td>
      <td>3553135.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.500000e+05</td>
      <td>2.500000e+05</td>
      <td>3.803135e+06</td>
      <td>6.622256e+06</td>
      <td>6.622256e+06</td>
      <td>1.042539e+07</td>
      <td>NaN</td>
      <td>2949645.0</td>
      <td>983215.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.228750e+08</td>
      <td>1.074157e+08</td>
      <td>2.302907e+08</td>
      <td>1.676803e+08</td>
      <td>6.261041e+07</td>
      <td>4.134013e+07</td>
      <td>21270276.0</td>
      <td>3228154.0</td>
      <td>24498430.0</td>
      <td>NaN</td>
      <td>24498430.0</td>
      <td>0.158478</td>
      <td>2504429.0</td>
      <td>1.368459e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360263</td>
      <td>0.8371</td>
      <td>0.889228</td>
    </tr>
    <tr>
      <th>4</th>
      <td>774171</td>
      <td>360091</td>
      <td>MEDINA HOSPITAL</td>
      <td>1000 E. WASHINGTON STREET</td>
      <td>MEDINA</td>
      <td>OH</td>
      <td>44256-</td>
      <td>MEDINA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>724.89</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9657.0</td>
      <td>304.0</td>
      <td>33651.0</td>
      <td>148.0</td>
      <td>54020.0</td>
      <td>NaN</td>
      <td>2178.0</td>
      <td>66.0</td>
      <td>7764.0</td>
      <td>148.0</td>
      <td>NaN</td>
      <td>8790.0</td>
      <td>246.0</td>
      <td>30521.0</td>
      <td>136.0</td>
      <td>49640.0</td>
      <td>NaN</td>
      <td>2178.0</td>
      <td>66.0</td>
      <td>7764.0</td>
      <td>3315241.0</td>
      <td>4945504.0</td>
      <td>4447134.0</td>
      <td>10292294.0</td>
      <td>62399059.0</td>
      <td>1.020755e+08</td>
      <td>8765794.0</td>
      <td>1.459961e+08</td>
      <td>2.700763e+08</td>
      <td>3.988384e+08</td>
      <td>6.689147e+08</td>
      <td>14818214.0</td>
      <td>470095.0</td>
      <td>62399059.0</td>
      <td>178769.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1186251.0</td>
      <td>15856930.0</td>
      <td>NaN</td>
      <td>31825503.0</td>
      <td>-8732284.0</td>
      <td>3800471.0</td>
      <td>192896.0</td>
      <td>NaN</td>
      <td>45236434.0</td>
      <td>1225994.0</td>
      <td>3022719.0</td>
      <td>1.403456e+08</td>
      <td>NaN</td>
      <td>1204751.0</td>
      <td>30621442.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.032573e+07</td>
      <td>1.753343e+08</td>
      <td>932868.0</td>
      <td>1.762671e+08</td>
      <td>2.818293e+08</td>
      <td>4444238.0</td>
      <td>5664249.0</td>
      <td>138407.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2117910.0</td>
      <td>12364804.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.944760e+05</td>
      <td>2.944760e+05</td>
      <td>1.265928e+07</td>
      <td>2.691700e+08</td>
      <td>2.691700e+08</td>
      <td>2.818293e+08</td>
      <td>NaN</td>
      <td>13574247.0</td>
      <td>5042413.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.700763e+08</td>
      <td>3.988384e+08</td>
      <td>6.689147e+08</td>
      <td>4.857001e+08</td>
      <td>1.832147e+08</td>
      <td>1.644745e+08</td>
      <td>18740119.0</td>
      <td>18683312.0</td>
      <td>37423431.0</td>
      <td>NaN</td>
      <td>37423431.0</td>
      <td>0.218258</td>
      <td>9212941.0</td>
      <td>6.387463e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360091</td>
      <td>0.8786</td>
      <td>0.917448</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>63</th>
      <td>803874</td>
      <td>360077</td>
      <td>FAIRVIEW HOSPITAL</td>
      <td>18101 LORAIN AVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44111-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>2421.00</td>
      <td>80.0</td>
      <td>NaN</td>
      <td>21348.0</td>
      <td>6859.0</td>
      <td>122041.0</td>
      <td>466.0</td>
      <td>170090.0</td>
      <td>NaN</td>
      <td>4400.0</td>
      <td>401.0</td>
      <td>25124.0</td>
      <td>466.0</td>
      <td>NaN</td>
      <td>18091.0</td>
      <td>5310.0</td>
      <td>84810.0</td>
      <td>376.0</td>
      <td>137240.0</td>
      <td>NaN</td>
      <td>4400.0</td>
      <td>401.0</td>
      <td>25124.0</td>
      <td>11522919.0</td>
      <td>13926609.0</td>
      <td>14791492.0</td>
      <td>31185546.0</td>
      <td>202255263.0</td>
      <td>3.496126e+08</td>
      <td>20823064.0</td>
      <td>5.016847e+08</td>
      <td>1.093822e+09</td>
      <td>1.171575e+09</td>
      <td>2.265396e+09</td>
      <td>49903087.0</td>
      <td>NaN</td>
      <td>202255263.0</td>
      <td>18263738.0</td>
      <td>7784.0</td>
      <td>938801.0</td>
      <td>4995647.0</td>
      <td>62939122.0</td>
      <td>NaN</td>
      <td>107257170.0</td>
      <td>-32543024.0</td>
      <td>14131157.0</td>
      <td>544859.0</td>
      <td>NaN</td>
      <td>177035687.0</td>
      <td>2525153.0</td>
      <td>8692729.0</td>
      <td>3.008051e+08</td>
      <td>2359410.0</td>
      <td>7866114.0</td>
      <td>99709100.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.332000e+08</td>
      <td>2.570368e+09</td>
      <td>3184457.0</td>
      <td>2.573552e+09</td>
      <td>2.883788e+09</td>
      <td>14615894.0</td>
      <td>18452497.0</td>
      <td>447045.0</td>
      <td>14247049.0</td>
      <td>NaN</td>
      <td>13749118.0</td>
      <td>61511603.0</td>
      <td>NaN</td>
      <td>7.373888e+07</td>
      <td>NaN</td>
      <td>7.535950e+05</td>
      <td>7.449248e+07</td>
      <td>1.360041e+08</td>
      <td>2.747784e+09</td>
      <td>2.747784e+09</td>
      <td>2.883788e+09</td>
      <td>NaN</td>
      <td>34674889.0</td>
      <td>11462474.0</td>
      <td>NaN</td>
      <td>1912394.0</td>
      <td>0.0000</td>
      <td>67998993.0</td>
      <td>3209453.0</td>
      <td>1.105629e+09</td>
      <td>1.180188e+09</td>
      <td>2.285817e+09</td>
      <td>1.614905e+09</td>
      <td>6.709122e+08</td>
      <td>5.518678e+08</td>
      <td>119044353.0</td>
      <td>190097143.0</td>
      <td>309141496.0</td>
      <td>NaN</td>
      <td>309141496.0</td>
      <td>0.000000</td>
      <td>67817475.0</td>
      <td>4.180697e+08</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360077</td>
      <td>0.8786</td>
      <td>0.917448</td>
    </tr>
    <tr>
      <th>64</th>
      <td>804003</td>
      <td>360143</td>
      <td>MARYMOUNT HOSPITAL</td>
      <td>12300 MCCRACKEN ROAD</td>
      <td>GARFIELD HTS.</td>
      <td>OH</td>
      <td>44125-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>743.00</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>7617.0</td>
      <td>1004.0</td>
      <td>32016.0</td>
      <td>188.0</td>
      <td>68620.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>262.0</td>
      <td>NaN</td>
      <td>6670.0</td>
      <td>864.0</td>
      <td>28081.0</td>
      <td>160.0</td>
      <td>58400.0</td>
      <td>NaN</td>
      <td>1659.0</td>
      <td>122.0</td>
      <td>7240.0</td>
      <td>4960258.0</td>
      <td>6005537.0</td>
      <td>6610489.0</td>
      <td>20288869.0</td>
      <td>68760998.0</td>
      <td>1.288689e+08</td>
      <td>13004822.0</td>
      <td>1.861900e+08</td>
      <td>2.915091e+08</td>
      <td>4.133701e+08</td>
      <td>7.048792e+08</td>
      <td>15485875.0</td>
      <td>NaN</td>
      <td>68760998.0</td>
      <td>10372586.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3327.0</td>
      <td>8750189.0</td>
      <td>NaN</td>
      <td>35798654.0</td>
      <td>-12021126.0</td>
      <td>5908241.0</td>
      <td>187265.0</td>
      <td>NaN</td>
      <td>40704523.0</td>
      <td>2156995.0</td>
      <td>9811905.0</td>
      <td>1.891104e+08</td>
      <td>2497691.0</td>
      <td>604085.0</td>
      <td>47685000.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>9.535494e+07</td>
      <td>3.978384e+07</td>
      <td>3642514.0</td>
      <td>4.342636e+07</td>
      <td>1.794858e+08</td>
      <td>8567580.0</td>
      <td>6329099.0</td>
      <td>160114.0</td>
      <td>11316159.0</td>
      <td>NaN</td>
      <td>1607638.0</td>
      <td>27980590.0</td>
      <td>NaN</td>
      <td>3.013659e+07</td>
      <td>NaN</td>
      <td>-2.380000e+04</td>
      <td>3.011279e+07</td>
      <td>5.809338e+07</td>
      <td>1.213924e+08</td>
      <td>1.213924e+08</td>
      <td>1.794858e+08</td>
      <td>NaN</td>
      <td>9998352.0</td>
      <td>3597148.0</td>
      <td>NaN</td>
      <td>294682.0</td>
      <td>0.0000</td>
      <td>23296909.0</td>
      <td>NaN</td>
      <td>2.919227e+08</td>
      <td>4.143265e+08</td>
      <td>7.062492e+08</td>
      <td>5.214664e+08</td>
      <td>1.847829e+08</td>
      <td>1.976299e+08</td>
      <td>-12847074.0</td>
      <td>13090602.0</td>
      <td>243528.0</td>
      <td>NaN</td>
      <td>243528.0</td>
      <td>0.000000</td>
      <td>23534379.0</td>
      <td>1.543868e+08</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360143</td>
      <td>0.8786</td>
      <td>0.917448</td>
    </tr>
    <tr>
      <th>65</th>
      <td>804173</td>
      <td>360348</td>
      <td>DUBLIN METHODIST HOSPITAL</td>
      <td>7500 HOSPITAL DRIVE</td>
      <td>DUBLIN</td>
      <td>OH</td>
      <td>43016</td>
      <td>FRANKLIN</td>
      <td>18140.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>1</td>
      <td>07/01/2023</td>
      <td>06/30/2024</td>
      <td>859.00</td>
      <td>16.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1840.0</td>
      <td>31253.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>110.0</td>
      <td>NaN</td>
      <td>6050.0</td>
      <td>1544.0</td>
      <td>26218.0</td>
      <td>110.0</td>
      <td>40255.0</td>
      <td>NaN</td>
      <td>1682.0</td>
      <td>700.0</td>
      <td>8752.0</td>
      <td>8662644.0</td>
      <td>6529247.0</td>
      <td>9971937.0</td>
      <td>18212017.0</td>
      <td>90872508.0</td>
      <td>1.670756e+08</td>
      <td>3714520.0</td>
      <td>2.098559e+08</td>
      <td>3.923512e+08</td>
      <td>6.831627e+08</td>
      <td>1.075514e+09</td>
      <td>18520085.0</td>
      <td>NaN</td>
      <td>90076936.0</td>
      <td>6895971.0</td>
      <td>NaN</td>
      <td>284692.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>213365159.0</td>
      <td>-158441459.0</td>
      <td>4583939.0</td>
      <td>NaN</td>
      <td>1826117.0</td>
      <td>62663175.0</td>
      <td>12002054.0</td>
      <td>4304133.0</td>
      <td>1.064236e+08</td>
      <td>NaN</td>
      <td>57315630.0</td>
      <td>36133457.0</td>
      <td>5318246.0</td>
      <td>NaN</td>
      <td>9.830465e+07</td>
      <td>NaN</td>
      <td>5493960.0</td>
      <td>5.493960e+06</td>
      <td>1.664618e+08</td>
      <td>7361901.0</td>
      <td>7402489.0</td>
      <td>NaN</td>
      <td>22046460.0</td>
      <td>NaN</td>
      <td>15200134.0</td>
      <td>52010984.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.901896e+08</td>
      <td>1.901896e+08</td>
      <td>2.422006e+08</td>
      <td>-7.573878e+07</td>
      <td>-7.573878e+07</td>
      <td>1.664618e+08</td>
      <td>NaN</td>
      <td>3886533.0</td>
      <td>13695949.0</td>
      <td>NaN</td>
      <td>208793.0</td>
      <td>0.0000</td>
      <td>18207187.0</td>
      <td>1329710.0</td>
      <td>3.923885e+08</td>
      <td>6.831627e+08</td>
      <td>1.075551e+09</td>
      <td>7.004998e+08</td>
      <td>3.750514e+08</td>
      <td>2.579481e+08</td>
      <td>117103275.0</td>
      <td>3609144.0</td>
      <td>120712419.0</td>
      <td>NaN</td>
      <td>120712419.0</td>
      <td>0.000000</td>
      <td>9424320.0</td>
      <td>9.308563e+07</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360348</td>
      <td>0.9346</td>
      <td>0.955528</td>
    </tr>
    <tr>
      <th>66</th>
      <td>806349</td>
      <td>360144</td>
      <td>SOUTH POINTE HOSPITAL</td>
      <td>4110 WARRENSVILLE CENTER ROAD</td>
      <td>WARRENSVILLE HEIGHTS</td>
      <td>OH</td>
      <td>44122-</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>2</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>681.00</td>
      <td>32.0</td>
      <td>NaN</td>
      <td>7495.0</td>
      <td>1723.0</td>
      <td>30896.0</td>
      <td>138.0</td>
      <td>51424.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>138.0</td>
      <td>NaN</td>
      <td>6763.0</td>
      <td>1146.0</td>
      <td>22962.0</td>
      <td>96.0</td>
      <td>36094.0</td>
      <td>NaN</td>
      <td>1528.0</td>
      <td>274.0</td>
      <td>6105.0</td>
      <td>3404647.0</td>
      <td>5056528.0</td>
      <td>4612672.0</td>
      <td>9297780.0</td>
      <td>57312306.0</td>
      <td>9.714770e+07</td>
      <td>9197783.0</td>
      <td>1.297566e+08</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>12323638.0</td>
      <td>NaN</td>
      <td>59365336.0</td>
      <td>13294493.0</td>
      <td>20052.0</td>
      <td>1077300.0</td>
      <td>2041.0</td>
      <td>-110582469.0</td>
      <td>NaN</td>
      <td>25837032.0</td>
      <td>-10247255.0</td>
      <td>4513176.0</td>
      <td>180759.0</td>
      <td>NaN</td>
      <td>-88970100.0</td>
      <td>4703177.0</td>
      <td>8196400.0</td>
      <td>1.427239e+08</td>
      <td>24966.0</td>
      <td>2244703.0</td>
      <td>29978152.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>6.180659e+07</td>
      <td>NaN</td>
      <td>4059481.0</td>
      <td>4.059481e+06</td>
      <td>-2.310403e+07</td>
      <td>5085976.0</td>
      <td>3691350.0</td>
      <td>NaN</td>
      <td>5419373.0</td>
      <td>NaN</td>
      <td>969652.0</td>
      <td>15166351.0</td>
      <td>NaN</td>
      <td>1.737651e+07</td>
      <td>NaN</td>
      <td>1.936435e+06</td>
      <td>1.931295e+07</td>
      <td>3.447930e+07</td>
      <td>-5.758333e+07</td>
      <td>-5.758333e+07</td>
      <td>-2.310403e+07</td>
      <td>NaN</td>
      <td>9785083.0</td>
      <td>3206009.0</td>
      <td>NaN</td>
      <td>347512.0</td>
      <td>0.0000</td>
      <td>21935652.0</td>
      <td>1393594.0</td>
      <td>2.521162e+08</td>
      <td>3.371134e+08</td>
      <td>5.892296e+08</td>
      <td>4.463686e+08</td>
      <td>1.428610e+08</td>
      <td>1.544600e+08</td>
      <td>-11598964.0</td>
      <td>3247968.0</td>
      <td>-8350996.0</td>
      <td>NaN</td>
      <td>-8350996.0</td>
      <td>0.000000</td>
      <td>21682032.0</td>
      <td>1.265699e+08</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360144</td>
      <td>0.8786</td>
      <td>0.917448</td>
    </tr>
    <tr>
      <th>67</th>
      <td>807149</td>
      <td>360059</td>
      <td>METROHEALTH MEDICAL CENTER</td>
      <td>2500 METROHEALTH DRIVE</td>
      <td>CLEVELAND</td>
      <td>OH</td>
      <td>44109</td>
      <td>CUYAHOGA</td>
      <td>17460.0</td>
      <td>U</td>
      <td>STH</td>
      <td>1</td>
      <td>13</td>
      <td>01/01/2023</td>
      <td>12/31/2023</td>
      <td>7711.00</td>
      <td>400.0</td>
      <td>NaN</td>
      <td>13400.0</td>
      <td>7587.0</td>
      <td>113599.0</td>
      <td>501.0</td>
      <td>182865.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>670.0</td>
      <td>NaN</td>
      <td>11346.0</td>
      <td>5024.0</td>
      <td>82749.0</td>
      <td>398.0</td>
      <td>145270.0</td>
      <td>NaN</td>
      <td>2211.0</td>
      <td>1526.0</td>
      <td>20086.0</td>
      <td>52249491.0</td>
      <td>41241147.0</td>
      <td>64768232.0</td>
      <td>172613758.0</td>
      <td>815495894.0</td>
      <td>1.022078e+09</td>
      <td>122305389.0</td>
      <td>1.144066e+09</td>
      <td>1.305561e+09</td>
      <td>2.477536e+09</td>
      <td>3.783097e+09</td>
      <td>151234382.0</td>
      <td>NaN</td>
      <td>815495894.0</td>
      <td>4095473.0</td>
      <td>2234972.0</td>
      <td>6887728.0</td>
      <td>167167876.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>181964719.0</td>
      <td>-32420355.0</td>
      <td>28286678.0</td>
      <td>18745013.0</td>
      <td>NaN</td>
      <td>451274662.0</td>
      <td>274381921.0</td>
      <td>25832250.0</td>
      <td>1.035162e+09</td>
      <td>17809023.0</td>
      <td>398974483.0</td>
      <td>259449588.0</td>
      <td>2564590.0</td>
      <td>NaN</td>
      <td>1.234442e+09</td>
      <td>5.369092e+08</td>
      <td>734717506.0</td>
      <td>1.271627e+09</td>
      <td>2.957343e+09</td>
      <td>89655513.0</td>
      <td>122910887.0</td>
      <td>NaN</td>
      <td>24192974.0</td>
      <td>NaN</td>
      <td>32359137.0</td>
      <td>270430031.0</td>
      <td>NaN</td>
      <td>1.090432e+09</td>
      <td>NaN</td>
      <td>1.183095e+09</td>
      <td>2.273527e+09</td>
      <td>2.543957e+09</td>
      <td>4.133858e+08</td>
      <td>4.133858e+08</td>
      <td>2.957343e+09</td>
      <td>NaN</td>
      <td>19277875.0</td>
      <td>6847645.0</td>
      <td>NaN</td>
      <td>2427061.0</td>
      <td>0.0000</td>
      <td>57246922.0</td>
      <td>7608953.0</td>
      <td>1.512498e+09</td>
      <td>3.187045e+09</td>
      <td>4.699543e+09</td>
      <td>3.424704e+09</td>
      <td>1.274839e+09</td>
      <td>1.842426e+09</td>
      <td>-567586421.0</td>
      <td>598744604.0</td>
      <td>31158183.0</td>
      <td>NaN</td>
      <td>31158183.0</td>
      <td>0.000000</td>
      <td>276594217.0</td>
      <td>1.271232e+09</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>360059</td>
      <td>0.8786</td>
      <td>0.917448</td>
    </tr>
  </tbody>
</table>
<p>68 rows × 120 columns</p>
</div>



```python

```


```python

```


```python
# EXPORT FINAL OHIO URBAN COST REPORT DATASET (CCR + WAGE INDEX)
# Purpose:
# - Save the cleaned and enriched Ohio Urban hospital dataset to Excel
# - This exported file is the final input used in the Power BI dashboard

# Notes:
# - The dataset includes Cost-to-Charge Ratio (CCR) and Wage Index fields
# - CCR is converted to numeric to avoid type issues in Excel/Power BI

cms_ccr_oh_u["Cost To Charge Ratio"] = pd.to_numeric(
    cms_ccr_oh_u["Cost To Charge Ratio"], errors="coerce"
)

cms_ccr_oh_u_ccn.to_excel("CMS Ogio Hospitals - Urban - CCR-WI.xlsx", index=False)


```


```python

```


```python

```
