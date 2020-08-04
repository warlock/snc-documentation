# waterfall

**snc.waterfall\(array\_functions\(done, data\), callback\_end\(data\)\)**

Runs next function when "done" method is executed. Alternative name: wf.

```javascript
snc.waterfall([
  done => {
    console.log(`fire`)
    done(5)
  },
  (done, data) => {
    console.log(`ice: ${data}`)
    done("win")
  }
],
data => {
  console.log(`End: ${data}`)
})
```

```text
-> fire
-> ice: 5
-> End: win
```

Break the waterfall with "true".

```javascript
snc.wf([
  done => {
    console.log(`fire`)
    done(true, 5)
  },
  (done, data) => {
    console.log(`ice: ${data}`)
    done(`win`)
  }
], data => {
  console.log(`End: ${data}`)
});
```

```text
-> fire
-> End: 5
```

