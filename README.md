# Notebook 4
## Isabella Bartoletti

### Reflection Questions: 
### What changes between live and archived data? 
Archived data (also known as a fixture) acts as a saved copy of data on your computer, so it will give the same result on every run. Conversely, live data updates according to the server on a regular basis (i.e. today). A fixture should always work, whereas a live request can fail if the requesed API address is incorrect or if the endpoint on longer exists (giving you `HTTP 404`). Also, the live data may be regularly updated, whereas the archived data is static.


### Which check prevents the most misleading failure?
I believe that the validation check (right before data acquistion) prevents misleading failure. In the `acquire()` function, a request can technically succeed with a `200` HTTP status, yet it still may return wrong or incomplete data missing certain fields. The validate payload functions catch this failure beforehand.

### How does caching support respectful use and reproducibility?
We learned that caching prevents you from repeatedly requesting and accessing from an API, over and over and over again. Instead over overloading the server with many requests, we can cache, or store temporary copies of data so they can be retrieved with high-speed.

In this notebook, there is an option to set `use_live` = `True` or `False` (I set to `True` for now because that is what you instructed us to do). However, if someone wanted to use this code in the future, they could set `use_live = False` so that PokeAPI does not need to handle unnecessary requests or experience heavy server traffic. This overall promotes respectful use.

This also helps with reproducibility, because anyone with my notebook and the same fixtures would get the same resulting tables, even if the API changes later.


