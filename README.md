## Data Cleaning Practice - Google Sheets

The [dataset](https://www.kaggle.com/datasets/amruthayenikonda/dirty-dataset-to-practice-data-cleaning) has been obtained from Kaggle, from the user Amrutha Yenikonda, this dataset will be used to practice data cleaning and manipulation like removing unwanted columns, nulls, removing symbols, etc.

This dataset consists of a list of the highest grossing music tours by Women.

### First I start by importing the dataset to Google Sheets, **here is a preview of the raw dataset:**

<img width="1157" height="604" alt="image" src="https://github.com/user-attachments/assets/884b42b2-a95a-4a37-94b6-824091f13c48" />

This dataset is made of 11 columns and 21 rows including the header

### Data Cleaning Process

- **Header Styling:**
   - I started by styling the header rows by using a bold font to identify them, 
   - Then I used the freezing row feature to not lose track of the headers while scrolling,
   - I standarized the headers by changing the names to remove the hidden special characters and long names, 
   - Finally, I finished the styling by adjusting the widths of all columns so that the data was clearly visible in all cells.
<img width="1044" height="469" alt="image" src="https://github.com/user-attachments/assets/d824ec83-53ab-4dee-833f-3488b5443baf" />

- **Removing Duplicates:** I used the Remove Duplicates function on Google Sheets to search for duplicate records in the data, but no duplicates were found.
<img width="1249" height="502" alt="image" src="https://github.com/user-attachments/assets/b086ddaa-7e14-429b-9353-4c30cbbd674e" />

- **Removing Unnecessary Features:** I removed one unnecessary column (Column K) that contained Wikipedia-style citations used by the original author for referencing, but in our case it has no analytical value.
<img width="357" height="483" alt="image" src="https://github.com/user-attachments/assets/211ea62c-c922-4272-ab23-f7a4ec7c38bb" />

- **Removing Unnecessary Symbols and Characters:** The `tour_title` column (Column G in the raw data) has symbols like `†` and Wikipedia citations like `[4][a]`.

  - I cleaned these symbols by using the **Find and Replace** feature on Google Sheets, copying and pasting the symbols I wanted to remove (`†`, `‡` & `*`) and clicking `Replace all`, replacing them with empty space.
<img width="675" height="573" alt="image" src="https://github.com/user-attachments/assets/aff3ca6a-4a61-4445-9865-637b70902f8b" />

  - Then I removed all Wikipedia citation brackets by using a regular expression in the **Find and Replace** feature, the expression `\[.*\]` which finds everything that starts with a bracket and ends with a bracket.
  <img width="676" height="600" alt="image" src="https://github.com/user-attachments/assets/17bb25bc-c1c4-41ef-957b-e3ca01609708" />
  
  - This is the clean result on the `tour_title` column (Column G in the raw data)
  <img width="241" height="469" alt="image" src="https://github.com/user-attachments/assets/e4689dcf-4381-43c7-a091-6456c7d0a446" />
  
  - Then I applied the same regular expression on the rest of the dataset to remove any other citation brackets found on our data.
  <img width="1147" height="594" alt="image" src="https://github.com/user-attachments/assets/024c9186-5d27-4e33-84ec-f969c214d6ec" />
  
   - This is the clean result on the whole dataset.
  <img width="985" height="469" alt="image" src="https://github.com/user-attachments/assets/f63bd0c5-e77a-439e-85ec-dbe7bab84c17" />

- **Changing Strings for Numbers:** The columns `actual_gross`, `adjusted_gross`, and `avg_gross` (Columns D, E, and J) are currently text strings, because they contain `$` symbols and commas.
  -  To fix this, I selected the columns and used the `Format as currency` feature on Google Sheets.
<img width="782" height="545" alt="image" src="https://github.com/user-attachments/assets/360fc210-1a0e-4eb8-b7fc-0e1ac1ac8e6a" />

  - This is clean result on those columns.
<img width="353" height="467" alt="image" src="https://github.com/user-attachments/assets/506d50a1-4faf-44e3-8bf3-bb978ca2747b" />


- **Cleaning Nulls:** in the columns `peak` and	`all_time_peak` (Columns B and C in the raw data) we can find some null data that we can replace with a placeholder for better readability, to do this we can use the filter feature on Google Sheets, selecting the columns we want to modify and creating a filter to leave only `Blank` cells.

<img width="390" height="574" alt="image" src="https://github.com/user-attachments/assets/6ba5df5b-1ef4-45e9-a310-55842cfb1757" />

Then I replaced those blanks with `N/A` and used the `Autofill` feature to copy it in all the blank cells.

<img width="103" height="323" alt="image" src="https://github.com/user-attachments/assets/811e1e22-9e04-4c4f-8d48-b43b0049e505" />

I finally, repeated the same in the other column, leaving both of them clean and with a placeholder to replace the null data.

<img width="133" height="468" alt="image" src="https://github.com/user-attachments/assets/4e7bf57f-80fe-429a-8844-7d47a492b312" />

- **Cleaning the Rank Logic:** To finish the cleaning we need to re-number the rank column from 1 to 20 based on the `actual_gross` values, to do this, I typed `1` and `2` in the first two rows, selected them and used the `autofill` feature to fix the rank logic.

<img width="64" height="99" alt="image" src="https://github.com/user-attachments/assets/24d89b9f-0e6b-4843-866f-c7edded7e3b1" />

## Preview of the final result - Clean Data

<img width="1016" height="467" alt="image" src="https://github.com/user-attachments/assets/513121b4-17ea-4946-9dd1-a2681ed2cfb4" />












