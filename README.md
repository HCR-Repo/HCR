### Requirements
- Pandas==1.5.1
### Folder Structure
- `test_folder_example`: The folder to store the collected code files and raw Copilot suggestion files.
- `computer_wordlist.txt`:  The compiled dictionary for the word filter, which contains the most common English words in top programming languages.
- `phase3_file_list.csv`: The csv file to store the meta information of `test_folder_example`.
- `filter.py`: The implementation of four filters.
- `extracted_result_test_folder_example.csv`: The sample result folder.
- `secret_re_list.csv`: The csv file to define the secret type and their regex.

### Usage
1. Follow Tab. 1 in the paper to prepare the `secret_re_list.csv`. 
2. Collect code files with secrets. Prepare a folder that contains all the code files. Inside this folder, create one folder (format: `test_ID`) for each code file. An example folder is `test_folder_example`, which contains three sample code files and their Copilot suggestions.
3. Remove the secret in each code file and ask Copilot for suggestions. Save the suggestions as a log file inside the corresponding `test_ID` folder. Please follow the format of `test_folder_example` for smooth running of the filters.
4. Prepare `phase3_file_list.csv`. In the csv file: `id` is the code file id; `secret_type` is the type of the secret in the code file; `file_name` is the filename of the code file. Note that `secret_type` should match the secret type definition (the `secret_id` column) in `secret_re_list.csv`; `file_name` should match the filename in Step 2.
5. Run `python filter.py`. A result csv file (`extracted_result_FOLDERNAME.csv`) will be generated. In `extracted_result_FOLDERNAME.csv`, `result_after_regex_filter` lists the secret strings that pass the regex filter. If the value of `regex_filter`,	`entropy_filter`, `pattern_filter`, or `word_filter` is True, it means that the secret string does not pass the corresponding filter. The `valid` column denotes whether the secret string is valid or not.

### Ethics
Following the current code of ethics of ACM and IEEE, to respect privacy: 
- Only three code files that we collected in Phase 3 are provided.
- All valid secrets presented in our code are only for demonstration purposes. Therefore, we rotate these secrets on purpose in our code.
  




