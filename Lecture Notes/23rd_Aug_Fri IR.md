---
tags:
  - IR
  - lecture
---
![[23rd_Aug_Fri IR 2024-08-23.excalidraw]]
# Text Transformation
- Stop Words
- Normalization
- stemming 
- Tokenization

### Lemmatization
Pretty similar to stemming but with small difference  

operation -> oper (stemmed) 
operation -> operate (lemmatization)

## Inverted Index 
- Efficiency Concern

 Query = Tx and Ty 
## SkipGrams 
- Shortcut Pointers 

It's giving us fast way of traversing long posting lists ,

![[7. Attachments/23rd_Aug_Fri IR 2024-08-23.excalidraw.md#^group=e0T6zY6ZqOc0zAlqSxVb2]]

#### Algorithm for skip search 
```
INTERSECT_WITH_SKIPS(p1 , p2)
	RESULTS = []
	WHILE p1 && p2:
		IF DOCID(P1)==DOCID(P2):
			APPEND(RESULT,DOCID(P1))
			P1 = NEXT(P1)
			P2 = NEXT(P2)
		ELSE
			IF DOCID(P1) < DOCID(P2) AND HASSHKIP(P1) = TRUE
				WHILE HASSKIP(P1) AND DOCID(SKIP(P1)) < DOCID(P2):
					P1 = SKIP(P1)
				ENDWHILE
			ELSE IF (DOCID(P2) < DOCID(P2) AND HASSHKIP(P2) = TRUE) 
				WHILE HASSKIP(P2) AND DOCID(SKIP(P2)) < DOCID(P1):
					P2 = SKIP(P2)
				ENDWHILE
				
			ELSE
				P2 = NEXT(P2)
			END IF
		END IF
```

> [!Important] 2 Marks Questions
> 1. A query is disjunction requires skip grams?
> 2. Write algorithm for skip grams
> 3. When should we use skip grams ? 
> 4. How are skip grams made? 


## Phrase Queries 
-> BI word phrases 
	"Olympic Game"

**Challanges**
- many users does not signify in the query that it is phrase query.

Many IR systems tackle the challanges by also adding all the two words pairs in their vocabulary , downsides of this method is that the size of vocabulary rises exponentially , ==this is not a feasible solution , not a practical one== 
- only academic search engine uses them.

A bi-word vocabulary can be used to make 3 word phrase , and any number of them by making them essentially a intersect operation , but there will be false postiive. 

==False postitive a document in returned but doesn't containt the word"==
two words maybe in the same document but not in the same order as that of query.

Many IR researchers have researched and found that many queries are of form : 
$$ Proper\ Noun \ x^* \ Proper Nouns $$

- So what we do if a document contains the pattern , we also include that pattern into the vocabulary. 
> [!note] 
> When we add the pattern we also add individual tokens as well.

### Positional Indexing 
