# foreverParallel

**snc.foreverParallel\(limit, callback\(counter, done\), callback\_end\(data\)\)**

Forever loop with parallel limit. Alternative name: fp.

```javascript
snc.fp(2, (counter, done, end) => {
  console.log(counter)
  if (counter < 6 ) {
    setTimeout(() => {
      done()
    }, 3000)
  } else end('bye!')
},
res => {
  console.log(`END: ${res}`)
})
```

```text
-> 1
-> 2
-> 3 // Wait 3 seconds
-> 4 // Wait 3 seconds
-> 5 // Wait 6 seconds
-> 6 // Wait 6 seconds
-> 7 // Wait 9 seconds
-> END: bye bye! // Wait 9 seconds
```

