#lecture #IR 
Date : 16/08/2024
## Crawling And Freshness 
Crawling : [HEAD]/student/home
Host: www.bitmesra.ac.in
```
Server Response :
DATE : 20-08-1998
SERVER : Apache 3 x UBUNTU 
Last Modified : -7-08-2024
connection : closer 
content-type : ftext/html : encoding = latin 
content-length: 2500
```

1. Freshness  = no of fresh pages / total pages crawled
		Freshness -> 1
		we want freshness to tend towards unity. 
After you have crawled the page  for first time , how do know distance you need to crawl back ? 
> [!example]
> - blog 
> - story repository
> - news 
> which among the first will update more frequently ? 
> How does the crawler know news need to crawl more often ?
> If we define that crawler comes back to the page every 5 seconds will the website allow that ? 
> Either you crawl and decrease your freshness ratio  or you ignore the pages , but then your users will suffer,
>  

>  **When should I recrawl ?** 
>  Instead of the freshness being either 0 or 1 we define `age` of the page and soons as the day passes the day becomes a nascent page, thus the access of page is now not a discrete graph but a increasing floating point number and this makes the calculation more mathematically tactile ,
>  


```
	page change freq = l  (changes per day)
	let l = 1/7 (page updates per week)
	l = 24 ( page update per day)
``` 

```
	Age ( l , t )
	l -> page change rate 
	t -> time 
	assuming the page was evaluated at time = x 
			x < t ;
Age(l,t) -> the expected age of the page at time 't' given it was last crawled at time 't'
```

**Age function need not be linear**
```
	Age(l , t ) = integral ( p(x) (t-x))dx
```

> [!note]
> Reasearchers have tested experminetlay and shown that poisson's distsribuiton is best for modelling the age of the page . 
> Molin's paper 

- [ ] 🔼  Check for lambda = 24 to calculate the age of the page

The  discussion is null and void if we don't know the value of lambda.
## How do we know the value of lambda ? 
**Sitemaps :**
its is special text file , usually written in XML which gives completes navigation hierarchy given by the admin to the search admin .

```xml
<?xml version="1.0" encoding = "latin">
<urlset>
	<url>
	<ioc> /home </ioc>
	<priority> 0.8</priority>
	<change freeq> 0.08</change freq>
	</url>
 <url> 
	 <ioc> /notices</ioc>
	 <priority> 0,75</priority>
	 <change frequency> 0.72</change frequncy>
	 </url>	
 </urlset>
```

## Can a Crawler look at whole internet ? 
- private web site ( dark web )
	url is never made public , and is given to a fixed set of people 
- Forms submissions 
	 For medium and enterpise level crawlers , forms submissions websites remain untouched 
- Dynamic website
	These links cannot be crawled they are  active only for a certain time
	A crawler can look at the sitemap and get past the signup forms.
	So if you not get enterprise level resources you will only get to see 50% of webpages. 