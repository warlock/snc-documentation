# eachParallelLimit

**snc.eachParallelLimit\(iterable\_array, number\_limit, callback\_loop\(item, index, next\_method\), callback\_end\(data\)\)**

Runs in parallel limit and next loop when "next" method is executed. Alternative names: eachpl, epl.

```javascript
const list = ['a', 'b', 'c', 'd']
snc.epl(list, 2, (item, index, next) => {
  console.log(`item: ${item}`)
  setTimeout(next, 2000)
},
() => {
  console.log(`End`)
})
```

```text
-> item: a
-> item: b
-> item: c // Next to start when next method executed;
-> item: d // Next to start when next method executed;
-> End
```

