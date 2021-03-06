#Import data from source geonames.org

VERSION 1.0.2  
DEVELOPMENT date 2014-11-15  

About [geonames.org](http://www.geonames.org/about.html).  

Process `import data` consist of two stages:  
- **downloading** data from external geonames.org  
- **importing** data into the internal MySQL database  

###DOWNLOADING data

External data urls:
* [all dumps](http://download.geonames.org/export/dump)
* [postal codes](http://download.geonames.org/export/zip)

For downloading external data - call the next shell script with option `--whole`
```bash
$ bash ./shell/download.sh --whole
```

For running shell script with other options see descriptions.
Just run without options - and see descriptions about all available options
```bash
$ bash ./shell/download.sh
```

###IMPORT data

For importing external data - call the next shell script with option `-a import-data`
and database options `-u username -p password`
```bash
$ bash ./shell/import.sh -a import-data -u username -p password
```

For running shell script with other options see descriptions.
Just run without options - and see descriptions about all available options
```bash
$ bash ./shell/import.sh
```

##Additionaly
Total disk space used for downloaded data:
```bash
$ du
376M ./data/zip  
1.6G ./data/txt  
2.0G ./data  
```
Total disk space used for unpacked data
```bash
$ ls -lh ./data/txt
total 1.6G
 136K admin1CodesASCII.txt
 1.9M admin2Codes.txt
 1.2G allCountries.txt
 349M alternateNames.txt
  143 continents.txt
  31K countryInfo.txt
 719K dependencies.txt
  56K featureCodes_en.txt
 6.0M hierarchy.txt
 125K iso-languagecodes.txt
  76M postalCodes.txt
  14K timeZones.txt
```
Total disk space used for zipped data [temporary]
```bash
$ ls -lh ./data/zip
total 376M
 269M allCountries.zip
  95M alternateNames.zip
 1.3M hierarchy.zip
 178K no-country.zip
  11M postalCodes.zip
```
