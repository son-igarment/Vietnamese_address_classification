# Vietnamese Address Classification

AUTHOR: PHẠM LÊ NGỌC SƠN. This project implements a solution for classifying Vietnamese addresses into their constituent parts: province, district, and ward. It uses various text processing techniques and algorithms to accurately identify and standardize address components.

## Project Structure

```
final-address-classification/
├── district_abbreviations.json    # Abbreviations mapping for districts
├── list_district_standard.txt     # Standard district names
├── list_district_verification.txt # Verification list for districts
├── list_province_standard.txt     # Standard province names
├── list_province_verification.txt # Verification list for provinces
├── list_ward_standard.txt        # Standard ward names
├── list_ward_verification.txt    # Verification list for wards
├── province_abbreviations.json   # Abbreviations mapping for provinces
├── public_corrected.json        # Test data with correct classifications
├── QuangVietSonAnh.py          # Main implementation file
├── test_3.json                  # Additional test cases
└── ward_abbreviations.json      # Abbreviations mapping for wards
```

## Features

1. **Text Normalization**
   - Removes special characters and extra spaces
   - Handles Vietnamese diacriticsssss
   - Normalizes common address format variations

2. **Address Component Recognition**
   - Province/City identification
   - District/Town identification
   - Ward/Commune identification

3. **Abbreviation Handling**
   - Supports common Vietnamese address abbreviations
   - Maps abbreviated forms to standard names

4. **Data Structures**
   - Uses Trie data structure for efficient string matching
   - Implements KMP algorithm for pattern matching
   - Employs edit distance for fuzzy matching

## Main Components

### Solution Class

The main implementation in `QuangVietSonAnh.py` contains:

1. **Initialization**
   - Loads standard and verification data
   - Initializes data structures
   - Sets up text processing patterns

2. **Text Processing**
   - `normalize_text()`: Cleans and standardizes input text
   - `preprocess()`: Applies various text preprocessing rules
   - Pattern matching for address components

3. **Data Loading**
   - `load_data()`: Loads address component data
   - `load_abbreviations()`: Loads abbreviation mappings
   - `load_data_standard()`: Loads standardized data

4. **Search and Matching**
   - Trie-based search implementation
   - KMP pattern matching
   - Edit distance calculation for fuzzy matching

### Groups and Standardization

The project maintains several standardization groups:
- Province groups
- District groups
- Ward groups

Each group contains mappings between various forms of the same name to ensure consistent classification.

## Usage

1. Initialize the solution:
```python
solution = Solution()
```

2. Process an address:
```python
result = solution.process("Your Vietnamese address here")
```

The result will contain standardized province, district, and ward names.

## Testing

The project includes test data in:
- `public_corrected.json`: Main test cases
- `test_3.json`: Additional test cases

Test results include:
- Accuracy metrics
- Processing time statistics
- Detailed classification results

## Technical Details

1. **Text Processing Features**
   - Special character handling
   - Number and abbreviation normalization
   - Vietnamese diacritic processing
   - Format standardization

2. **Matching Algorithms**
   - Trie-based search for exact matches
   - KMP algorithm for pattern matching
   - Edit distance for similarity matching

3. **Performance Optimizations**
   - Efficient data structures
   - Preprocessing for faster matching
   - Caching of common patterns

## Requirements

- Python 3.x
- Standard Python libraries (re, json, unicodedata)
- No additional external dependencies required

## Notes

- The solution is specifically designed for Vietnamese addresses
- Handles various formats and writing styles
- Supports both formal and informal address representations
- Maintains accuracy while dealing with abbreviations and local variations
