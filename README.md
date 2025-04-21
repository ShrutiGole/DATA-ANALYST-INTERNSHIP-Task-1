# DATA-ANALYST-INTERNSHIP-Task-1 : Data Cleaning and Preprocessing

Data Cleaning & Preprocessing Documentation
markdown
Copy
Edit
# 📊 Sales Data Cleaning & Preparation Report

This README documents the cleaning and transformation process applied to the `sales_data_sample.csv` dataset. The objective was to clean, standardize, and prepare the dataset for high-quality analysis and reporting.

---

## ✅ Key Cleaning Steps Performed

### 1. 🧼 **Handling Missing Values**
- **TERRITORY**:
  - Replaced `"NA"` and `NaN` values with `"North America"`.
- **ADDRESSLINE2**:
  - Dropped entirely as it is an optional secondary address field.
- **STATE & POSTALCODE**:
  - Missing values were filled based on grouping by `CITY` and `COUNTRY` using forward and backward fill logic.

---

### 2. 🧹 **Text Standardization**
- Converted all **text columns** to **Title Case** for consistency.
- **STATE** column was standardized to **UPPERCASE**.
- **COUNTRY, CITY, PRODUCT LINE, ORDER STATUS** were cleaned and stripped of leading/trailing whitespace.

---

### 3. 📞 **Phone Number Formatting**
- All phone numbers were normalized to the **international format**:
  - Example: `+1-123-456-7890`
  - Non-digit characters removed, US numbers formatted consistently.

---

### 4. 🕒 **Date Formatting**
- `ORDERDATE` column:
  - Converted to `datetime` type.
  - Standardized format to: `dd/mm/yyyy`

---

### 5. 🧾 **Column Renaming**
Renamed columns to be clean, uniform, and descriptive using `UPPER_SNAKE_CASE` format:

| Old Name         | New Name       |
|------------------|----------------|
| ORDERNUMBER      | ORDER_ID       |
| ORDERDATE        | ORDER_DATE     |
| PRICEEACH        | PRICE_EACH     |
| CUSTOMERNAME     | CUSTOMER_NAME  |
| CONTACTFIRSTNAME | FIRST_NAME     |
| CONTACTLASTNAME  | LAST_NAME      |
| PRODUCTLINE      | PRODUCT_LINE   |
| ORDERLINENUMBER  | LINE_NUMBER    |
| DEALSIZE         | DEAL_SIZE      |
| SALES            | TOTAL_SALES    |
| ...              | ...            |

---

### 6. 🧮 **Data Type Fixes**
Ensured all key columns had appropriate data types:
- `ORDER_DATE`: datetime
- `ORDER_ID`, `QUANTITY`, `LINE_NUMBER`, `MSRP`: integers
- `TOTAL_SALES`, `PRICE_EACH`: float
- `POSTALCODE`: string (to preserve leading zeros)
- `ORDER_STATUS`, `PRODUCT_LINE`: converted to categorical types

---

### 7. 🔁 **Duplicate Removal**
- All exact duplicate rows were detected and removed using `.drop_duplicates()`.
