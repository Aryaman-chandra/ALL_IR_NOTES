---
tags:
  - IR
  - lecture
---

# Crawling
## Distributed Crawling : 
- Multiple Machines 
- Multiple Threads

#### Advantages of Distributed Crawling:
- Distance 
	Google's server crawls entire documents in South East Region from Singapore.
- Reduced Latency
- Memory 
	- Recrawl 
- Improved Computational Load
	If while crawling a thread is blocked on I/O i should immediately run another thread as to reduce idle time.

![[7. Attachments/20th_Aug_Tue IR 2024-08-22_1.excalidraw.md#^frame=gF1juURhFBHX_RCsSzWg8|thread_run]]


## Text Transformation 

![[7. Attachments/20th_Aug_Tue IR 2024-08-22_1.excalidraw.md#^group=5dpZcjPo]]
```
D1 -> The Sun rises in the East 
D2 -> The Sun is Hot
D3 -> The Sauce was very hot
```


==Query== "Orange Sun" 
Now which documents should i fetch for the above query. 

For our purposes does it not make sense to retrieve those documents which has both the terms Orange and Sun 

### Boolean Retrieval 
This is **my understanding** of the **boolean model** based **information retrieval** system that given a set of documents and it's **index terms** and whether or not the index terms are present in the documents , 
The boolean model predicts that each document is either relevant or non-relevant 

## Disadvantages of Boolean Retrieval 
1. The Boolean Retrieval Model is based on binary criterion , whether a document is relevant or note , ==without any notion of grading== does making it more of a ==Data Retrieval Model==
2. While boolean expression have semantics , most query cannot be translated into boolean expression whereas the user queries are generally simple.

> [!example] Example of the boolean retrieval
> [Example of Boolean Retrieval](https://nlp.stanford.edu/IR-book/html/htmledition/an-example-information-retrieval-problem-1.html)



![[7. Attachments/20th_Aug_Tue IR 2024-08-22_1.excalidraw.md#^group=96gRa2ra]]

## Concerns 

Are these words going to be stored in Primary Memory ? 

Is my Primary Memory long enough to account for all the words in a Document ? 

## Primary Data Structure 
The primary Data structure to index the terms is called the **Inverted Index**

#### Inverted Index
In an Inverted Index , we maintain an index of terms and to each term we maintain an corresponding **Posting List**
A Posting List is a list of   reference of documents containing the indexed search term. 

![[7. Attachments/20th_Aug_Tue IR 2024-08-22_1.excalidraw.md#^group=cfAPTOIhwH9LqfgcSMjWI]]


To answer the query which documents contains we need to merge the lists of the given terms , 

We maintain a sorted list of document numbers in order to efficiently merge the lists.

Now we can only merge two lists at a time , so in order to optimize the no of steps of comparison that are required we try to merge by shortest lists first , 

> [!note] It's a probability 
> Going shortest first improves our chances of going much faster as the result containing all the terms will be determined by the length of the shortest list

>[!caution] **Edge Case** 
> If the shortest list has documents indexed far apart we still need to traverse the entire second list 
> ```
> T1 -> 1 , 1500
> T2 -> 1,2,3,5,8,7,23,64,74,.....,1433,1500

