# Maria Sek Reflection

## What changes between live and archived data? 
Live data changes over time, while archived (fixture) data always stays static. In my notebook, I use the live API to get current data, while the fixture files "charizardapi.json" and "bulbasaurapi.json" are what we use for archived data in case we need something to fall back on.

## Which check prevents the most misleading failure? 
The specific check that prevents the most misleading failure is subjective, but if I had to choose I would say the schema and type checks. For example, in my notebook, I use schema and type checks to check whether the required Pokemon fields exist, that sprites is a dictionary, that abilities is a list, and more. Without these checks, later steps using DataFrames might not work as they are using missing or incorrectly structured data.

## How does caching support respectful use and reproducibility?

Caching supports respectful API use because through caching it is no longer necessary to keep requesting live API data repeatedly, which can use unnecessary server resources. It also supports reproducibility as the notebook can be run even without access to any live API.