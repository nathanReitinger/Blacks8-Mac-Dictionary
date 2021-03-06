# Black's Legal Dictionary (8th) [beta]


![screen](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/blob/master/media/screen.png) 

This is a ".dictionary" version of black's legal dictionary (8th edition). It permits users to take advantage of the "lookup" function native to mac. The definitions are not yet fully parsed (i.e., definitions appear as block text instead of parsed tenses, sub-definitions, and phonetic break-outs); however,  this does give a good preview of how the dictionary works. 

For simple install and use, follow these steps: 

1. download the .dictionary <[link to dictionary](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/tree/master/dictionary(download))>
2. open your own dictionary application
3. on the top menu, click "file" then "Open Dictionaries Folder"
4. put the .dictionary file you just downloaded into the folder you just opened
5. go back to your dictionary application, click "preferences" 
6. scroll down until you find "Blacks_8_[beta]" and check that box
7. you now have it! you can search for words in the dictionary, or use the three-finger tap 

![three-finger tap](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/blob/master/media/three_finger_tap.gif)

### TODO
- parse: ordinals, tenses, phonetics, and sub-definitions 
- clean: fix errors generated from scraping (how I obtained the dictionary) 

### Process

1. scrape from <[sovereign connection dictionary](http://dictionary.sovereignconnection.com)> into pandas dataframe <[scraper](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/blob/master/code/scraper)>
2. iterate through a dataframe and place terms and definitions in .xml format as a string, to export <[build](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/blob/master/code/build)>
3. compile apple dictionary with xml text produced in step 2 <[dictionary(source)](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/tree/master/dictionary(source%20code))>

### Notes 

double entries break dictionary compiling ==> after step 1, use excel to "remove duplicates" 
  - terminal returns: Duplicate entry_id: [PARENTAL-IMMUNITY DOCTRINE] at [the_path_goes_here]
  - source from path: if ( defined( $entryToBodyHash{ $entry_id } ) )   ...     {die "*** Duplicate entry_id: [$entry_id]";}     ...

XML formatting ==> at step 2, replace special [characters](https://github.com/nathanReitinger/Blacks8-Mac-Dictionary/blob/master/media/xml%20special%20characters.png)

### Resources
- http://blog.nagpals.com/cfwheels-dictionary/
- https://github.com/SebastianSzturo/Dictionary-Development-Kit
