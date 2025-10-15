# Learning-Wikidata
This is a Wikidata Learning Hub, where concepts, ideas and tutorials are stored.
## Index
- About Wikidata
- Some Statistics
- Wikidata Timeline
- Some useful links
- Get started
- The editing
- How's data structured?
- How's this working in Wikidata?
- Let's edit!
- How to interact with the machine? SPARQL and Wikidata Query Service WDS)
- Let's query!

## About Wikidata
Wikidata is a free and open knowledge base that can be read and edited by both humans and machines.
It acts as central storage for the structured data of its Wikimedia sister projects including Wikipedia, Wikivoyage, Wiktionary, Wikisource, and others.
This knowledge base also provides support to many other sites and services beyond just Wikimedia projects! The content of Wikidata is available under a free license, exported using standard formats, and can be interlinked to other open data sets on the linked data web.
So to sum up, Wikidata is: 
- a repository of the world's knowledge
- a database anyone can read and edit since it's free and multilingual

## Some statistics
Bots perform nearly half of all edits on Wikimedia projects, with a similar proportion of Wikidata's total edits made by bots and human editors. While bots handle a large volume of tasks like adding statements, labels, and descriptions, humans perform more complex and creative work. Bots are also more involved in smaller language communities where they can contribute over 50% of the edits. 
The majority of the editing concerns scholarly articles and miscellaneous topics. A great chart suming up all the topics in Wikidata can be found in https://www.wikidata.org/wiki/Wikidata:Statistics.

## Wikidata timeline
The Wikidata project officially began on October 29, 2012, but its conception dates back to 2005. During that period, the technological landscape was rapidly evolving, and the idea of a Semantic Wikipedia was born. At Wikimania 2005 in Frankfurt, doctoral students Markus Krötzsch, Max Völkel, and Denny Vrandečić, recently involved in Semantic Web research, exchanged ideas that led to the vision of a system capable of connecting entities through typed links, specifying the nature of relationships between them. This early concept laid the groundwork for what would become Wikidata: a structured, machine-readable knowledge base linked to human-readable content on Wikipedia. Over the following years, the development of Semantic MediaWiki (SMW) and its query interfaces allowed for structured data collection and inspired external projects, despite occasional tensions with the Wikimedia Foundation. By February 2011, at a Wikimedia Data Summit in Sebastopol, Vrandečić was tasked with drafting a formal proposal, initially named data.wikimedia.org. The project received funding from the Wikimedia Foundation and other sponsors, and Wikidata was launched with a system of alphanumeric identifiers, beginning with Q1 for the universe, Q2 for Earth, Q3 for life, and so on. From 2013 to 2015, the platform expanded with community contributions, introducing properties and statements, while key tools like QuickStatements and Mix’n’Match facilitated the efficient import and linking of data, establishing Wikidata as a structured, multilingual knowledge repository.

## Some useful links
To get started in Wikidata one should browse a bit through the website and find out more about Wikidata Projects that span from Astrophisics to Politics, from Biographies to Classics and so forth, and give a first glance to the structure of the Wikidata Community, which is more and more spread every day. Some useful links to start are down below, but I'd recommend to expand the research to what might interest the reader. Some of the topics here listed are not meant to be explored as soon as the user gets started, but are either useful recomendation throughout the process of learning or Wikidata documentations on which I based this Learning Hub.
- A (very) general (but official) introduction to Wikidata: https://www.wikidata.org/wiki/Wikidata:Introduction
- A guide to import data: https://www.wikidata.org/wiki/Wikidata:Data_Import_Guide
- Wikidata Tours with some activities (more to come soon): https://www.wikidata.org/wiki/Wikidata:Tours
- Click on 'Random Item' on the side bar to explore items
- SPARQL language (the one you'll get to know in the next chapters): https://www.wikidata.org/wiki/Wikidata:SPARQL_tutorial
- The Wikidata Query Service to make your own queries (we'll use it the 'Let's query' Chapter: https://query.wikidata.org/
- Some exaples of Projects in Wikidata (Digital Himanities):
  - IDEA on Dura Europos inscriptions: https://www.wikidata.org/wiki/Wikidata:WikiProject_IDEA
  - ALtinum on Altinum inscriptions: https://www.wikidata.org/wiki/User:Anna_Clara_Maniero_Azzolini/Altinum
  - Testi Latini: https://www.wikidata.org/wiki/Wikidata%3ATesti_latini
  - Ancient Greece: https://www.wikidata.org/wiki/Wikidata%3AWikiProject_Ancient_Greece
  - On Wikibase (the difference between Wikibase and Wikidata will be better explain in other chapters) Greek Metrical Inscriptions: https://wiki.digitalclassicist.org/Greek_Metrical_Inscriptions

## Get started
The next steps are the following:
1. Create a new account: https://auth.wikimedia.org/wikidatawiki/wiki/Special:CreateAccount?useformat=desktop&usesul3=1%C2%A2ralauthLoginToken=3bd4a84af90943527477e13a18bab57c
2. Add a babel (or the languages the user is confident with so to clarify in which language the edits are to be made): https://en.wikipedia.org/wiki/Wikipedia:Babel#Instructions
3. Start editing with "create a new item" to put oneself to the test: https://www.wikidata.org/wiki/Special:NewItem

## The editing
There are two tipes of editing, one is the manual editing and the other is the masss editing. The first is done directly via the Wikidata interface, allowing for precise, context-aware contributions. Editors can verify sources, correct details, and add nuanced data. Though slower than automated methods, it ensures semantic accuracy and reflects Wikidata’s collaborative and human-centered approach. The latter refers to large-scale data updates using tools like QuickStatements, OpenRefine, or bots. It enables fast and consistent integration of datasets across many items, supporting institutional and research projects. This method boosts efficiency but requires strict adherence to data models and community guidelines to maintain quality and avoid duplication.

## How's data structured?
Though not strictly necessary to the basic knowledge of editing, I argue that it is still important to know how the data we want to add into the database are to be stored. To understand this, we need to take a step back. The data is structured in triples following the Resource Descriptive Framework (RDF). So, as we all speak a language with a subject, a predicate and an object, we must consider this structure as a proper grammar connection. Moreover, the links between those nodes are logical, that is I cannot say anything that contradicts the logical rules (otherwise I would violate the contraints, as will be discussed later on). For instance, as one cannot say "The color of the river is mother" - obviously the interlocutor would expect to hear a color and not a family member, a database will exclude this statement as logical.

<img width="630" height="327" alt="Wikidata Editing" src="https://github.com/user-attachments/assets/9227e4ff-c48e-4441-85b5-4257efef0dde" />

## How's this working in Wikidata?
At this point, it is easy to understand that the word "river" we used in teh previous example alone does not constitute a readable element of the statement for the machine, but only for the human brain. That word must correspond to a machine-readable code. First, we call item the part of the statement that has thw roleof subject, then property the predicate and value the object (that is in other circumstances an item in turn). Second, in Wikidata a unique identifier is given to both items and properties, respectively a Q+number and a P+number IDs. Let us now make a sentence machine-readable in Wikidata: Charles Dickens is friend of Elizabeth Gaskell.

<img width="1004" height="392" alt="immagine" src="https://github.com/user-attachments/assets/cfd1367d-6f64-4879-a7cd-93c5f1b88cb8" />

So every item in Wikidata has or will have an ID, that is if an item can't be found it's patiently waiting for someone to add it. 
When we look for an item in Wikidata (I'd rather say item than word for personal nouns and so forth are included), i.e. J. R. R. Tolkien not only may we find a proper description, but also aliases (in this case, other names he might be known and browsed with, such as nicknames), translations, and all the statement we talked about. One of the statement we find connected to this item is "Tolkien was born in Bloemfontein". This is how it appears to human readers:

<img width="1251" height="247" alt="immagine" src="https://github.com/user-attachments/assets/8b912115-4f08-40ed-9eae-24e84d210d10" />

Thus, the writer is the actual subject of the statement (read by the machine as Q892), then the "place of birth" (P19) serves as predicate/property, and finally Bloemfontein (Q37701) serves as object/value. We can add more information to this statement (just as in a natural languace speech one can add more predicates and objects connected to a single subject). And in the same way, we can add in this very statement some references (that make the data more scientific to the community, as it can be verified), or dates and so forth.

## Let's edit!
Here is a recorded tutorial on how to add an item properly. This is all part of the manual editing.

[Creating an item.zip](https://github.com/user-attachments/files/22928571/Creating.an.item.zip)





