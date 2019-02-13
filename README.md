# DigitalCommonsETDtoCatalog
Converting exported spreadsheets into MARC

Process starts on reciept of a DigitalCommons export spreadsheet.  There are three source repos in DigitalCommons: Disserations, Theses, and Major Papers.  
https://digitalcommons.lsu.edu/gradschool/
The fourth source repo, "Historical Diss/Theses" is not being added to, and it has already been migrated to Symphony.

To generate your own DigitalCommons export spreadsheet, log in as Adminstrator to Digital Commons, select a source repo, then select "Manage Dissertations" from the upper toolbar.  Then select "Batch revise Excel" from the left-side toolbar.  Then "Generate" if the most recently generated Spreadsheet is out of date, else "Download".  Repeat this for each of the three source repos.

Alternately, you could receive this spreadsheet from the DigitalCommons admin at the Graduate School.

Filter out the items in the source spreadsheets using whatever criteria.  Probably "select those items listed as published since X date" but possibly another criteria.

Previous filters have involved comparing against items already in the catalog to eliminate items present in Symphony.  This is difficult to do exactly because the cataloger will enter into Symphony the title/author seen on the actual document instead of using the DigitalCommons data.  It may be better to select for conversion only those items with a 'published date' after some cutoff.

If you persist in wishing to compare against item already in Symphony:  use Workflows to export the theses/disserations already in Symphony.  Run a Report: Schedule New Report: Bibliographic: List Bibliography: {Item Selection: {Item category 1: [DISS, E-DISS, E-THESIS, THESIS], In the shadow catalog: No}, Print Item: {Output format: Pipe Delimited}}   Then edit this file to shape it into a csv 

When you have the spreadsheets containing only items you wish to migrate to Symphony, convert these spreadsheets into xlsx format and name the sheets "1".  Use these files as your source filepaths in the jupyter notebook script "ConvertingTheses.ipynb".  Execute each cell in the notebook, and look for output *.mrc files in a folder 'output'.



