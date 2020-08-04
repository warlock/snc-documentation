# now

**snc.now\(function, callback\(data\)\)**

Execute now and then execute callback.

```javascript
snc.now(then => {
  console.log('Now')

  setTimeout(() => {
    then('End...')
  }, 3000)
},
res => {
  console.log(`Reponse: ${JSON.stringify(res)}`)
})
```

```text
-> Now
-> Response: "End..."
```

