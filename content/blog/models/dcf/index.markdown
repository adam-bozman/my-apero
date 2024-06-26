---
title: "Discounted Cash Flows"
weight: 3
subtitle: ""
excerpt: ""
date: "2024-06-03"
draft: false
---

# Understanding Cash Flows in Financial Modeling

## Types of Cash Flows

Cash flows are crucial for evaluating a company's financial health and investment potential. They can be categorized into three main types:

### Operating Cash Flows (OCF)
- Generated from the core business operations.
- Includes cash receipts from sales and cash payments for expenses.
- **Formula**: 
  \[
  \text{OCF} = \text{Net Income} + \text{Non-cash Expenses} + \text{Changes in Working Capital}
  \]

### Investing Cash Flows (ICF)
- Associated with the purchase and sale of long-term assets.
- Includes capital expenditures and proceeds from asset sales.
- **Formula**: 
  \[
  \text{ICF} = \text{Capital Expenditures} - \text{Proceeds from Sale of Assets}
  \]

### Financing Cash Flows (FCF)
- Related to borrowing, repaying debt, and equity transactions.
- Includes dividends paid and proceeds from issuing stock or debt.
- **Formula**: 
  \[
  \text{FCF} = \text{Proceeds from Issuance of Debt or Equity} - \text{Repayments} + \text{Dividends Paid}
  \]

## Cash Flows to Firm vs. Cash Flows to Equity

### Cash Flows to the Firm (FCFF)
- Represents the cash flow available to all capital providers (both debt and equity holders).
- FCFF is used in enterprise valuation.
- **Formula**: 
  \[
  \text{FCFF} = \text{Net Income} + \text{Non-cash Expenses} + \text{Interest} \times (1 - \text{Tax Rate}) - \text{Changes in Working Capital} - \text{Capital Expenditures}
  \]

### Cash Flows to Equity (FCFE)
- Represents the cash flow available to equity shareholders.
- FCFE is used in equity valuation.
- **Formula**: 
  \[
  \text{FCFE} = \text{FCFF} - \text{Interest} \times (1 - \text{Tax Rate}) + \text{Net Borrowing}
  \]

## The Math Underpinning Cash Flows

### Time Value of Money (TVM)
Fundamental concept stating that money available now is worth more than the same amount in the future due to its earning potential.

### Net Present Value (NPV)
- The value of all future cash flows (both incoming and outgoing) over the entire life of an investment discounted to the present.
- **Formula**: 
  \[
  \text{NPV} = \sum_{t=1}^{n} \frac{CF_t}{(1 + r)^t} - \text{Initial Investment}
  \]
- \(CF_t\) is the cash flow at time \(t\), \(r\) is the discount rate, and \(n\) is the number of periods.

# Discounted Cash Flow (DCF) Processes

## Generic DCF Process

1. **Forecast Future Cash Flows**:
   - Project the company's future operating cash flows, capital expenditures, and changes in working capital.

2. **Determine the Discount Rate**:
   - Use the Weighted Average Cost of Capital (WACC) for FCFF or the Cost of Equity for FCFE.

3. **Calculate the Terminal Value**:
   - Estimate the value of the company beyond the forecast period.
   - **Formula**: 
     \[
     \text{Terminal Value} = \frac{FCF_{n+1}}{(r - g)}
     \]
   - Where \(FCF_{n+1}\) is the cash flow in the first year after the forecast period, \(r\) is the discount rate, and \(g\) is the growth rate.

4. **Discount Cash Flows to Present Value**:
   - Discount the forecasted cash flows and terminal value back to present value using the discount rate.

5. **Summing Up**:
   - Sum the present value of the forecasted cash flows and the terminal value to get the total enterprise value or equity value.

## DCF in Excel

1. **Set Up Your Spreadsheet**:
   - Create columns for each year of the forecast period.
   - Include rows for revenues, expenses, taxes, changes in working capital, capital expenditures, and resulting cash flows.

2. **Calculate Each Component**:
   - Use Excel formulas to project revenues and expenses.
   - Calculate free cash flows for each year.

3. **Discount Cash Flows**:
   - Use the NPV function to discount cash flows back to the present value.
   - **Formula in Excel**: `=NPV(discount_rate, cash_flows_range)`

4. **Calculate Terminal Value**:
   - Use the formula for terminal value.
   - Include the terminal value in your NPV calculation.
   - **Formula in Excel**: `=Terminal_Value / (1 + discount_rate)^years`

5. **Sum the Present Values**:
   - Add the NPV of the forecast period and the discounted terminal value.
   - Example Spreadsheet Setup:
     - Column A: Year
     - Column B: Cash Flows
     - Column C: Discounted Cash Flows (`=B2/(1+$B$1)^A2`)

## DCF in Python Jupyter Notebooks

```python
import numpy as np

# Define cash flows and discount rate
cash_flows = np.array([-100000, 20000, 30000, 40000, 50000, 60000])
discount_rate = 0.1

# Calculate NPV
npv = np.npv(discount_rate, cash_flows)
print(f"Net Present Value (NPV): {npv}")

# Calculate Terminal Value
fcf_next_year = 60000
growth_rate = 0.02
terminal_value = fcf_next_year / (discount_rate - growth_rate)
terminal_value_pv = terminal_value / (1 + discount_rate) ** len(cash_flows)
print(f"Terminal Value (Present Value): {terminal_value_pv}")

# Total Value
total_value = npv + terminal_value_pv
print(f"Total Value: {total_value}")
