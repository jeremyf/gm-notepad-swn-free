A set of tables extracted from the [Stars without Number: Revised Edition](https://www.drivethrurpg.com/product/226996/Stars-Without-Number-Revised-Edition?affiliate_id=318171). These tables are formatted for use with [`gm-notepad`](//github.com/jeremyf/gm-notepad).

The included tables are also found in [Stars without Number: Revised Edition (Free Version)](https://www.drivethrurpg.com/product/230009/Stars-Without-Number-Revised-Edition-Free-Version?affiliate_id=318171).

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

## Diving Into a Table

Let's take a look at the [`npc` table](./data/npc.tsv)

```tsv
# One Roll Table for npc
#	Age {npc.age}
#	Most Obvious Character Trait {npc.most-obvious-character-trait}
#	Their Background {npc.their-background}
#	Their Biggest Problem {npc.their-biggest-problem}
#	Their Greatest Desire {npc.their-greatest-desire}
#	Their Role in Society {npc.their-role-in-society}
# Includes subtables:
1	Age:\t{npc.age}\nMost Obvious Character Trait:\t{npc.most-obvious-character-trait}\nTheir Background:\t{npc.their-background}\nTheir Biggest Problem:\t{npc.their-biggest-problem}\nTheir Greatest Desire:\t{npc.their-greatest-desire}\nTheir Role in Society:\t{npc.their-role-in-society}
```

This table has one entry, the line starting with `1`. I'm going to expand the control characters (e.g. `\n` and `\t`); The `gm-notepad` does the same expansion when it processes a table.

```tsv
Age:	{npc.age}
Most Obvious Character Trait:	{npc.most-obvious-character-trait}
Their Background:	{npc.their-background}
Their Biggest Problem:	{npc.their-biggest-problem}
Their Greatest Desire:	{npc.their-greatest-desire}
Their Role in Society:	{npc.their-role-in-society}
```

The `gm-notepad` further expands each `{npc.<sub-table>}` declaration by rolling on the corresponding table.

Let's dig a bit deeper into the [`{npc.their-background}` table](./data/npc.their-background.tsv).

```tsv
# One Role Entry for: npc (Their Background)
INDEX	Their Background
1	The local underclass or poorest natives
2	Common laborers or cube workers
3	Aspiring bourgeoise or upper class
4	The elite of this society
5	Minority or foreigner part of {npc.their-background[d4]}
6	Offworlder or exotic part of {npc.their-background[d4]}
```

Let's look at line 5:

```tsv
5	Minority or foreigner part of {npc.their-background[d4]}
```

When `gm-notepad` rolls a 5 on the `{npc.their-background}` table, it will then roll on the table again, but limit the possible results to entries 1 through 4.
