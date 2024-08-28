#IR #LectureNotes 
Date : Wednesday , 21st Aug 2024 

## Text Transformation 

- Go to data structure -> inverted index 

**Posting List :** 
List of documents containing the words. 

WE are mostly interested in vocabulary , document. 

### Document : 
IR needs to address these challanages 
- Language 
	IR should be able to read and comprehend the languages of document , 
	primary ML is used
> [!example]
> English is read from left to right 
> while hebrew and arabic is read from right to left 
- Encoding
	IR needs to be able to understand the encoding of the document ,
	For example  : 
	ASCII needs 8 bits , meanwhile UTF or unicode is dual layer encoding ,
	A large number of documents written not in english which ascii cannot provide  unicode which , you cannot just read bits , 
- Attributes
	if the documents  need to unzip  for compressed files 
### Document Granularity
![Document Granularity]()

> [!example] Documents has paragraphs
> 	query = "vanilla cake"

if the document contains the word `vanilla ` and also `cake` how would IR system know whether the query match the paragraph 
that is should i treat paragraph as a Document or sentence as paragraph , 

Question IR asks ? 
1. Can you read the document ?
2. Do you know what is a document ?


Do you know the format of the document ? 

## Vocabulary
Our first goal should be to **Reduce Vocabulary** 
- Tokenization : 
	- "I will go there today!"
	What token needs to added to the vocabulary , how do you decide to break the token 
	- "I am sure it is Ravi's Car" 
		Is `'` an apostrophe ? if it is do i want to keep `s` it as token.
	- This is a "viva-do-joie"
		Should i keep viva as one token or entire word as token.

#### What is token? 
Is an individual smallest unit , individual output of tokenization is called a token.
#### What is a type ?
-> Group of token having same character sequence.
#### What is a term ?
Terms are those token that make it into the vocabulary , 

#### Jargon 
A word that recently has been made into the language.
For example : 
- U.S.A should be a token .
- A friend type setup , probably reffering to the show.
Primary goal is to reduce vocabulary , 

### Stop Words : 
Given the query the document needs to answer that query  , 

Many words are there for  grammatic understanding they don't add meaning to the words .

- "There is a lot of rain"
- "To be or not to be"
#### Normalization or Canonical Forms:
```yaml
USA : 
	USA
	U.S.A
	United States of America
```

That is forming a group of tokens that convey same meaning , 

Case folding is also normaillization : 
The world 
the world 

What are the tokens that needs to be bunched together ? 

### Stemming 
Operation , operational , operatives , rn running runs ,ran all these words are different character sequences , they convey same meaning , 

Fiven any term reduce it to inflection form or root word , 
for example wherever the word realted to operation repalce it to ==oper==,

Porter's Stemmer 

If a person is running , runs or ran then replace it to run the root word or ==inflection form== , which ultimately conveys same meaning. 