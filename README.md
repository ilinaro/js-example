# js-example


```js
var arr = [{id: 1}, {id: 2}, {id: 2}, {id: 1}, {id: 1}, {id: 1}];
var counter = arr.reduce(function (o, i) {
  if (!o.hasOwnProperty(i.id)) {
    o[i.id] = 0;
  }
  o[i.id]++;
  return o;
}, {});
var result = Object.keys(counter).map(function (id) {
  return {id: id, sum: counter[id]};
});
```
