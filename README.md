# Notebook 4
## Ciana Tzuo

## Reflection
### What changes between live and archived data?

Live data comes directly from the API and may change over time, while archived data is a saved version that stays the same. In my notebook, I used live PokéAPI data for Contest Types and Currencies and compared it with saved JSON fixtures. Live data depends on the API and internet connection, while the fixtures allow me to access the same data even when the API is unavailable.

### Which check prevents the most misleading failure?

I think the dictionary-key validation is the most important because it checks whether the API response contains the information my code needs. For example, my `validate_contest_data()` function checks that `berry_flavor` contains both `name` and `url`. If either is missing, the function raises a `ValueError` instead of continuing with incomplete data. I also check the lengths of the `names` lists for both endpoints to make sure they match the saved fixtures.

### How does caching support respectful use and reproducibility?

Caching lets me reuse saved API data instead of making unnecessary requests to the server. This reduces traffic to PokéAPI and makes my notebook more reliable. In my notebook, setting `use_live=False` loads the fixtures directly, and if a live request fails, the functions automatically fall back to the saved data.