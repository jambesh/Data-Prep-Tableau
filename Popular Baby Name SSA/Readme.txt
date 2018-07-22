Objective :
Wanted to find which Baby name famous in USA ?
Where to get data ? 
SSA maintain the names from 1880 in  SSA website https://www.ssa.gov/oact/babynames/limits.html.
Download the national data(7MB) , which will download the file in .zip format in names.zip  and contain data from 1880.
Why we need cleanup and what is the problem in the files?

1) All the files  are in the format  <font color=red>yobXXXX.txt</font> ,contain the data for year mentioned in file name.
2) Each file contain three fields:  The name, the gender (M or F)  and the number of babies of that gender  for the year mentioned 
in the file name.

Challenges:
As Year is part of file name and not part of data in file name, If we have to find a particular name trend over the year
(how popular a name is) we first need to parse each of the 100+ file and extract the name and then have the year concat to the file content.

Solution:
While this can be done using Python/R through a scrip 
1 ) Read each of the file
2) Extract the  year from the file name
3) Append the year to the content of the file like :  YEAR:NAME:GENDER:NUMBER OF BABY OF THAT GENDER IN THAT YEAR

Will do it using Tableau Prep :
1) Open Tableau Prep.
2) Unzip the names.zip file that was downloaded from SSA website.
3) Connect to text file and use "Multiple file with pattern" - this will scan all the files in the name directory as all file 
have similar naming convention.
4) Pivot the data 
5) Rename the fields appropiately (Name,Gender,Count) 
6) Bringing the Year from file name to the content : - parse the field that filename  ( 1- remove the letters this will leave year. 2)
split the field and it will leave year in one field...)
7) rename the year field and remove the unwanted field .
8) Run the flow to produce output in CSV or tde or Hyper file which Tableau can directly open and start analyze.


