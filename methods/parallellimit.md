# parallelLimit

**snc.parallelLimit\(number, Array\_functions\(done\), callback\_end\(data\)\)**

Run limit of functions in parallel and then execute "callback\_end". Alternative name : pl

```javascript
snc.pl(2,
  [
  done => {
    setTimeout(() => {
      console.log(`go 1!`)
      done(`a`)
    }, 1000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 2!`)
      done(`b`)
    }, 3000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 3!`)
      done(`c`)
    }, 1000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 4!`)
      done(`a2`)
    }, 3000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 5!`)
      done(`b2`)
    }, 1000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 6!`)
      done(`c2`)
    }, 3000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 7!`)
      done(`a3`)
    }, 1000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 8!`)
      done(`b3`)
    }, 3000)
  },
  done => {
    setTimeout(() => {
      console.log(`go 9!`)
      done(`c3`)
    }, 1000)
  }
],
data => {
  console.log(`we: ${JSON.stringify(data)}`)
})
```

```text
-> go 1!
-> go 3!
-> go 2!
-> go 5!
-> go 4!
-> go 7!
-> go 6!
-> go 9!
-> go 8!
-> we: ["a","b","c","a2","b2","c2","a3","b3","c3"]
```

