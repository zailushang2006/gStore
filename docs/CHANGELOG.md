## Nov 06, 2015

We merge several classes(like Bstr) and adjust the project structure, as well as the debug system. 

In addition, most warnings are removed, except for warnings in Parser module, which is due to the use of ANTLR.

What is more, we change RangeValue module to Stream, and add Stream for ResultSet. We also better the gquery console, so now you can redirect query results to a specified file in the gsql console.

Unable to add Stream for IDlist due to complex operations, but this is not necessary. Realpath is used to supported soft links in the gquery console, but it not works in Gstore.(though works if not in Gstore)

- - -

## Oct 20, 2015

We add a gtest tool for utility, you can use it to query several datasets with their own queries.

In addition, gquery console is improved. Readline lib is used for input instead of fgets, and the gquery console can support commands history, modifying command and commands completion now.

What is more, we found and fix a bug in Database/(a pointer for debugging log is not set to NULL after fclose operation, so if you close one database and open another, the system will fail entirely because the system think that the debugging log is still open)

- - -

## Sep 25, 2015 

We implement the version of B+Tree, and replace the old one.

After testing on DBpedia, LUBM, and WatDiv benchmark, we conclude that the new BTree performs more efficient than
the old version. For the same triple file, the new version spends shorter time on executing gload command.

Besides, the new version can handle the long literal objects efficiently, while triples whose object's length exceeds 4096 bytes result in frequent inefficient split operations on the old version BTree. 

- - -

## Feb 2, 2015

We modify the RDF parser and SPARQL parser.

Under the new RDF parser, we also redesign the encode strategy, which reduces RDF file scanning times.

Now we can parse the standard SPARQL v1.1 grammar correctly, and can support basic graph pattern(BGP) SPARQL queries written by this standard grammar.

- - -

## Dec 11, 2014

We add API for C/CPP and JAVA.

- - -

## Nov 20, 2014

We share our gStore2.0 code as an open-source project under BSD license on github.
