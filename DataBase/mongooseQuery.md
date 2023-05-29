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
