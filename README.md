# 👨🏼‍⚕️ Predictors of Mental Health Illness


 <img src="https://user-images.githubusercontent.com/101379141/201035143-6f1af4fe-4169-4074-8287-6790d88803db.png" alt="Image" width="350" height="160">  



# :books: Table of Contents <!-- omit in toc -->

- [:briefcase: Case Study and Requirement](#case-study-and-requirement)
- [:bookmark_tabs: Example Datasets](#bookmark_tabsexample-datasets)
- [🔎 Explore data and test model](#explore-data-and-test-model)
- [📃 What can you practice with this case study?](#-what-can-you-practice-with-this-case-study)

---

# Case Study and Requirement

Company A sells fashion. They have stores in each country’s capital: UK (London); FR (Paris); IT (Milan); GER (Berlin). Their customers either buy online or in the store itself. 
At the same time, it maintains a website of individual product pages with write ups and images about the page. In some cases, the page might have gone up after the product was put up for sale. 


### ❓ Question
Management would like you – the data analyst – to use of this data and answer these questions: 
- What is the impact of our website traffic on revenue? 
- Which products get us pageviews and revenue?
- What customer segments are there?

---

# :bookmark_tabs:Example Datasets


**Table** 

<div align="center">

|Source|Description|	Link|	
|:----|:-----|:----|
Customers & Transactions|Customer info and their transactions. These transactions are a mix of in-store and online transactions.|Customers|
Website Traffic|Website traffic data for individual product pages (Duration: Jan to Dec 2020)|Traffic|
</div>
 

<details><summary> 👆🏼 "Customer Info" Dataset of Customers & Transactions Source </summary>

- ID : Customer ID
- FirstName
- LastName
- Country
- DateJoined : The date when customer sign up for account on website.
- Gender 
- Birthday:
- Newsletter : Do customer accept to receive email-newsletter monthly ?

|ID|FirstName|	LastName|	Country|	DateJoined|	Gender|	Birthday|	Newsletter|
|:----|:-----|:----|:----|:-----|:----|:----|:-----|
0|	V0.296680287495188|	L0.104646531512644|	FR - France|	2015-12-18|		|1968-02-03|	N|
1|	D0.793097101838541|	Law0.141693355411763|	GER - Germany|	2015-12-21|	M|	2009-10-06|	Y|
2|	Ker0.141418247925814|	Ng0.753960335680345|	FR - France|	2015-12-22	|F	|1990-08-04	|Y|
3|	Fik0.950054552966336|	F0.590961171612745	|UK - United Kingdom|	2015-12-22|	M	|1974-07-24|	N|
4|	Iona0.294287981536498|	Ison0.826191754811968|	IT - Italy|	2015-12-22	|M	|1981-08-13	|N|
5|	Celin0.498684223052738|	Tio0.597043135639238|	GER - Germany|	2015-12-23|	F	|1979-03-27|Y|
6|	Ad0.410135716954602|	Tan0.662463855720801|	GER - Germany|	2015-12-23	|M	|1984-06-01|N|
7|	Ev0.291189764697797|	Kh0.766529502176661|	GER - Germany|	2015-12-24	|F	|1970-11-12|Y|
8|	S0.892783416837388|	WEN0.271074390106408|	FR - France|	2015-12-28	|M|1991-02-28|Y|
9|	Chok0.637930969851357|	SW0.984189910495377|	FR - France|	2015-04-01|	|	|1984-02-14|Y|

</details>

<details><summary> 👆🏼 "Items" Dataset of Customers & Transactions Source </summary>

- ItemID : Customer ID
- Product: encrypted Product Name
- Brand : encrypted Brand name
- SellPrice 
- CostPrice

|ItemID|Product|Brand|SellPrice|CostPrice|	
|:----|:-----|:----|:----|:-----|
1|	032irview0.686128260621012|	Ki)D3jDmA,RIP68X|	943|	359|
2|	070ttream0.518887735674677|	GO4582ey<S!+k1VE| 717|	207|
3|	070htream0.333307794468401|	G.Kb^jz*soY!(-4Q|	739|	199|
4|	100Grseys0.271522111052549|	Dr|vm[-5p~56Y\mk|	532|	262|
5|	100[nside0.645837365801341|	Dr|vm[-5p~56Y\mk|	593|	392|
6|	101Hition0.428000735843647|	LaX{ty9j_zZdD-\`|	1098|	110|
7|	101Tation0.58144832266657|	Bap5U9):Zyo)!(Y0|	434|	164|
8|	101s-info0.671227295694652|	LN=p+iC[&z'G,t&/|	524|	406|
9|	101clease0.915823550778048|	Ac8IJsKH,4xtY.Tk|	586|	231|
10|	101Dlease0.745305177696334|	SSJ%#@$7LTf<p'Jx|	465|	256|


</details>

<details><summary> 👆🏼 "Customer transactions" Dataset of Customers & Transactions Source </summary>

- OrderID :
- CustomerID: 
- ItemID : 
- TransactionDate : When customer buy products
- Channel : Store or Online

|OrderID|CustomerID|ItemID|TransactionDate|Channel|	
|:----|:-----|:----|:----|:-----|
0|	0|	352|	2020-03-21|	In Store|
0|	0|	3433|	2020-07-14|	In Store|
0|	0|	11162|	2020-08-09|	In Store|
0|	0|	13011|2020-12-07|	In Store|
0|	0|	13885|	2020-11-08|	In Store|
1|	0|	1867|	2020-05-19|	In Store|
1|	0|	16495|	2020-01-24|	In Store|
2|	0|	1653|	2020-09-24|	Online|
2|	0|	2520|	2020-02-06|	Online|
2|	0|	5117|	2020-04-27|	Online|

</details>

<details><summary> 👆🏼 Example of traffic Dataset  </summary>

- Page URL : website's address of products  contains products names vs month & Year of transactions
- users: number of users
- uniquePageviews :  number of unique page views
- pageviews : number of page views
- Brand : encrypted Brand name
- Posted On (DD/MM/YYYY) : Date of Website traffic. 

|Page URL|users|uniquePageviews|pageviews|Brand|Posted On (DD/MM/YYYY)|	
|:----|:-----|:----|:----|:-----|:-----|
/2020/1/032irview0.686128260621012|	5669|	5778|	6286|	Ki)D3jDmA,RIP68X|	1/10/2020|
/2020/1/070ttream0.518887735674677|	360|	370|	403|	GO4582ey<S!+k1VE|	1/10/2020|
/2020/1/070htream0.333307794468401|	588|	614|	658|	G.Kb^jz*soY!(-4Q|	1/16/2020|
/2020/1/100Grseys0.271522111052549|	1284|	1309|	1385|	Dr|vm[-5p~56Y\mk|	1/17/2020|
/2020/1/100[nside0.645837365801341|	1846|	1881|	2025|	Dr|vm[-5p~56Y\mk|	1/23/2020|
/2020/1/101Hition0.428000735843647|	2111|	2134|	2330|	LaX{ty9j_zZdD-\`|	1/30/2020|
/2020/1/101Tation0.58144832266657|	1714|	1740|	1896|	Bap5U9):Zyo)!(Y0|	1/8/2020|
/2020/1/101s-info0.671227295694652|	465|	469|	498|	LN=p+iC[&z'G,t&/|	1/28/2020|
/2020/1/101clease0.915823550778048|	516| 519|	552|	Ac8IJsKH,4xtY.Tk|	1/2/2020|
/2020/1/101Dlease0.745305177696334|	285|	287|	306|	SSJ%#@$7LTf<p'Jx|	1/1/2020|

</details>


---
## 🔎  Explore data and test model

### The Process is following - [Code & Presentation](https://github.com/beto1810/Predictors-of-mental-health-illness/blob/main/Explore%20data%20and%20test%20model.md#1%EF%B8%8F%E2%83%A3-explore-data-analysis) or [Only Code](https://github.com/beto1810/Predictors-of-mental-health-illness/blob/main/File/Final_Mindx_De1%20(2).ipynb)

- Import Library and dataset
- Explore data
- Preprocessing - Encoding
- Relationship Charts
- Scaling & Fitting
- Tuning
- Evaluate Model
- Final Clusters

---

# 🧾 What can you practice with this case study?
- Python
  - pandas, numpy,matplotlib, sklearn.
  - Cleaning, check Null values, transforming, Merging, Groupby. 
  - Running model,Scaling model, Fiting model, Testing model. 
  - Loop function.


