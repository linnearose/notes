## Embryo Options

	- read in .xlsx files in pandas
		> I knew there was also a way to load the data directly from an Excel doc instead of individually saving .csv files and then loading them.
		> 2 rows of null values that need to be dropped
		
	- check DOB from .xlsx files
		> I was wondering if manually saving the Excel tabs as .csv files first and THEN loading them in with Pandas caused any of the data to be "lost". Data types can be tricky and it's always important to check the original data type/format.
		> when looking at the SORTED date column in Excel, three suspicious dates pop up at the bottom of the sorted list:
			1. 11/6/65
				a. shows full date '11/6/4565' when you click on cell
				b. showing up at bottom of sort because the year is MUCH higher than any others - i.e. it's an invalid birth date
			2. 11/5/79
				a. shows full date '11/5/4579' when you click on cell
				b. showing up at bottom of sort because the year is MUCH higher than any others - i.e. it's an invalid birth date
			3. 11/14/1990
				a. when converted to dateimte, this date is NOT an issue which is why it didn't pop up in my python analysis
				b. showing up at bottom of sort because it's the only date where the year had 4 digits instead of 2	
					
	- check datatypes of zip code column
		> In Excel doc, certain zip code cells have little warning signs that inform you that that cell has been stored as TEXT instead of a NUMBER

		> In Python, when you check the datatype of the 'Zip' column, it also becomes apparent that some are stored as numbers and some as strings. If one were to do more digging into zip codes, you'd want to convert those all to the same datatype first. I would convert them all into string format. 
		> When you sort the Excel zip code column, you can also immediately see that there is a clear divide between the valid numbers and the strings, 
			a. some of the zip code strings are valid aside from datatype
			b. cities that are labeled as 'International' have zip code string '111111'
			c. as identified while using Python, one row has the Country abbreviation ('CA') in the Zip column instead of an actual zip code