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
- How to interact with the machine? SPARQL and Wikidata Query Service (WDS)
- Let's query!

## About Wikidata
Wikidata is a free and open knowledge base that can be read and edited by both humans and machines. It acts as central storage for the structured data of its Wikimedia sister projects including Wikipedia, Wikivoyage, Wiktionary, Wikisource, and others.  
This knowledge base also provides support to many other sites and services beyond just Wikimedia projects! The content of Wikidata is available under a free license, exported using standard formats, and can be interlinked to other open data sets on the linked data web.  
So to sum up, Wikidata is: 
- a repository of the world's knowledge
- a database anyone can read and edit since it's free and multilingual

## Some statistics
Bots perform nearly half of all edits on Wikimedia projects, with a similar proportion of Wikidata's total edits made by bots and human editors. While bots handle a large volume of tasks like adding statements, labels, and descriptions, humans perform more complex and creative work. Bots are also more involved in smaller language communities where they can contribute over 50% of the edits. The majority of the editing concerns scholarly articles and miscellaneous topics. A great chart suming up all the topics in Wikidata can be found in https://www.wikidata.org/wiki/Wikidata:Statistics.

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

As shown, the user can add statements as desidered, including every field of knowledge. The user will then understand the impact Wikidata can have in those disciplines that extend their borders to other fields of research, as Epigraphy itself is about paleography, geology, archeology, history, prosopography and so forth. Had a property not been created yet, the procedure to add it would be more intricated than the item cration. One should "ask" the comunity to add it, and the few ones that are in charge of taking action will then add it (it sometimes take a bit of time, but the good news is that we don't add properties as often as we create items). The user may wonder the reason of such a difference in procedures. The keyword is "coherence". Let us imagine creating a new property stating that one "is friend" of another. There are many types of friendship (and the concept has certainly changed over time), so one could state that "Charles Dickens was friend of Elizabeth Gaskell". Then, a a second user might have coded some of Dickens' relationships not as "friend to" as "significant person to". Finally a third user may want to query these data and investigate the relationships that Dickens had with others and it would be difficult to add evry type of relantionship in it. So what to do? We use the more general one (significant person) and then add as a qualifier the type of it (friend, lover).  
For those familiar to grammar syntax: while speaking, it is far better (and understandable) to add synonyms of objects rather than to add multiple verbs connected to a single object.

## How to interact with the machine?
Let us now understand how these data are to be retrieved once they've been put into the databased. We use the verb 'query' because that's what indeed we are tryong to do: ask the machine something about data it already has. We could ask for a special visualization: let us imagine putting all the English authors lived in a certain time period. If we want to investigate how many of them died in a certain year or married in their thirties, doing it manually on our own would be a too time-consuming task. And that's where the machine comes to our aid. We can ask it to do this task in a few seconds, exploring how many authors one can think of (obviously, the more data we query the more time the machine will take to give a certain result). Moreover, we could then visualize the answer in many ways, as genealogical trees, timelines, tables, graphs and charts and so one. The great scientific potential speaks for itself. But how are we to speak to a machine? We need to use a ceertain language code, called SPARQL (pronounced like _sparkle_) and use a specific tool for the querying, the [Wikidata Query Service](https://query.wikidata.org/). An explanation on how to use it follows.  
As an example, let us ask the database a simple question: “How many writers have the name Charles?” expressed in RDF and SPARQL. A SPARQL query always includes some basic components — here we will use the most common ones: SELECT and WHERE. SELECT specifies the variables we want to retrieve, each preceded by a question mark. For example:
`SELECT ?person`
Although our natural-language question uses a plural (“writers”), in SPARQL the variable name is singular; the machine will automatically return all matching instances.
Next comes the WHERE section, where we define what each variable represents and the conditions it must meet. In our case, ?person must have two properties: “occupation: writer” and “given name: Charles.”
```
SELECT ?person
WHERE {
  ?person wdt:P106 wd:Q36180.
  ?person wdt:P735 wd:Q2958359.
}
```
Each statement follows the subject–predicate–object (SVO) structure, which in SPARQL is not reversible: the first element is always the subject, followed by a property (introduced by the prefix wdt:), and finally by an object (introduced by wd:).
If we instead wanted to know where Goethe died, the subject would be known and the object unknown, so the query would reverse the variable position:
```
SELECT ?placeOfDeath WHERE {
  wd:Q5879 wdt:P20 ?placeOfDeath.
}
```
To make the results more readable, we can ask for human labels (not just IDs) by adding ?personLabel to the SELECT clause and a service line specifying the preferred language.
```
SELECT ?person ?personLabel
WHERE {
  ?person wdt:P106 wd:Q36180.
  ?person wdt:P735 wd:Q2958359.
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE]". }
}
```
By default, [AUTO_LANGUAGE] retrieves results in the user interface language (e.g., Italian if the WDQS interface is in Italian). You can also specify another language directly, such as "en".
`SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }`  
This final query returns 1,807 results, taking slightly longer to execute than the simpler version without labels.

## Let's query!
So here's some examples on how to query certain types of data. First we will consider a very basic query, then, as soon as we need other details to be investigated, we will add some more information to our query such as time periods and coordinates.  
Before stepping into the querying process, I need to make some remarks. Presently, Wikidata is not meant to be used as a search engine in the most general sense. I have tried myself to investigate banal things such as how many Archbishops of Canterbury have there been or how many women were accused on witchcraft in Scotland. Is is hard to obtain a result that approximates reality. The reason why is that we all think in many different ways and some items or properties ora values may have been identified in different ways: Some individuals ‘hold the position’ of archbishop, others have this role connected to property “occupation”, and still others are even archbishops with the qualifier ‘Canterbury’. So my recomendation is to use a good search engine for questions we don't know how to formulate (queries that can't be build without adding an infinite number of specifications). So it is better to know a project we want to investigate (there are plenty of them!), see how it was built and which properties/items/values were used to describe a statement. A research question about scotland witchcraft could be well answered by the [WikiProject Scotland's Accused Witches](https://www.wikidata.org/wiki/Wikidata:WikiProject_Scotland%27s_Accused_Witches/Queries) (and notice, some of these broad projects come with a query suggestions page too).
In other words, Wikidata is meant for researchers, and it is assumed that a researcher knows the 'domain' of the question.

