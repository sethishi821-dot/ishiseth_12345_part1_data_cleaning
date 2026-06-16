## Task 5: Business Rule Validation

### 1. Missing Region
Action:
- Missing values in the region field were replaced with "Unknown".
- All affected records were counted and reported in the Data Quality Report.

### 2. Missing Ship Mode
Action:
- Missing values in the ship_mode field were replaced with "Unknown".
- All affected records were counted and reported in the Data Quality Report.

### 3. Missing Discount
Action:
- Missing discount values were replaced with 0 only when all related sales fields were valid.
- Records failing validation were flagged for review.

### 4. Negative Discount
Action:
- Negative discount values were flagged as Invalid.
- No automatic correction was performed.

### 5. Discount Above Allowed Range
Action:
- Discount values above the permitted business range were flagged as Invalid.
- These records were included in the Data Quality Report.

### 6. Cancelled Orders
Action:
- Cancelled orders were retained in the dataset.
- Excluded from final completed sales summaries and sales analysis.

### 7. Failed Payments
Action:
- Orders with failed payment status were retained in the dataset.
- Excluded from final completed sales summaries and sales analysis.

### 8. Refunded Orders
Action:
- Refunded orders were retained in the dataset.
- Reported separately in summary reports.

### 9. Ship Date Before Order Date
Action:
- Records where ship_date occurred before order_date were flagged as Invalid Shipping Records.
- Included in the Data Quality Report for review.
