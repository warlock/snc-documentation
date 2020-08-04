# all

**snc.all\(array, callback\_in\_parallel\(element, done\), callback\_end\(data\)\)**

Execute all elements in array in parallel. And get all responses in order.

Alternative name: map.

```javascript
snc.all([3,2,1], (element, index, done) => {
  setTimeout(() => {
    console.log(element)
    done(element)
  }, element * 1000)
},
res => {
  console.log(`Reponse: ${JSON.stringify(res)}`)
})
```

```text
-> 1
-> 2
-> 3
-> [3,2,1]
```

