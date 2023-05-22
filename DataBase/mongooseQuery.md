#### mongoose Schema types
    https://mongoosejs.com/docs/schematypes.html

#### mongoose general Queries:
    https://mongoosejs.com/docs/queries.html


#### Aggregate examples:
 ```
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