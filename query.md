## Queries

1. db.employees.find({name: 'Babelgum'}, {name: 1, _id: 0})

2. db.employees.find({number_of_employees:{$gt:5000}}).limit(20).sort({number_of_employees:1})

3. db.employees.find({ founded_year: { $gte: 2000, $lte: 2005 } }, { name: 1, founded_year: 1, _id: 0 })

4. db.employees.find({ "ipo.valuation_amount": { $gt: 100000000 }, "ipo.pub_year": { $lt: 2010 } }, { name: 1, ipo: 1, _id: 0 })

5. db.employees.find({number_of_employees:{$lt:1000},founded_year:{$lt:2005},},{name:1,number_of_employees:1,_id:0})

6. db.employees.find( { $or: [{ partners: { $exists: false } }, { partners: { $size: 0 } }] }, { _id: 0, name: 1 } )

7. db.employees.find( { category_code: null }, { _id: 0, name: 1 } )

8. db.employees.find( { number_of_employees: { $gte: 100, $lt: 1000 } }, { _id: 0, name: 1, number_of_employees: 1 } )

9. db.employees.find( { "ipo.valuation_amount": { $exists: true } }, { _id: 0, name: 1, "ipo.valuation_amount": 1 } ).sort({ "ipo.valuation_amount": -1 })

10. db.employees.find({},{_id:0,number_of_employees:1}).sort({number_of_employees:-1}).limit(10)

11.  db.employees.find( { $expr: { $and: [ { $gte: ["$founded_month, 7] }, { $lte: ["$founded_month", 12] }] } }, { _id: 0, name: 1, founded_year: 1, founded_month: 1, founded_day: 1 } ).limit(1000)

12. db.employees.find( { $and: [ { founded_year: { $lt: 2000 } }, { "acquisition.price_amount": { $gt: 10000000 } }] }, { _id: 0, name: 1, founded_year: 1, "acquisition.price_amount": 1 } )

13. db.employees.find( { "acquisition.acquired_year": { $gt: 2010 } }, { _id: 0, name: 1, acquisition: 1 } ).sort({ "acquisition.price_amount": 1 })

14. db.employees.find( {}, { _id: 0, name: 1, founded_year: 1 } ).sort({ founded_year: 1 })

15.  db.employees.find( { "founded_day": { $gte: 1, $lte: 7 } }, { _id: 0, name: 1, founded_day: 1, "acquisition.price_amount": 1 } ).sort({ "acquisition.price_amount": -1 }).limit(10)

16. db.employees.find( { "category_code": "web", "number_of_employees": { $gt: 4000 } }, { _id: 0, name: 1, category_code: 1, number_of_employees: 1 } ).sort({ number_of_employees: 1 })

17. db.employees.find( { "acquisition.price_amount": { $gt: 10000000 }, "acquisition.price_currency_code": "EUR" }, { _id: 0, name: 1, acquisition: 1 } )

18. db.employees.find( { "acquisition.acquired_month": { $gte: 1, $lte: 3 } }, { _id: 0, name: 1, acquisition: 1 } ).limit(10)

19. db.employees.find( { $and: [ { "founded_year": { $gte: 2000, $lte: 2010 } }, { "acquisition.acquired_year": { $not: { $lt: 2011 } } }] }, { _id: 0, name: 1, founded_year: 1, acquisition: 1 } )