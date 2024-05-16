# DCRB1
- The schema of the database ```(SQL DDL)``` is contained inside the file ```bulk_db_batch.py``` immediately after the function ```connect_db()```.
- The script to build the schema, the table and load the table is ```bulk_db_batch```.
- The script of the search engine is ```retrival.py```.
- Snapshot for non existing string -> see ```e```.
- Snapshot of the search for a string matching at least two file names, but not found in any searchable file -> see ```f```.
- Snapshot of the search for a string matching at least one file name and contained in at least one searchable file, with the counts of the occurrences in the files -> see ```g```.
- Snapshot of the search for a sting that does not match a file name but is found in at least one searchable file, with the counts of the occurrences in the files -> see ```h```.
# Database
```Schema: file_info(ID, Name, Path, SizeInBytes, Type, CreationTime, LastModifiedTim, Txt)```
# Features
* The program is able to index all the files in the filesystem. It's necessary change the path (first parameter) of the function ```populate_db()``` of the script bulk_db_batch.py
* The program implement a functionality to load the database in batches. The size of the batch is chosen tuning the parameter ```MAX_BATCH_SIZE```. This implementation avoid to saturate the RAM.
* The functions ```executemany()``` and ```commit()``` are used to insert ```MAX_BATCH_SIZE``` tuples into the database for each commit instead to insert a single tuple and commit just a single insert.
## Necessary libraries
* To run the search facility the ```mysql connector``` library is necessary. It's possible to install the driver using the command ```pip(3) install mysql-connector-python```
