### One line iterate
```js
results = results.map(row => (row.package = JSON.parse(row.package), row));
```