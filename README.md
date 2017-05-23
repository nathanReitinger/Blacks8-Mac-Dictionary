# Black's Legal Dictionary (8th) #

This is a beta version of a ".dictionary" version of black's legal dictionary (8th edition). This permits users to take advantage of the "lookup" function native to mac. For simple use, follow these steps: 

1. download the .dictionary
2. open the dictionary application
3. on the top menue, click "file" > "Open Dictionaries Folder"
4. put the .dictionary file in the folder you just opened
5. go back to the dictionary application, click "preferences" 
6. scroll down until you find "Blacks_8_[beta]" and check that box
7. you now have it! you can search for words in the dictionary, or use the three-finger tap 
<link to gif of three-finger>

<screen of program>

### TODO
- parse: ordinals, tenses, phonetics, and sub-definitions 
- clean: fix errors generated from scraping (how I obtained the dictionary) 

### Process

1. scrape from http://dictionary.sovereignconnection.com into pandas dataframe [sovereignconnection_scraper]
2. iterate through a dataframe and place terms and definitions in .xml format as a string, to export [build_dictionary]
3. compile apple dictionary with customized xml [compile]

### Notes 

double entries break dictionary compiling ==> after step 1, use excel to "remove duplicates" 
  - terminal looks like this: Duplicate entry_id: [PARENTAL-IMMUNITY DOCTRINE] at [the_path_goes_here]
  - source of error: if ( defined( $entryToBodyHash{ $entry_id } ) )   ...     {die "*** Duplicate entry_id: [$entry_id]";}     ...

XML formatting ==> at step 2 make sure to replace special characters 
<link to special characters>

### Resources
- http://blog.nagpals.com/cfwheels-dictionary/
- https://github.com/SebastianSzturo/Dictionary-Development-Kit