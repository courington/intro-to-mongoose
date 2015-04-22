##### intro to mongoose for node.js
pluralsight course


#### Schema and Models

##### example usage
```
var personSchema = new Schema({
    firstName: String,
    lastName: String
});

var Person = mongoose.model('Person', personSchema);

var bob = new Person({
    firstName: 'Bob',
    lastName: 'Oblaw'
});

bob.save(callback);
```

##### disabled _id
```
var noIdSchema = new Schema({name: String}, {_id: false});
```


##### example of using Schema.add
```
var exampleSchema = new Schema;

var includeMiddleName = true;

if(includeMiddleName) {
    exampleSchema.add({
        memberName: {
            first: String,
            middle: String,
            last: String
        }
    });    
}
else {
    exampleSchema.add({
        memberName: {
            first: String,
            last: String
        }
    });
}

exampleSchema.add({
    project: String,
    createdOn: {type: Date, default: Date.now}
});
```