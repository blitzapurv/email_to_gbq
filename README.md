# Email_to_Google Big Query
Exporting data directly from email to google bigquery table.
This solution enables users to regularly upload data from email by searching email inbox directly to BigQuery table.

The functional steps in this process are broadly listed below:

- **Searching Inbox :** Searching for a desired email(s) based on a search query. Enlisting all the emails that qualify and then look for attachements if any.
- **Extracting data from Attachemtns and reading it :** This is done while also checking if the file is already ingested in to the table by referring ingested_files logs. If the file is already successfully ingested then nothing is done.
- **Transforming and uploading to respecting Tables in gbq :** Necessary tranformations are made and the data is uploaded to gbq table.
- **Cloud Scheduler :** A Cloud Scheduler job is used to schedule run the script periodically to upload data as it comes.


This process makes us of a configuratoin file, which is a google sheet, uploadparams.gsheet which is accessed and modified using Google Sheets API.

The parameters in the file are described below:

![ee](https://user-images.githubusercontent.com/93088807/192857902-2c0e6430-a59b-4b37-aa10-e9720fadf0e7.JPG)
