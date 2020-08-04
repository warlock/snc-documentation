# forSync

**snc.forSync\(initial, final, increment, callback\_loop\(index, next, end\), callback\_end\(data\)\)**

Syncronous "for" iterator.  
Alternative name: for.

```javascript
snc.for(0, 10, 1, (index, next, end) => {
  console.log(index)
  setTimeout(() => {
    next(5)
  }, 1000)
}, data => {
  console.log(`LENGTH: ${data.length} -> ${JSON.stringify(data)}`)
})
```

```text
-> 0
-> 1
-> 2
-> 3
-> 4
-> 5
-> 6
-> 7
-> 8
-> 9
-> LENGTH: 10 -> [5,5,5,5,5,5,5,5,5,5]
```

```javascript
snc.for(1, 10, 2, (index, next, end) => {
  console.log(index)
  setTimeout(() => {
    next(index)
  }, 1000)
}, data => {
  console.log(data)
})
```

```text
-> 1
-> 3
-> 5
-> 7
-> 9
-> [ 1, 3, 5, 7, 9 ]
```

