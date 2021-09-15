# DAT250-expass-3

_DAT250: Software Technology Experiment Assignment 3_

### Technical problems that you encountered during installation and use of MongoDB and how you resolved

No issues were encountered.

### Screenshots for:

#### - The correct validation of the installation package (docs.mongodb.com/manual/tutorial/verify-mongodb-packages)
![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_install.png)
![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_startup.png)

#### - Relevant results obtained during Experiment 1 (it is not necessary to put a single screenshot on each substep, but at least one significant from each CRUD operation).

Insert One

![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_crud_insert.png)

Query

![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_crud_query.png)

Update

![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_crud_update.png)

Remove

![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_crud_delete.png)

Bulk Write

![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_crud_bulkwrite.png)

#### - Experiment 2 example working and the additional Map-reduce operation (and its result) developed by each of you.

```
var mapFunction2 = function() {
   emit(this.cust_id, this.items);
};
```

```
var reduceFunction2 = function(keyCustId, items) {
   var flatItems = [];
   items.forEach(itm => flatItems = [...flatItems, ...itm]);
   var count = {};
   flatItems.forEach(itm => {
      if(count[itm.sku] === undefined) {
         count[itm.sku] = itm.qty;
      } else {
         count[itm.sku] = count[itm.sku] + itm.qty;
      }
   });
   var favourite = '';
   var favouriteQty = 0;
   Object.entries(count).forEach(itm => {
       if(itm[1] > favouriteQty){
           favourite = itm[0];
       }
   });
   return favourite;
};
```

```
db.orders.mapReduce(
   mapFunction2,
   reduceFunction2,
   { out: "favourite_items" }
)
```

Result:

```
test> db.favourite_items.find().sort( { _id: 1 } )
[
  { _id: 'Ant O. Knee', value: 'apples' },
  { _id: 'Busby Bee', value: 'pears' },
  { _id: 'Cam Elot', value: 'apples' },
  { _id: 'Don Quis', value: 'chocolates' }
]
```

![](https://raw.githubusercontent.com/palexcast/DAT250-expass-3/main/screenshot_experiment_2.png)

### Reason about why your implemented Map-reduce operation in Experiment 2 is useful and interpret the collection obtained.

It prints out the most bought item for a user. 
There is a bug ("feature") in the code where, if two items have the same quantity, it will print the first of the 2 that it counted.

### Any pending issues with this assignment which you did not manage to solve

No issues came up, but realized quickly that modern JS was not supported in `mongosh`, so I had to avoid using `.flat` and array/object destructuring.