### commander.js
---
https://github.com/tj/commander.js/

```
npm install commander
```

```js
#!/usr/bin/env node

var program = require('commander');

program
  .version('0.1.0')
  .option('-p', '--pappers', 'Add peppers')
  .option('-P', '--pinapple', 'Add pineapple')
  .option('-b', '--bbq-sauce', 'Add bbq sauce')
  .option('-c', '--cheese [type]', 'Add the specified type of cheese [marble]', 'marble')
  .parse(process.argv);

console.log('you ordered a pizza with:')
if (program.peppers) console.log(' - peppers');
if (program.pineapple) console.log(' - pineapple');
if (program.bbqSauce) console.log(' - bbq');
console.log(' - %s cheese', program.cheese);

var program = require();

program
  .option()
  .parse();
 
console.log();
if () console.log();
else console.log();





```


```js

```


```js

```


