Data Processing Summary
Initial Load: JSON data loaded into PySpark DataFrame.

Column Removal:

Removed name, description, and expiration_date columns.

Data Cleaning:

Removed hyphens from billing_code and negotiation_arrangements (e.g., "111-222" → "111222").

Removed "$" symbols from negotiated_rate values.

Data Transformation:

Applied SHA-256 hashing to service_code values.

Filtered out rows with null billing_code values.

Replaced null values in billing_class with "I".

Column Renaming:

Renamed columns to shorter aliases (e.g., billing_class → bCls, negotiated_rate → negR).

New Column:

Added billing_code_modifier (renamed to mdH) with default value "1426636".

Hashed the mdH column using SHA-256.

Output:

Saved processed data as a single Parquet file using coalesce(1).
