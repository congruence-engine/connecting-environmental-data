# **1871 Rivers Pollution Commission Report Datasets**

The files in this folder contain datasets based on the third report of the 1868 Rivers Pollution Commission, *Pollution Arising from the Woollen Manufacture, and Processes Connected Therewith* (1871). They were created as part of the 'Connecting Environmental Data' investigation by the *Congruence Engine* project. 

## Context

## File overview:
The folder contains the following files:
* 1871_all_companies_input.csv - a csv file with the full dataset extracted from the report, with column headers for 'firm_name', 'business_type', 'address', and 'reply'.
* 1871_all_companies.json - the processed dataset, with detailed values extracted from the 'reply' column in 1871_all_companies_input.csv.
* bradford_mills_1871.csv - a subset of the report, focussed specifically on textile mills in the Bradford area.
* bradford_mills_1871_extracted.json - the processed dataset for the Bradford subset. 

## Data preparation

### Pipeline
1. Image aquisition: the images of the report were acquired via ProQuest's UK Parliamentary Papers database. Because of licensing restrictions, we are unable to share the original images here.
2. OCR - Optical Character Recognition of the images was peformed using the [Surya](https://github.com/VikParuchuri/surya) OCR engine.
3. Conversion to CSV - The OCR results were then fed to the OpenAI API for conversion, first into a markdown file, and then into a CSV file with the following column headers: 'firm_name', 'business_type', 'address', 'reply'. This ensured that the data accurately matched the original table layout of the report. 
4. Manual cleaning - At this stage, the dataset was cleaned manually, with a view to fixing common OCR errors present in the dataset. Manual cleaning was also required for joining the cells of responses from businesses which ran over more than one page in the original report.
5. JSON file creation - Finally, the cleaned dataset was transformed into a structured JSON file, using the OpenAI API's 'Structured Outputs' option. This followed a pre-established schema that was included with the prompt. This enabled the 'reply' section to be transformed row by row in the input CSV.

## Code
You can find the relevant code files for each step of this process in the main '[code](https://github.com/congruence-engine/connecting-environmental-data/tree/main/code)' file of this repo. 
* [GPT splitting](https://github.com/congruence-engine/connecting-environmental-data/blob/main/code/GPT_split_1871_report.ipynb)
* 

## License
