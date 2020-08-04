# each

**snc.each\(iterable\_array, callback\_loop\(item, index, next\_method, end\_method\), callback\_end\(data\)\)**

Runs next function when "next" method is executed.

```javascript
const list = ['a', 'b', 'c']
snc.each(list, (item, index, next, end) => {
  console.log(`item: ${item}`)
  setTimeout(next, 3000)
},
() => {
  console.log(`End`)
})
```

```text
-> item: a // Wait 3 seconds
-> item: b // Wait 3 seconds
-> item: c // Wait 3 seconds
-> End
```

Call "end" method for break the loop.

```javascript
const list = ['a', 'b', 'c'];
snc.each(list, (item, index, next, end) => {
  console.log(`item: ${item}`)
  setTimeout(() => {
    if (index === 1) end(`Bye!`)
    else next()
  }, 3000)
}, data => {
  if (data) console.log(`End: ${JSON.stringify(data)}`)
  else console.log(`End`)
});
```

```text
-> item: a // Wait 3 seconds;
-> item: b // Wait 3 seconds;
-> End: Bye!
```

