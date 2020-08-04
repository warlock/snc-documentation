# forever

**snc.forever\(callback\(repeat, end\), callback\_end\(data\)\)**

Loops syncronous forever.

Alternative name: fe.

```javascript
snc.forever((repeat, end) => {
  console.log(`Hi!`)
  setTimeout(repeat, 3000)
});
```

```text
-> Hi! // Wait 3 seconds;
-> Hi! // Wait 3 seconds;
-> ...
```

Breaking forever loop.

```javascript
var i = 0;
snc.fe((repeat, end) => {
  console.log(`loop: ${i}`)
  if (i>=3) end(`Now Break!!`)
  else {
    i++;
    setTimeout(repeat, 3000)
  }
}, data => {
  console.log(`Response: ${data}`)
});
```

```text
-> loop: 0 // Wait 3 seconds;
-> loop: 1 // Wait 3 seconds;
-> loop: 2 // Wait 3 seconds;
-> loop: 3 // Wait 3 seconds;
-> Response: Now Break!!
```

