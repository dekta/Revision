#### mongoose Schema types
    https://mongoosejs.com/docs/schematypes.html

#### mongoose general Queries:
    https://mongoosejs.com/docs/queries.html


#### Aggregate examples:
 ```javascript
 Model.
  aggregate([{ $match: { age: { $gte: 21 }}}]).
  unwind('tags').
  exec();
```


#### more Examples of aggregation:
    https://studio3t.com/knowledge-base/articles/mongodb-aggregation-framework/
    https://www.mongodb.com/docs/manual/core/aggregation-pipeline/



#### more information of MongoDB
    https://interviewhandbook.notion.site/NoSQL-282749fd15d540ff8afee0cf1517ee18


## Explain why mongoose does not return a promise but has a .then
- Mongoose is a library for working with MongoDB databases in Node.js. While most database operations in Mongoose are asynchronous, Mongoose does not return Promises by default.
- Instead, Mongoose uses a callback function to handle the results of asynchronous operations. However, Mongoose also provides a .then() method that allows you to chain asynchronous operations together, similar to Promises.
- So while Mongoose does not directly return Promises, it provides a way to work with Promises using the .then() method.



## What are pre and post hooks?
- In Mongoose, pre and post hooks are functions that can be executed before or after certain operations are performed on a Mongoose model or document.
- Pre hooks are functions that are executed before a specified operation is performed on a model or document. These functions are useful for performing additional validation, modifying data, or executing additional logic before an operation is executed. Pre hooks can be registered using the pre() method on a Mongoose schema.
- Post hooks are functions that are executed after a specified operation is performed on a model or document. These functions are useful for logging or auditing data, executing additional logic, or modifying data after an operation is executed. Post hooks can be registered using the post() method on a Mongoose schema.
- example
    ```javascript
     const mongoose = require('mongoose');
    const userSchema = new mongoose.Schema({name: String,email: String,});
    userSchema.pre('save', function (next) {const now = new Date();
                this.updatedAt = now;
                if (!this.createdAt) {
                this.createdAt = now;
                }
                next();
                });
     userSchema.post('save', function (doc, next) {
            console.log(`User ${doc.name} saved`);
            next();
            });
    const User = mongoose.model('User', userSchema);


## What are aggregation pipelines with mongoose?

- Aggregation pipelines in Mongoose are a way to process and transform data from MongoDB collections using a sequence of stages.
- An aggregation pipeline consists of a series of stages that are executed in a specific order to transform the input data. Each stage in the pipeline takes the input documents and performs some operation on them, passing the results to the next stage.
- The stages in an aggregation pipeline can perform a wide range of operations, such as filtering, sorting, grouping, and transforming data. Some examples of pipeline stages include $match, $group, $sort, $project, and $lookup.
- Aggregation pipelines in Mongoose are defined using the aggregate() method, which takes an array of pipeline stages as its argument. Once the pipeline is defined, you can execute it using the exec() method, which returns a Promise that resolves to an array of output documents.
- Aggregation pipelines are a powerful tool for working with data in MongoDB collections, and can be used for a wide range of tasks such as data analysis, reporting, and business intelligence.
    ```javascript
         const Order = mongoose.model('Order', { total: Number});
         Order.aggregate([{ $group: { _id: null, avgTotal: { $avg: "$total" } } }]).exec((err, result) => {
        if (err) {
            console.error(err);
            return;
        }
        console.log(result);
        });


## How do you create indexes with mongoose
- we can create indexes in Mongoose using the Model.ensureIndexes() method.
- The ensureIndexes() method ensures that all defined indexes are created in the background. It takes a callback function that is called once all indexes have been created, or if an error occurs during the index creation process.
- Example =>
    ```javascript
        const mongoose = require('mongoose');
        const userSchema = new mongoose.Schema({name: String,email: String,});
        userSchema.index({ email: 1 }, { unique: true });
        const User = mongoose.model('User', userSchema);
         User.ensureIndexes((err) => {if (err) {console.error(err);} else {console.log('Indexes created successfully'); }});




## Mongoose basic query:
- Mongoose is an Object-Data Modeling (ODM) library for Node.js and MongoDB, which provides a straightforward way to interact with MongoDB databases. It simplifies the process of defining schemas, creating models, and performing database operations.

#### Connecting to MongoDB:
- ```javascript
       const mongoose =  require("mongoose")
        const connect = mongoose.connect("mongodb://127.0.0.1:27017/db")
        module.exports = {connect}

#### Defining a schema:
-   ```javascript
        const mongoose  =  require("mongoose")
        const userSchema =  mongoose.Schema({
            name:"String",
            email:"String",
            password:"String",
        })
        const UserModel = mongoose.model("user",userSchema)
        module.exports = {UserModel}

#### Creating a new document:
-   ```javascript
    const user = new UserModel({ name: 'John Doe', age: 30 });
    user.save()

#### Finding documents:
-  ```javascript
    let user = await UserModel.find()   // Find all documents
    let SpecificUser = await Usermodel.findOne({email}) //Find documents with a specific condition
    let userbyid = await Usermodel.findById(id).exec();  //find document that match the given id

#### Updating documents:
-  ```javascript
    let filter = {key:value} // to find document
    let update = {key:value} // update value
    let user = await UserModel.findOneAndUpdate(filter, update);
    // find by Id and update
    await userModel.findByIdAndUpdate(id, update)


#### delete document:
-  ```javascript
    await UserModel.deleteOne({ email: 'abc@gmail.com' });  //delete one that match the condition
    await UserModel.deleteMany({ name: /Stark/, age: { $gte: 18 } });  //delete many that match the condition
    await UserModel.findByIdAndRemove(id)   //find by Id and remove
    await UserModel.findOneAndDelete(conditions)   // fidn by condition and delete

#### replace value:
-  ```javascript
    const res = await Person.replaceOne({ _id: 24601 }, { name: 'xyz' });



## Aggregation example:
-  ```javascript
   1) Model.aggregate([{ $match: { age: { $gte: 21 }}}]).exec();
   2) aggregate.lookup({ from: 'users', localField: 'userId', foreignField: '_id', as: 'users' });


## populate:

#### defining schema with ref
- ```javascript
        const mongoose = require('mongoose');
        const { Schema } = mongoose;

        const personSchema = Schema({
        _id: Schema.Types.ObjectId,
        name: String,
        age: Number,
        stories: [{ type: Schema.Types.ObjectId, ref: 'Story' }]
        });

        const storySchema = Schema({
        author: { type: Schema.Types.ObjectId, ref: 'Person' },
        title: String,
        fans: [{ type: Schema.Types.ObjectId, ref: 'Person' }]
        });

        const Story = mongoose.model('Story', storySchema);
        const Person = mongoose.model('Person', personSchema);

#### Saving refs
- ```javascript
    const author = new Person({
        _id: new mongoose.Types.ObjectId(),
        name: 'Ian Fleming',
        age: 50
        });

        author.save(function(err) {
        if (err) return handleError(err);

        const story1 = new Story({
            title: 'Casino Royale',
            author: author._id // assign the _id from the person
        });

        story1.save(function(err) {
            if (err) return handleError(err);
        });
    });
    

#### Population
- ```javascript
    const story = await Story.
    findOne({ title: 'Casino Royale' }).
    populate('author').
    exec();
