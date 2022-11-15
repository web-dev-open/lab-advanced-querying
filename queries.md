![Root logo](https://imgur.com/Hq8xgzy.png)

# Answers

Filter:
Project:
Sort:
Collation:
Skip:
Limit:

### DONE1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

filter:{name:"Babelgum"} Project:{name: 1, \_id:0}

<!-- Your Code Goes Here -->

### DONE2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

Filter: {number_of_employees: {$gt:5000}}
Project:
Sort: {number_of_employees: -1}
Collation:
Skip:
Limit: 20

<!-- Your Code Goes Here -->

### DONE3. All the companies founded between 2000 and 2005, both years included. Retrieve only thex `name` and `founded_year` fields.

Filter: {founded_year: {$in: [2000,2001,2002,2003,2004,2005]}}
Project: {name: 1, founded_year:1}
Sort:
Collation:
Skip:
Limit:

### Done 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

Filter: {$and: [{ "ipo.valuation_amount": { $gt:100000000 }},{ founded_year: { $lt: 2010 }}]}
Project:{name: 1, ipo:1}
Sort:
Collation:
Skip:
Limit:

### DONE5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

Filter:{$and: [{ number_of_employees: { $lt: 1000 }},{ founded_year: { $lt: 2005 }}]}
Project:
Sort:{number_of_employees: -1}
Collation:
Skip:
Limit: 10

### 6. All the companies that don't include the `partners` field.

Filter: { partners : { $exists: false } }
Project:
Sort:
Collation:
Skip:
Limit:

### DONE 7. All the companies that have a null type of value on the `category_code` field.

Filter: {category_code:{$in:[null]}}
Project:
Sort:
Collation:
Skip:
Limit:

<!-- Your Code Goes Here -->

### 8. Done All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

Filter: { number_of_employees: { $lt: 1000,$gte:100 }}
Project: {name:1,number_of_employees:1, \_id:0}
Sort:
Collation:
Skip:
Limit:

### 9. DONE Order all the companies by their IPO price in a descending order.

Sort:{"ipo.valuation_amount":-1}

<!-- Your Code Goes Here -->

### 10. DONERetrieve the 10 companies with most employees, order by the `number of employees`

sort : {number_of_employees:-1}
limit: 10

<!-- Your Code Goes Here -->

### 11.DONE All the companies founded on the second semester of the year. Limit your search to 1000 companies.

Filter: {founded_month: {$lte:12, $gte:6}}

Limit: 1000

<!-- Your Code Goes Here -->

### 12.DONE All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

filter: {$and: [{ founded_year: { $lt: 2000 }},{ "acquisition.price_amount": { $gt: 10000000 }}]}

### 13.DONE All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.

Filter: {$and: [{ "acquisition.acquired_year": { $gt: 2010 }},{ "acquisition.price_amount": { $exists: true }}]}
Project: {name:1,acquisition:1}
Sort: {"acquisition.price_amount":-1}
Collation:
Skip:
Limit:

### 14.DONE Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

Filter: {"acquisition.acquired_year": { $type : 16 }}
Project: {name:1,"acquisition.acquired_year":1,\_id:0}
Sort: {"acquisition.acquired_year":1}
Collation:
Skip:
Limit:

### 15. DONE All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

Filter: {founded_day: {$lte:7, $gte:1}}
Project:
Sort: {"acquisition.price_amount":-1}
Collation:
Skip:
Limit: 10

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

Filter: {$and: [{ category_code: "web"},{ number_of_employees:{$gt:4000}}]}
Project:
Sort: {number_of_employees: 1}
Collation:
Skip:
Limit:

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

Filter: {$and: [{ "acquisition.price_amount": { $gt: 10000000 }},{ "acquisition.price_currency_code":"EUR"}]}
Project:
Sort:
Collation:
Skip:
Limit:

### 18. DONEAll the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

Filter: {$and: [{ "acquisition": { $ne: null }},{ "acquisition.acquired_month": {$lte:3, $gte:1}}]}
Project:{name:1, acquisition:1, \_id:0}
Sort:
Collation:
Skip:
Limit: 10

### 19.DONE All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

Filter: {$and: [{ "acquisition.acquired_year": { $gte: 2011 }},{ founded_year: {$lte:2010, $gte:2000}}]}
Project:
Sort:
Collation:
Skip:
Limit:

not null;{founded_day: {$ne: null}}
