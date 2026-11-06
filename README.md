# RootsMagicPy gazetteer

This repository holds the files of the dated gazetteer that RootsMagicPy
downloads the first time a command needs it.  RootsMagicPy is a genealogy
program that reads and writes RootsMagic family files.  The files are
attached to the releases, one release for each build, and the repository
holds no code.

Each file is a SQLite database compressed with xz.  It records places with
dated statements of their names, their parents, their types, and the years
in which they existed.  A statement keeps its source's own ID where the
source gives one, so that a later build can be compared with an earlier one
statement by statement.

## Release 2026-11-05.2

This release also has only a new GOV file.  It leaves out the League of
Nations (`object_320423`) and the European Union with the communities
before it (`object_1176980`) as well as the United Nations, since GOV puts
each of these organizations above its member states in the same way.

| File | Source | Data as of | Places | Size | Unpacked | License |
|---|---|---|---|---|---|---|
| `gov.sqlite.xz` | GOV's web service | 3 Nov 2026 | 1,886 | 307 KB | 1.2 MB | CC BY-SA 4.0 |

```
2f2efecf4b2dc78982a428c12c75c3d76a45317668835ebcfc3e01c3e7da9218  gov.sqlite.xz
```

## Release 2026-11-05.1

This release has only a new GOV file, and the program takes the Wikidata
file from release 2026-11-05.  GOV records the United Nations
(`object_1285561`) as a "confederation" that 31 countries have been part of
since 1945, and no address includes it, so the build leaves out the object
and every statement that names it as a parent.

| File | Source | Data as of | Places | Size | Unpacked | License |
|---|---|---|---|---|---|---|
| `gov.sqlite.xz` | GOV's web service | 3 Nov 2026 | 1,888 | 308 KB | 1.2 MB | CC BY-SA 4.0 |

```
ee1b225845ebdfb4e2ffa7e70ef27725527fab55cbf82301d7927e905deb2c80  gov.sqlite.xz
```

## Release 2026-11-05

| File | Source | Data as of | Places | Size | Unpacked | License |
|---|---|---|---|---|---|---|
| `wikidata.sqlite.xz` | Wikidata's JSON dump | 27 Oct 2026 | 4,739,486 | 1.03 GB | 3.68 GB | CC0 1.0 |
| `gov.sqlite.xz` | GOV's web service | 3 Nov 2026 | 1,889 | 310 KB | 1.2 MB | CC BY-SA 4.0 |

The SHA-256 hashes of the files are these.

```
3c073e599e3feabc85bcafbcfec4073f1931495b4e403dca54f33028530e3fbb  wikidata.sqlite.xz
e280330c0b1a9728388b4122b4535d98378ed9a33aa887e5b2a74d169d2d5b6b  gov.sqlite.xz
```

## Wikidata

The Wikidata file is built from Wikidata's full JSON dump,
`latest-all.json.gz` of 27 Oct 2026.  It keeps the items that are instances
of a human settlement, an administrative territorial entity, a historical
region, a country, a historical country, a cemetery, a church building, or
a hospital, or of a subclass of one of them.  A place's names are its
labels in 30 languages, most of them European, and its official and native
names with their dates.  Its parents are its "located in the administrative
territorial entity" statements with their start and end dates, or its
country when it has none.

Wikidata's data is under the
[CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/)
dedication, and so is this file.  RootsMagicPy shows the credit "Data from
Wikidata (https://www.wikidata.org), CC0, as of 2026-10-27."

## GOV

The GOV file holds objects of the Geschichtliches Ortsverzeichnis (GOV) of
the Verein für Computergenealogie e. V.  They were fetched through GOV's
web service, and they are the objects that the places of a set of family
files name together with every object above them.  The file has GOV's
objects in the gazetteer's tables, with GOV's types mapped to RootsMagicPy's
place types.

GOV's data is licensed under
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), as the
[GOV web service's page](https://wiki.genealogy.net/GOV/Webservice) states
in its section "Lizenz".  This file is an adaptation of that data and is
under the same license, so an adaptation of this file must be under CC BY-SA
4.0 as well.  The Verein für Computergenealogie asks for this credit, which
RootsMagicPy shows.

> Nutzt Daten des Geschichtlichen Ortsverzeichnisses GOV
> (http://gov.genealogy.net) des Vereins für Computergenealogie e. V.
> (http://compgen.de) in der Version vom 2026-11-03.
