# js-example

### Подсчет дублируемых элеметов в каждом обьекте по 1 признаку

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


### Подсчет дублируемых элеметов в каждом обьекте по 2м признакам
```js
const names = [{cat: 1, sub: 1}, {cat: 1, sub: 2}, {cat: 2, sub: 1}, {cat: 1, sub: 1}];

const result = [...names.reduce( (mp, o) => {
    const key = JSON.stringify([o.cat, o.sub]);
    if (!mp.has(key)) mp.set(key, { ...o, count: 0 });
    mp.get(key).count++;
    return mp;
}, new Map).values()];

console.log(result);
```
