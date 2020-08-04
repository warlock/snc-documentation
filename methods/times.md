# times

**snc.times\(number\_times, callback\_loop\(index, next, end\), callback\_end\(data\)\)**

Iterates function "number" times.

```javascript
snc.times(5, (index, next, end) => {
  console.log(`iterator: ${index}`)
  setTimeout(() => {
    if (index === 3) end()
    else next()
  }, index*1000);
},
() => {
  console.log(`End!`)
})
```

```text
-> Iterator 0
-> Iterator 1
-> Iterator 2
-> Iterator 3
-> End!
```

```javascript
snc.times(5, (index, next, end) => {
  console.log(`iterator: ${index}`)
  setTimeout(() => {
    next()
  }, 1000);
},
() => {
  console.log(`End!`)
})
```

```text
-> Iterator 0
-> Iterator 1
-> Iterator 2
-> Iterator 3
-> Iterator 4
-> End!
```

