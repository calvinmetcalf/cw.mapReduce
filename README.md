cw.mapReduce
============
map reduce in your browser

```javascript
var worker = cw.mapReduce(4);
//pass it the number of map workers
worker.data([1,2,3]);
//pass it data
worker.map(function(x){
	return x*x;
});
//function do be done once on each datum
worker.reduce(function(a,b){
	return a+b;
});
//reduce function
worker.data([4,5,6]);
worker.fetch().then(function(a){
	console.log(a);
});
//prints 91
worker.data([6,7,8]).fetch().then(function(a){
	console.log(a;)
});
//prints 240
//fetch takes an argument "now", if it's undefined then waitins until it's done
worker.data([6,7,8]).fetch(true).then(function(a){
	console.log(a);
});
//also prints 240
worker.close().then(function(a){
	console.log(a);
});
//prints 389
```