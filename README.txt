Retail data-quality practice dataset

Exact row counts:
- calendar.csv: 60 (five dates in each month, January-December 2025)
- stores.csv: 50
- customers.csv: 1,000
- products.csv: 200
- sales_transactions.csv: 6,000

All sales transaction dates are drawn from the 60 calendar dates. Every sales store_id, product_id, and customer_id references an existing row in its master table. Primary IDs are unique and non-null; customer and product names are unique and non-null. Manager IDs are unique and non-null. Transaction IDs are unique and non-null.

Return rule is preserved exactly: quantity=-1, sales_amount=-300, return_flag=Y.

Intentional cleaning/validation practice issues: mixed date formats; incorrect is_weekend values; inconsistent city casing; selected null states/regions/emails/discounts/promo codes/sales amounts; negative and zero ages; inconsistent customer active flags; currency symbols and comma separators in numeric transaction fields; invalid numeric strings; anomalous negative quantity; invalid tax rate; duplicate transaction business details under a distinct transaction ID.

For ordinary valid non-return transactions, sales_amount is quantity * unit_price * (1-discount_pct) * (1+tax_pct). Currency strings, missing values, and other deliberately malformed records may require cleaning before validation.
