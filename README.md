# MARC Geographic Areas – Wikidata mappings

Trove uses codes from the [MARC Geographic Areas list](https://www.loc.gov/marc/geoareas/gacs_code.html) to identify locations in metadata records. I couldn't find any mappings of these codes to other sources of geospatial information, so I fired up [OpenRefine](https://openrefine.org/) and reconciled the geographic area names against [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page). Once I'd linked as many as possible, I copied additional information from Wikidata, such as [ISO country codes](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_code), [GeoNames](https://www.geonames.org/) identifiers, and geographic coordinates.

I've saved the resulting dataset in two formats – as a flattened CSV file (handy for loading as a dataframe), and as a JSON file that uses the geographic area codes as keys (handy for looking up values). I've also written the codes back into the Wikidata records, so you can now find them with a [SPARQL query like this](https://w.wiki/8iKM).

The columns in the CSV file are:

- `code` – MARC geographic areas code (without any trailing dashes)
- `place` – name of geographic area from the MARC list
- `wikidata_label` – name of geographic area from Wikidata
- `wikidata_id` – Wikidata identifier
- `coordinates` – pair of decimal coordinates in the form `latitude,longitude` (multiple values are pipe `|` separated) 
- `iso_country_code` – ISO two letter country code (multiple values are pipe `|` separated) 
- `iso_numeric_country_code` – ISO numeric country code (multiple values are pipe `|` separated)
- `geonames_id` – GeoNames identifier (multiple values are pipe `|` separated)

Note that some fields can contain multiple values. For example the area `Mediterranean Region` is linked to 22 countries, so there will be multiple values in the ISO code fields.

For an example of this dataset in use, see [Which countries do the oral histories relate to?](https://tdg.glam-workbench.net/other-digitised-resources/oral-histories/overview.html#which-countries-do-the-oral-histories-relate-to) in the *Trove Data Guide*.

----

Compiled by [Tim Sherratt](https://timsherratt.au), December 2023