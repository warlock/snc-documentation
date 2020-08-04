# interval

**snc.interval\(function, end\(data\)\)**

Execute in time intervals and break with end function.

```javascript
var i = 0
snc.interval(2000, end => {
  console.log(`Executed: ${new Date()}`)
  i++
  if (i === 3) end('Bye bye')
},
res => {
  console.log(`End: ${res}`)
})
```

```text
-> Executed: Thu Feb 01 2018 13:54:27 GMT+0100 (CET)
-> Executed: Thu Feb 01 2018 13:54:29 GMT+0100 (CET)
-> Executed: Thu Feb 01 2018 13:54:31 GMT+0100 (CET)
-> Response: "End..."
```

