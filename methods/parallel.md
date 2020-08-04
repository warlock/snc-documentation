# parallel

**snc.parallel\(array\_functions\(done\), callback\_end\(data\)\)**

Run functions in parallel and then execute "callback\_end". Alternative name: p.

```javascript
snc.parallel(
  [
  done => {
    setTimeout(() => {
      console.log(`hi 3!`)
      done(`a`)
    }, 3000)
  },
  done => {
    setTimeout(() => {
      console.log(`hi 2!`)
      done(`b`)
    }, 2000)
  },
  done => {
    setTimeout(() => {
      console.log(`hi 1!`)
      done(`c`)
    }, 1000)
  }
],
data => {
  console.log(`End: ${JSON.stringify(data)}`)
})
```

```text
//Wait 1 second
-> hi 1! //Wait 1 second
-> hi 2! //Wait 1 second
-> hi 3!
-> End: ["a","b","c"]
```

