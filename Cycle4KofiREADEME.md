# Cycle 4 — PokéAPI: Berry Flavors and Contest Types

This notebook gets data from the [PokéAPI](https://pokeapi.co/) `berry-flavor` and `contest-type` pages and puts it in a pandas DataFrame.

**To run:** `pip install requests pandas jupyter`, keep the `datasets/api-fixtures/` folder next to the notebook, and run all cells. Set `USE_LIVE = True` to use live data instead of the saved fixtures.

## How the data is retrieved, step by step

1. **Read the docs.** Both pages use a GET request with the name in the web address. No parameters or login.
2. **Set up.** The notebook sets the web addresses, an empty parameters box, and a `USE_LIVE` switch.
3. **Send the request.** In live mode, `requests.get` asks the website for data. It waits at most 10 seconds.
4. **Check the status.** `raise_for_status()` turns errors like 404 or 500 into a problem the code can catch.
5. **Read the JSON.** `response.json()` turns the reply into Python dictionaries and lists.
6. **Check the fields.** The code makes sure the fields we need are there.
7. **Use the fixture if something fails.** The notebook prints a message and uses the saved copy.
8. **Make DataFrames.** A loop goes through the berries and adds one row for each (flavor, berry, potency). The contest type gets its own small table. The two are joined (merged) on the flavor.
9. **Check the table.** The notebook checks the size, data types, missing values, repeats, and potency range.
10. **Write down the source.** A dictionary records where the data came from.

## Reflection

**What changes between live and archived data?**
Live data can change when PokéAPI updates it, so my results could be different on another day. My fixtures are saved copies (the `spicy` flavor with one berry, `rowap`, potency 10), so my notebook gives the same 1-row table every time. The downside is that the fixture is much smaller than the live data, so my average potency of 10.0 only comes from one berry. My provenance dictionary shows which one I used.

**Which check prevents the most misleading failure?**
Checking that the needed fields are there (`berries`, `contest_type`, `berry_flavor`). A reply can say "success" and still be missing data. Then my DataFrame could be empty or wrong and I wouldn't know. My DataFrame checks also helped: they showed 1 row, a whole-number `potency`, no missing values, and no repeats, so I knew the table was OK to use.

**How does caching help respectful use and reproducibility?**
My notebook uses saved fixtures by default, so it doesn't ask PokéAPI for data every time I run it. That is nicer to a free website. It also means anyone who runs my notebook gets the same 1-row result, and the fallback means it still works if the website is down.

## Attribution

Data from [PokéAPI](https://pokeapi.co/). Classroom use.
