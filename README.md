# README

## Overview

This script, titled `calculate_prosodic_weight.ipynb`, calculates the prosodic weight of quadrisyllabic poetic lines from the ancient Chinese poetry collection, *Shijing* (Book of Poetry). The prosodic weight is determined by summing the weights assigned to each phonetic segment (vowels and consonants) based on established linguistic theories.

## Background

The *Shijing* is one of the oldest collections of Chinese poetry, consisting of various poetic forms. Understanding the prosodic structure of these poems can provide insights into their rhythm and musicality. This script implements a method to quantify this structure through prosodic weights, drawing on the work of Selkirk (1982) and Hogg & McCully (1997).

## Prosodic Weight Mapping

The prosodic weights for segments are defined as follows:

- **Vowels:**
  - a = 10
  - e, o = 9
  - i, u, ɯ, w = 8
  - j = 7

- **Consonants:**
  - l = 6
  - n, m, ŋ = 5
  - s = 3
  - d, g, b, ɢ = 2
  - ʔ = 1

These weights are based on:
- Selkirk, Elisabeth. 1982. *The syllable.* In H. V. d. Hulst, & N. Smith (Eds.), *The structure of phonological representations: Part 2* (pp. 337-384).
- Hogg, Richard M, & McCully, Christopher Bayston. 1987. *Metrical phonology: a course book.* Cambridge University Press.

## How It Works

1. **Input Data**: The script reads from a text file (`dic.txt`) containing the poetic lines in a specific format. Each line includes the poetic text followed by its phonetic transcription.

2. **Weight Calculation**:
   - The script iterates through each syllable in the transcription.
   - For each segment in a syllable, it checks if it's a vowel or consonant and adds its corresponding weight.
   - If a long vowel marker (ː) is found, it repeats the weight of the previous segment.

3. **Output**: The results are stored in a pandas DataFrame and exported to an Excel file (`output5.xlsx`), which contains the original data along with the calculated prosodic weights for each syllable.

## Requirements

- Python 3.x
- Pandas library
- OpenPyXL library (for Excel output)

## Installation

To run this script, ensure you have Python installed along with the required libraries. You can install the necessary libraries using pip:

```bash
pip install pandas openpyxl
