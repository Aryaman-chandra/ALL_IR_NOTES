#lecture #IR  
## **What is Information Retrieval ?**
An Information Retrieval System is devoted to finding ***relevant***
documents to the user query , not just finding simple patterns.

**Definition :**
Information Retrieval deals with representation , fetching , storage , organization and access of the information items.

> [!quote] Information is too abstract. 

[[What is Information?|Information]]  Retrieval system the goal is to satisfy the information need
of the user about an subject rather than the matching the data that satisfies a query pattern.

[[Data Retrieval vs Information Retrieval]] 
### **Different Aspects of Information Retrieval**
Different Aspects of Information Retrieval System related to information 
1. Organization.
2. Analysis
3. Storage
4. Access
5. Retrieval 

---
> [!example] Library as an Information Retrieval System
> Some of the tasks you perform at the library 
>  - Information Need 
>  - Query 
>  - Index 
>  - Fetch --> Relevance
>  You are in search of some information , you go to through the index of the library and look at Racks , Section and shelves where you might find the data relevant to subject matter you require , 
>  If the book doesn't contain relevant information we fetch again , otherwise we stop. 


## **Computer as Search Engine** 
Nowadays to satisfy our needs of information we can let a system of computer do the manual task of organization , query , storage Retrieval of information we require 

`Computers as Search Engine`

#### Types of Search Engines 
- Web Search 
- Vertical Search Engine 
- Enterprise Search Engine
- Desktop Search Engine 


## Challenges of IR Systems 
- Vocabulary Mismatch : 
	Since we as human often like to interface in natural language it is tough for an IR system to understand what exactly is user asking about. 
> [!example] 
> IR should probably mention these results for the query
>  1. What is the fastest Car ? 
>  2. Which is the fastest Automobile ? 
>  3. Which is the fastest four wheeler ? 
> All of the above the queries equivalently describes a car , so the IR should mention the results of these queries as well 
> 1. What is the GDP of USA ? 
> 2. What is the GDP of United States of America ? 
- Topic vs User Relevance : 
	What  is the Weather Today ? (User is in Kolkata)
	so answer should be sunny , but it is raining in Ranchi 
	so should IR mention that result ? 
	No , Because it is not relevant to User. 
- Ranking 
	An IR system should be able to rank results based on relevance 
	**For Example:**
	Google lists the Hyperlinks based on the relevance to user query.

### Judgement of Search Engine 
**Parameters a Search Engine** is judged on :

- Effectiveness 
	Given a set of queries what is the fraction of Relevant documents returned 
- Efficiency 
	IR has to be both Effective and Efficient 