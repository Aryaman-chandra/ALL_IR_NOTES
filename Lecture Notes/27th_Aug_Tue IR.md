#IR #lecture 
- Positional Index
- Biphrase queries
## Positional Indexes
Vocabulary -> Posting List , 
$$ to= \{ 9000 , \{ 17 \{  6 , 24 , 180\}\}, \{21 , \{7 , 19 ,21, 40 ,64\}\}\}$$
With this positional indexes you should be able to answer phrase queries or proximity queries.

```
	Q: metal /3 disk 
	the words metal and disk are 3 words apart 
	Q : metal /1 disk 
	a bi phrase word
```

**Algorithm**
```
P1 : METAL 
P2 : DISK 
K : 3 
METAL AND DISK WHERE THEY ARE 3 INDEXES APART 
POSITIONAL INTERSECT(P1 , P2 , K): 
	ANSWER = [] 
	WHILE P1 != NULLL && P2!= NULL
		IF DOCID(P1) == DOCID(P2):
			MATCH = [] 
			PP1 = POS(P1)
			PP2 = POS(P2)
			WHILE PP1 
				WHILE PP2 
					IF |POS(PP1) - POS(PP2)| <= k 
						APPEND( MATCHES , POS(PP2))
					ELSE IF POST(PP2) - POS(PP1) > K :  //there is a match but the threshold has been reached 
						BREAK;
					PP2 = NEXT( PP2 )
			END WHILE 
		FOR M IN MATCH 
			APPEND(ANSWER , < DOCID(P1 , POS(PP1) , M>))
```

- [ ] ZIP'S LAW

> [!NOTE]
> 

## Last lookup Aggregation
Same as LRU caching , 
If there's a search term 
recent queries 
recent search terms. 
// To be written again 
## Dictionary & Fault tolerant querying 

what data structures to store the tokens or vocabulary // Maybe Tries
how to search on those ds ? // Suffix Search 
Are there an errors ? // Edit distance ? 


