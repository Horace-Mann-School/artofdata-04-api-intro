# Notebook 4
## Dilan Shah

### What changes between live and archived data? 
Archive data is the copy of the data from the API which is saved directly to your computer from the time you saved it. In this case, it was stored as a json file. Live data is connected to a server and is 'live' because it updates and refreshes regularly. Archived data is stored on your computer so it cannot be affected by a server being shutdown or an endpoint not being requested correctly like live data. The `location-fixture` is archived data because I downloaded it from the PokeAPI website, while the endpoint `https://pokeapi.co/api/v2/location/canalave-city/` is live data. In the case of the PokeAPI, it is highly likely that nothing will change between the two because there isn't anything to regularly update when the data is fact-based. 

### Which check prevents the most misleading failure? 
The validation checking functions prevent misleading failure because the code will always stop if it cannot retrieve the API data or if there
is a HTTP status error. But, missing keys or incorrect values would still allow the code to run while the data would be wrong, which is a much bigger issue because it is harder to identify. In the case of this notebook, the `validate_location()` and `validate_color()` functions prevent the most misleading failures because they raise errors for problems that are not as obvious and wouldn't stop the code from running.

### How does caching support respectful use and reproducibility?
Requesting the data every time you use it would cost money for the people who run the PokeAPI, which is completely free for the user and doesn't require an API key to use. Caching is respectful because it avoids any unnecessary costs for PokeAPI and keeps the data from my analysis consistent so anyone could run the code at any point in time, regardless of the API updating the data or shutting down.