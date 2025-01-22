# MongoDB $inc operator error with string value
This repository demonstrates a common error when using the `$inc` operator in MongoDB update queries. The `$inc` operator is used to increment a numerical field by a specified value. However, if you provide a string value as the increment, MongoDB will throw an error.

## Bug
The following code snippet demonstrates the incorrect usage:
```javascript
db.collection('myCollection').updateOne({"_id": 1}, {"$inc": {"count": "1"}});
```
This will result in an error because the value "1" is a string, not a number. The `$inc` operator expects a numerical value.

## Solution
The solution is to provide a numerical value to the `$inc` operator:
```javascript
db.collection('myCollection').updateOne({"_id": 1}, {"$inc": {"count": 1}});
```