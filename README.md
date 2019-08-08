A set of tables extracted from the [Stars without Number: Revised Edition](https://www.drivethrurpg.com/product/226996/Stars-Without-Number-Revised-Edition?affiliate_id=318171). These tables are formatted for use with `[gm-notepad](//github.com/jeremyf/gm-notepad)`.

The included tables are also found in [Stars without Number: Revised Edition (Free Version)](https://www.drivethrurpg.com/product/226996/Stars-Without-Number-Revised-Edition?affiliate_id=318171).

To use these tables with `gm-notepad`, you'll need to clone this repository and run `gm-notepad` with the following parameters:

```console
gm-notepad \
  --path=<path-to-this-cloned-repository> \
  --delimiter="\t" \
  --table_extension=".tsv"
```

There are a lot of sub-tables in the data directory. The following tables are "containers" for either resolving a One Roll entry or for generating a tag.

In `gm-notepad` type the following to see the a random result:

```console
{npc}
{patron}
{planetary-tag}
{urban-encounter}
{wilderness-encounter}
```
