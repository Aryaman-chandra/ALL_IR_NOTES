# Fault Tolerant Querying 
- Permuterms 
- k-terms indexes

```mermaid
flowchart

```

```
	$METRIC$ 
	GIVE ME ALL SUBSET OF WORD ETR
	$ -> OUT OF VOCABULARY ELEMENT 

QUERY : RET*
REPHRASED QUERY $RE AND RET
$RE DOES NOT MATCH WITH RETRIEVAL SUCH THAT $RE ONLY MATCHES RET 
THUSE $RETRIEVAL$ ARE NOT  MATCH WITH $RET* 
```

## Why K-term algorithm ? 
- K-term end up making smaller index size.
- full rotations are broken into smaller words 

```mermaid 
flowchart TB 
a[('$ro')]--> b[("rotate")];
a-> c("rotation")]
```
### K-terms 
if a rotation doesn't exist we add it to the index , other wise we remove it ,
[K-gram index for wildcard Queries](https://nlp.stanford.edu/IR-book/html/htmledition/k-gram-indexes-for-wildcard-queries-1.html)


 >[!important] Maybe asked in Midsem
 >What is the size of k-term index in the voabulary
 
- [ ] 🔽 ➕ 2024-08-30 🔁 every week Find the counter cases where k-term doesn't help you out 

> [!example] Counter case for K-term algorithm
> ```
> 	k = 3 , for the word retrieval 
> 	$re
> 	ret
> 	eti 
> 	tir 
> 	ire 
> 	red 
> 	points to retrieval 
> 	Query : red*
> 	matches $re and red and retrieval 


## Spelling Correction 
- First check if the words was a mistake 

> "When do you bring in spell correction ?"


```
Query : Form 
```


### Proximity Measure 
The number of insert , del , replace operations performed on a word `q` to change it to `p` 

The distance between two words. 
Unit distance 

- Hamming Distance 
- Edit distance 
- Levenhstein distance 
$$q=^P (q)$$

==Q: grnt==
### Identification 
1. How does IR know if a mistake has been made ? 
2. If the word is in the dictionary is it a mistake ? 
3. How do you decide what is a spelling mistake ? ~~no definite answer~~
	We usually put a threshold 
	- Content Density 
		>Less than T% of document contains the search term then we say it's a spelling mistake this is called **Content Density**
		
	- Query Density
### Correction 
We have decided that it is a spelling mistake ? 
```
	-> grnt 
		grant 
		grunt
	Offer as substtutute the term with higher content density 
```

### INCONTEXT or spell reference spell correction
```
Query : grnt //spelling mistake in the words itself (isolation)
Query : Who flew form IGI today ? 
	IN context wrong i.e grammatical error
```


### How do you calculate the Proximity Distance ? 
- Levenshtein's Algo 

## Simple DP table for edit Distance 

==DP table is not completed , left it as an exercise for the reader==

| 0/0 | F 1 | A 2 | S 3 | T 4                       |
| --- | --- | --- | --- | ------------------------- |
| C 1 | 1   | 2   |     |                           |
| A 2 |     |     |     |                           |
| S 3 |     |     |     |                           |
| T 4 |     |     |     | Target Proximity Distance |


![Edit Distance Diagram](https://nlp.stanford.edu/IR-book/html/htmledition/img159.png)