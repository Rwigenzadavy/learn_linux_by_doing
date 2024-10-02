# Commands Used in Task 2

1. Count the number of rows in the file:
   ```bash
   cat satelite_temperature_data.csv | wc -l
sort -u satelite_temperature_data.csv -o satelite_temperature_data.csv
sort -t, -k2 -nr data/satelite_temperature_data.csv | head -n 6 > analyzed/top-5-highest-temparatures.csv
sort -t, -k2 -n data/satelite_temperature_data.csv | head -n 6 > analyzed/top-5-lowest-temparatures.csv
grep 'CountryName' data/satelite_temperature_data.csv > analyzed/country-heat_data.csv
# 1. Delete a useless file:
rm data/test-1
# Deleted the file `test-1` from the `data` directory.

# 2. Move the file `top-5-lowest-temparatures.csv` to the analyzed directory:
mv top-5-lowest-temparatures.csv analyzed/
# Moved the file `top-5-lowest-temparatures.csv` from the root directory to the `analyzed` directory.

# 3. Rename file in the analyzed directory:
mv analyzed/incorrect_filename.csv analyzed/top-5-incorrect_filename.csv
# Renamed the file in `analyzed/` to match the naming convention `top-5...`.

# 4. Search and remove duplicate rows in `satelite_temperature_data.csv`:
sort data/satelite_temperature_data.csv | uniq > data/cleaned_satelite_temperature_data.csv
# Sorted and removed duplicate rows, saving the result as `cleaned_satelite_temperature_data.csv`.

# 5. Extract top 5 highest temperatures:
sort -t, -k2,2 -nr data/satelite_temperature_data.csv | head -5 > analyzed/top-5-highest-temparatures.csv
# Extracted the top 5 highest recorded temperatures and saved them into `top-5-highest-temparatures.csv`.

# 6. Extract top 5 lowest temperatures:
sort -t, -k2,2n data/satelite_temperature_data.csv | head -5 > analyzed/top-5-lowest-temparatures.csv
# Extracted the top 5 lowest recorded temperatures and saved them into `top-5-lowest-temparatures.csv`.

# 7. Extract heat data from your country:
grep "YourCountry" data/satelite_temperature_data.csv > analyzed/country-heat_data.csv
# Filtered and saved heat data from `YourCountry` into a new file `country-heat_data.csv`.
