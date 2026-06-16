# Cleaning Log

## Project
Business Data Cleaning, Validation & Excel Reporting

Student Name: Ishi Seth  
Student ID: BA_251119

---

# 1. Issues Found

The following data quality issues were identified in the raw dataset:

- Leading and trailing spaces in text fields
- Multiple spaces between words
- Inconsistent text capitalization
- Unwanted special characters in some text values
- Inconsistent category and status naming
- Missing region values
- Missing ship_mode values
- Missing discount values
- Invalid or missing dates
- Ship dates occurring before order dates
- Duplicate records
- Duplicate order IDs with conflicting information
- Negative discount values
- Discount values outside the allowed range
- Cancelled orders
- Failed payment records
- Refunded orders
- Sales and profit calculation inconsistencies

---

# 2. Cleaning Actions Performed

### Text Cleaning

The following fields were standardized:

- customer_name
- segment
- region
- state
- city
- category
- sub_category
- ship_mode
- payment_status
- order_status

Actions performed:

- Removed leading and trailing spaces using TRIM()
- Removed extra spaces between words
- Standardized capitalization using PROPER()
- Removed unwanted special characters using SUBSTITUTE()
- Standardized inconsistent category names
- Standardized inconsistent status values
- Used Find and Replace where necessary
- Used Flash Fill where applicable

---

### Date Cleaning

Validated:

- order_date
- ship_date

Actions performed:

- Converted dates into a consistent format
- Identified missing dates
- Identified invalid dates
- Flagged non-date text values
- Flagged records where ship_date was earlier than order_date

---

### Duplicate Handling

Actions performed:

- Identified exact duplicate rows
- Removed exact duplicate rows where appropriate
- Identified duplicate order IDs
- Reviewed duplicate order IDs for conflicting information
- Flagged conflicting records for manual review

---

# 3. Business Rules Applied

### Missing Region

- Missing region values were replaced with "Unknown".

### Missing Ship Mode

- Missing ship_mode values were replaced with "Unknown".

### Missing Discount

- Missing discount values were replaced with 0 only when related sales fields were valid.

### Negative Discount

- Negative discounts were flagged as invalid.

### Discount Above Allowed Range

- Discounts above the acceptable range were flagged as invalid.

### Cancelled Orders

- Retained in the dataset.
- Excluded from completed sales analysis.

### Failed Payments

- Retained in the dataset.
- Excluded from completed sales analysis.

### Refunded Orders

- Retained in the dataset.
- Reported separately in summary reports.

### Invalid Shipping Records

- Records with ship_date earlier than order_date were flagged.

---

# 4. Calculated Columns Added

The following columns were created:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag

---

# 5. Assumptions Made

- Missing region values were treated as Unknown.
- Missing ship_mode values were treated as Unknown.
- Missing discounts were assumed to be 0 when sales information was valid.
- Cancelled orders do not contribute to completed sales.
- Failed payments do not contribute to completed sales.
- Refunded orders require separate reporting.
- Profit margin was calculated using calculated sales and calculated profit.
- Duplicate order IDs with conflicting information require manual review.

---

# 6. Records Removed

- Exact duplicate records were removed after validation.
- One copy of each exact duplicate record was retained.

Total records removed: X

---

# 7. Records Flagged

The following records were flagged:

- Invalid discounts
- Discounts above allowed range
- Missing critical dates
- Invalid dates
- Ship date before order date
- Duplicate order IDs with conflicting information
- Calculation mismatches

Total records flagged: X

---

# 8. Limitations

- Some business decisions required assumptions because source system rules were not provided.
- Duplicate records with conflicting business information require manual review.
- Discount validation depends on the allowed range defined by business policy.
- Date validation depends on source data quality.
- Automated cleaning cannot guarantee correction of all business-specific data issues.

---

# Conclusion

The dataset was successfully cleaned, validated, and transformed into an analysis-ready format. Data quality issues were documented, business rules were applied, calculated fields were created, and summary reports were generated for business review.
