# CA4009 Search Technologies

## Gareth Jones

**Resources**: _Introduction to Information Retrieval_ C.D Manning, P Ragheven, H. Schultz

How to Effciently identify & access useful info from collections of various media types

- why this is difficult - the challenges
- current tech
- how to test how well it works
- different media

**Information Retrieval** (IR): satisfy user's info need
- locate _relevant content_ - that which he user deems to completely/partially fulfil this need
- concerned with _unstructured info._ - found in natural language text/video. A majority of info out there is unstructured.
- lack of structure precludes use of traditional datavasse tech, we cannae use it. 
- Challenges..
  - eg photos can be searched based on _time_ and _location_, but can also use features such as _light status_ and _likely weather conditions_ etc.
  - "smart" design ideas such as mapping date to time periods ( weekend, midweek etc ), not "clever" since these are based on insights into what might be useful rather than being technically sophisticated.

---

## Module Outline:

- Hypertext, WWW, XML
- Text Retrieval
- Text Retrieval for web ( a combo )
- Information summarisation
- Semantic Search
- Recommended Systems - "you might like..", "customers who bought X also bought Y" etc
- Multimedia Information Retrieval - audio, speech&music, video, images etc

---

## Intro to Info Retrieval

IR systems seek to enable us to **locate information relevant to our needs** more _efficiently_ and _effectively_. Greatly reduce user efforet by directing them to potentially relvant materials with satisfactory info rather than using brute force reading all available materials.

Information can be _formally organised_ to assist manual searching.. can be

- Flat collection of homogeneous objects: library card catalogues, fies in a large directory, db records
- Hierarchial organisation (in manual info structuring): Filing cabines, docs with chapters, sections, subsection. The Dewey decimal system for classiication of books

This physical organisation can be efficient _if it is clear how to organise the info_. Howeve, it is **not often clear** how the info should be organised...

Use **cross referencing** to _associate information with multiple places_; links to related information of possible interest. Can be implemented with: footnotes, "see also" notes, post-its, encyclopedia references..

**Hypertextual linking**: an extended form of cross-references, multiple info links and no superimposed hierarchy, navigation by following links.

- links between WWW pages and within Wikipedia are egs.
- This method of info linking, seeking and navigation **does not scale**
- Links and structures are limited to the _specific intentions of the creator_ of the links. Often not worth the investment of creator to place all the links tht might be included.
- Larger/more complex structures begin to accrue absences of useful links, might not be possible to use these to locate entirely relvant content.
- ...**search** provides a means to _locate relevant info at arbitrary positions_ within these structures.

### History

- Date back to mid-1800s library systems - Dewey
- Automatic indexing and document abstracting began in 1950's - one of the _oldest applications of computers_. Computers used to search for manually labelled items and for items labelled automatically from title, abstract etc.
- in 1966, discovered that automatic indexing produced equivalent results to manual indexing - **huge**
- These IR systems were used exlusively by expert users (librarians) until WWW came along, now a ubiquitous tool used in day to day by millions. Need to become simple and fast to use.

**Information Retrieval is a needle in a haystack problem** - billions of docs on the web but only a small number are relevant to info need!

The only information available to IR system is the users **request/query**. These user information needs vary between..

- **Verificative** ("Is this correct") vs **Explorative** ("Tell me about ...")
- **Precise** ("Who directed X") vs **Vague** (open question)
- **Shifting** (live updates) vs **Static** (answer unchanging)

..Properly addressing these varied types require the IR system to _function differently for each one_

Information need arises from an **Anomolous State** of **Knowledge** (**ASK**), where the user realises that they have a need for information. The process of resolving an ASK is a _cognitive process on the part of the user_.

- conceptually trying to resolve an ASK makes I hard. Stated formally as the idea there is a **non-specifiability of need** problem.
- ASK means the user may not know or use language correctly to form an appropriate search request.. Users' models of information seekng are strongly influenced by systems. 
- this is a challenge for _all search engines_

On top of this, user search requests often contain too little, incorrect or too bloated information.

- 1% of users use advanced search facilities
- 10% use query syntax - usually incorrectly
- Average length of a search query is 2.5 words

### IR System Performance

Concerned with

- **Precision** -  fraction of _retrieved items that are relevant_
- **Recall** - fraction of _available existing relevant items hat have been retrieved_. Less important except in the case of patent search.

### Multimedia IR

Speech, music and video have a real-time temporal dimension; include acility to specify where in this dimension playback should begin

Music can be search based on signal processing to find similar items using music scores of MIDI representations

### Multilingual IR

English is now significantly <50% of all web content. Makes sense to search beyond English language docs. IR systems need to cater to this multilingual landscape

- **Machine translation**; currently far from perfect, but can enable users to gist subject matter of retrieved vernacular docs

### Semantic Search

**Query-document mismatch** problem; query and relevant documents describe ths _same concept using different words_

- use **semantic analysis** to understand or interpret queries and documents. Understand the contents of the document to help address this problem and improve reliability.

  - Use of **knowledge graphs**; used by Google to create info _cards_ describing entities including ppular peple, places etc
  - Use of **question answering** systems to _interpret the query as a direct question_ and seeks to provide the answer to that question.
  - **Vector representation** of words and concepts; Words represented in a _common vector space_ enabling direct comparison of words and vector summation to represent complex concepts eg "river" and "stream" may be similar. "Dublin" and "river" can be similar to vector for "Liffey".

### Enterprise Search

The practice of identifying and enabling content across an enterprise to be indexed, searched and displayed to **authorized users**.

- need to index data/docs from a variety of sources; file systems, intranets, doc management systems, email and databases - then present an **integrated list** of _ranked potenially relevant items_ from all these sources at once.
- **Access controls are vital** if user access is to be restricted only to data and documents to which they have been granted access to within enterprise.

### Information Omnipresence

Web on mobile means info should be acceptable anywhere, anytime..

Need to take **user context** into account:

- location, time weather, current associates, diary, current activity (driving, walking etc)
- info can be suplied _without an interactive query_ eg while driving, supply traffic congestion info

### Personalization and Context.

Search engines behave the same for all users, but different users have different needs at different times.

- Personalization and exploitation of context offer adaption of IR to deliver right results to different users in different settings

### Lifelogging

**Capture, storage** and **exploitation** of _as many sources of info_ relating to an individual's life experience as possible.

- GPS tracking, phone and computer use, images on Microsoft SenseCam, biometric sensor data (fitbits).
- allows users to search for informtion from their past, reminisce or reflect on a past experience
- Need to link content _and context_ for searching a digital "human memory"

### Components of an IR System

- **Document Collection**
  - gathered from existing document set - business repots, newspaper articles
  - gathered from web documents using a _web spider_, crawler, bot
  -Docs need to be _preprocessed_ to standad format - case conversion, removal of HTML, stemming etc

- **Document Indexing**
  - convert docs into _fast, searchable format_ e.g inverted file

- **Search Request**
  - enter search request expressing _user info need_

- **Document Searching**
  - compute a set of potentially relevant documents and return to user
  - rank with a _matching score_, which can rank based on likelihood of relevance

- **Relevance Feedback**
  - modify the search; expand query using extra search lines based on relevance data, _run the search again_

### Web Search

- Web search engines can pre-compute results for popular queries (maybe daily), then provide these results rather than re-computing the results each time this query is entered.
- Text IR is an important component of Web search. Also can use Web link structure, frequencty with which users click on particular docs or subjective qualiy of each page to refine the search

Final note: Search is so important in tackling **information overload**

