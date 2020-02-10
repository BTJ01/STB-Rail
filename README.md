# STB-Rail-Commodity
There are 7 major rail companies in the United States & Canada:

 BNSF - CSX - GTC - KCS - NS - SOO - UP

Commodity data for all carriers is available on the [Surface Transportation Board website](https://www.stb.gov/econdata.nsf/M%20Statistics%20of%20Class%201%20Feight%20RR?OpenPage&Start=1&Count=300&Collapse=10.7). 

Data is available back to 2006, but is in `.PDF` format until 2013 when it changes to `.XLS(X)` format. There are four quarterly and one annual reports per year per carrier. I manually downloaded all 32 reports from 2013 through Q2 2019 for each carrier to play around. They were all a little different and most had unique problems so I wrote a script to clean the data from each carrier. This data was a perfect project to practice data cleaning for several reasons:

- Some carrier's commodity codes had lost the leading zero
     - not all codes have a leading zero so I needed a pattern to decide when to add them
- There were lots of extra columns and formatting remnants from excel to deal with
- Some columns had commas, tick marks, hyphens, etc. in the data that had to be removed
- Formatting changed even for the same carrier over time

Some things I learned from the process include:
1. Unsurprisingly, the scripts ended up very similar - I realized I could just write one to automate cleaning if I was careful to account for their nuances. 
2. There's no need to convert from `.XLS(X)` to `.CSV` before cleaning! For some reason I thought this was a necessary step but it's really just a waste, R handles Excel files just fine.
3. Iteratively testing a complex solution in bite sized pieces makes a much easier and faster approach to solving complex problems
4. R has an incredible amount of quality resources - packages, community support, tutorials, etc. - that helped me immensely with certain aspects of this project.


After working through cleaning the historic rail data, I started putting `STB-Rail-Update.R` together using the scripts I made for each carrier as reminders of what to watch out for and guidance to improve.
