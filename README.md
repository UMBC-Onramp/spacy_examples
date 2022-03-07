# spacy_examples

notebooks and scripts showing how to use SpaCy for simple NLP tasks

SpaCy is an open-source software library for advanced natural language processing, written in the programming languages Python and Cython.  SpaCy focuses on providing software for production usage.

### spacy101.ipynb and spacy102.ipynb

These cover some of the basic NLP tasks with SpaCy

### [entityRulerExamples.ipynb](https://github.com/UMBC-Onramp/spacy_examples/blob/main/entityRulerExamples.ipynb)

This demonstrates how we can use SpaCy's entityRuler pipeline component to recognize entity types using regular expressions (e.g., URLs), simple patterns (e.g., network port references), and enumerated or partly enumerated types (e.g., malware types, malware names, threat actors).

The data for creating entityRuler patterns for enumerated types is extracted from Wikidata.  For example, querying for malware instances, we find over 250.  for each one we record its canonical name (e.g., Stuxnet), how many wikipedia sites have a page about it (37) which provides a simple measure of its prominence, a a list of its aliases (e.g., RootkitTmphider,W32.Stuxnet,   W32.Temphid).  See the [data](https://github.com/UMBC-Onramp/spacy_examples/blob/main/data/Q14001.tsv) on github.  

There's also an example that creates the text for the entityRuler using data like this. and a short paragraph showing the results on some text.

One issue is how to use this with models trained from human annotations.  Also, we'd like to find a way to use the EntityRuler results as data for the training.  I'm sure we can find a way.

### [entity_names_text.ipynb](https://github.com/UMBC-Onramp/spacy_examples/blob/main/entityRulerExamples.ipynb)

This notebook has examples of code for extracting data and text from wikidata and DBpedia to help create the entityRuler elements and also as text for human annotation and/or fine tuning large language models.

We can identify Wikidata types that match our Cybersecurity types, find all of their Wikidata instances, and get the DBpedia abstract for each.  Dbpedia's abstract is usually for first paragraphs or several paragraphs of a Wikipedia article,  For example, the abstract of the Cozy Bear threat actor is

> Cozy Bear, classified by the United States federal government as advanced persistent threat APT29, is a Russian hacker group believed to be associated with one or more intelligence agencies of Russia. The Dutch General Intelligence and Security Service (AIVD) deduced from security camera footage that it is led by the Russian Foreign Intelligence Service (SVR); this view is shared by the United States. Cybersecurity firm CrowdStrike also previously suggested that it may be associated with either the Russian Federal Security Service (FSB) or SVR. The group has been given various nicknames by other cybersecurity firms, including CozyCar, CozyDuke (by F-Secure), Dark Halo, The Dukes (by Volexity), NOBELIUM, Office Monkeys, StellarParticle, UNC2452, and YTTRIUM. On 20 December 2020, it was reported that CozyBear was responsible for a cyber attack on US sovereign national data, believed to be at the direction of the Russian government.

### [Data](https://github.com/UMBC-Onramp/spacy_examples/tree/main/data)

This directory as some of the small sample datasets created by the examples in the notebooks. I believe the process is fast, though querying DBpedia seems to be very slow, but I think that is because it sometimes is ona weekend when they updating the system and data.
