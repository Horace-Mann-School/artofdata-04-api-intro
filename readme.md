# Notebook 4
## Jeremy Yao

What changes between live and archived data? 
Archived data is a snapshot of the data from whenever I took and stored it. Live data is taken fresh from the website, and might've been updated if my archived data is too old. For example, archived data from yesterday wouldn't have data on a pokemon released today. 

Which check prevents the most misleading failure? 
The schema check prevents the API from sending back data with missing/incorrect parts. This is the most misleading failure because everything else will run fine and just give me the wrong result. In other cases like a timeout, I won't be able to proceed and will know I have to fix something. Basically, a wrong output/result is worse than no output/result. 

How does caching support respectful use and reproducibility?
Requesting the same data over and over costs PokeAPI money each time, and for my purposes, caching it and oading it from api-fixtures each time is enough. Also, anyone with the artofdata-04-api-intro folder will automatically have the cached data and won't need to call it from PokeAPI again. 