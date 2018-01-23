### start mongoDB
```
net start mongoDB
```
### to show database

```
show database
```
### create and use database

```
use someName
```

### create user

```
db.createUser(
   {
     user: "shiva",
     pwd: "password",
     roles: [ "readWrite", "dbAdmin" ]
   }
)
```
---
collections are like **tables** in relational database

### creating a collections
```
db.createCollection('tableName');
```

### to show collections

```
show collections
```

### inserting into table(collection)

```
db.customers.insert({name:"...",age:"..."});
```
### to find
```
db.customers.find();
```

### multiple insert

```
db.customers.insert([{...},{...}])
```


### pretty

```
db.customers.find().pretty();
```

### update

```
db.customers.update({before},{after});

```

### update with previous data
```
db.customers.update({before},{$set:{after}})
```

**$set:** retains previous data and adds new data after it

### increment

```
db.customers.update({before},{$inc:{age:5}});
```
this will increment age by 5 and also retains previous data


### remove
```
db.customers.update({before},{$unset:{age:1}});
```

### if collection is not present then to add it to database

```
db.customers.update({before},{after},{upsert:true});
```

### to rename
```
db.customers.update({before},{$rename:{"gender":"value"}});

```

### to remove

```
db.customers.remove({...});
```

### to remove only one

```
db.customers.remove({...},{justOne:true});
```

### or operator
```
db.customers.find($or:[{...},{...}]);
```

### grater than and less than operator
```
db.customers.find(age:{$lt:40});
```
