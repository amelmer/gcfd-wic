This is the website I used to convert the excel file into a geojson: https://www.convertcsv.com/csv-to-geojson.htm </br>
</br>
<b>Data Cleaning Steps</b>
1. Split the excel file into two separate files. The website does not seem to recognize the second sheet in the file.
2. Delete the Partner Type (old) column from the Austin spreadsheet.
3. Delete any rows that do not have latitude and longitude coordinates.
4. Identify the latitude and longitude columns (16 & 17).
5. In the text box where it generates the geojson, delete any features it generates that do not have coordinates.
6. Copy the remaining features and replace the current austin/south chicago geojson with them.
7. Add "var austin =" or "var south_chicago =" to the beginning of the file and a ";" at the very end of the file and save it as a javascript file (replace the ones that currently exist).
8. The map should update to show the new data.
