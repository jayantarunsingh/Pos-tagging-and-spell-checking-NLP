# POS-Tagging-and-Spell-Checking

## Overview
This project focuses on tokenization, Part-of-Speech (POS) tagging, and spell-checking for Telugu text using tools such as **Stanza** and the **Indic NLP Library**. Additionally, it provides functionality for grouping words into sentences, correcting misspellings, and re-applying POS tagging for corrected sentences.

## Features
1. **Tokenization and POS Tagging**:
   - Tokenizes and applies POS tagging to Telugu text using Stanza.
   - Processes each verse in the dataset to generate word-POS pairs.

2. **Spell Checking**:
   - Identifies and flags potentially misspelled words.
   - Suggests corrections using a basic spell-checking mechanism (e.g., `difflib` for similarity-based suggestions).

3. **Sentence Grouping**:
   - Groups tokens into sentences based on punctuation (e.g., `.`, `!`, `?`).

4. **Reprocessing**:
   - Corrects misspelled words in sentences.
   - Reapplies POS tagging to corrected sentences.

5. **Visualization**:
   - Generates bar plots of POS tag distributions using Matplotlib and Seaborn.

6. **Output Formatting**:
   - Creates a structured dataset with words, POS tags, and spell-check status.
   - Saves the final output to a CSV file for further use.

## Requirements
Install the following Python libraries:
- `stanza`
- `indic-nlp-library`
- `pandas`
- `matplotlib`
- `seaborn`
- `difflib` (built into Python)

Run the command to install required libraries:
```bash
pip install stanza indic-nlp-library
```

## Dataset
The input dataset should be a CSV file with a column `Verse` containing the Telugu text.

### Sample Input
| Verse            |
|------------------|
| మీ పేరు ఏమిటి? |
| మీరు ఎలా ఉన్నారు? |

## How to Run
1. **Prepare the Dataset**:
   - Place the dataset file in your working directory (e.g., `/content/dataset(nlp).csv`).

2. **Install Dependencies**:
   - Install the required Python libraries.

3. **Run the Script**:
   - Execute the Python script provided in the `final_project(nlp).ipynb` file.

4. **Outputs**:
   - The script generates:
     - A CSV file containing tokenized words, POS tags, and spell-check results.
     - Visualizations of POS tag distributions.

## Workflow
1. **Tokenization and POS Tagging**:
   - Initialize the Stanza Telugu model for tokenization and POS tagging.
   - Process each verse to extract word-POS pairs.

2. **Spell Checking**:
   - Flag words as "Correct" or "Incorrect" based on a placeholder logic (or a predefined word list).
   - Suggest corrections for misspelled words using `difflib`.

3. **Sentence Grouping**:
   - Group words into sentences using punctuation marks as delimiters.

4. **POS Tagging for Corrected Sentences**:
   - Reapply POS tagging to corrected sentences (optional).

5. **Visualization**:
   - Plot the frequency distribution of POS tags using Seaborn.

6. **Save Results**:
   - Save the processed data to a CSV file.

## Example Usage
### Input Verse
```
మీరు ఎలా ఉన్నారు?
```

### Output
| Word   | POS_Tag | Spell_Check |
|--------|---------|-------------|
| మీరు  | PRP     | Correct     |
| ఎలా   | RB      | Correct     |
| ఉన్నారు | VB     | Correct     |
| ?      | PUNCT   | Correct     |

### Corrected Sentence
```
మీరు ఎలా ఉన్నారు?
```

## Results Visualization
The POS tag distribution plot provides insights into the frequency of various POS tags in the dataset.

## File Outputs
- **Processed Data**: A CSV file with tokenized words, POS tags, and spell-check results.
- **Visualization**: A bar chart of POS tag frequencies.

## Notes
- Ensure the Stanza Telugu model is downloaded before running the script:
  ```python
  stanza.download('te', processors='tokenize,pos')
  ```
- Replace the placeholder spell-checking function with a more sophisticated implementation for better accuracy.

## Author
Developed by [Jagadhish3](https://github.com/Jagadhish3).

---
**Repository**: [POS-Tagging-and-Spell-Checking](https://github.com/Jagadhish3/POS-Tagging-and-Spell-Checking)

