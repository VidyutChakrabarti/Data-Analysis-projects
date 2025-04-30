### Components:
1. Text Preprocessing:

- clean_text(): Normalizes text by inserting spaces around numbers and removing unwanted characters.

- correct_units(): Converts shorthand like 11'' or 10" into full form (11 inches), and replaces certain symbols (e.g., /, \, ,).

2. Unit Extraction:

- extract_units(): Uses the quantulum3 parser to identify and extract quantities with specific units from cleaned and corrected text, using an entity_unit_map to filter relevant units per entity.

3. Image OCR & Unit Detection:

**fetch_and_ocr_from_csv():**

- Loads image links and entity names from a CSV.

- Performs OCR using EasyOCR with multiple image rotations and preprocessing to improve accuracy.

- Aggregates detected text, processes it, and extracts relevant measurements.

- Displays image and prints extracted details for verification.

### Flow:
- Load and sample rows from CSV.

- For each sampled image:

   - Perform OCR with multiple rotations and image preprocessing.

   - Extract all detected text and clean it.

   - Identify and return only relevant unit measurements.

   - Display results and image for inspection.