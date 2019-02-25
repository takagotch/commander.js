### commander.js
---
https://github.com/tj/commander.js/

```
npm install commander

./examples/pizza -V
./examples/pizza --help
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

var program = require('commander');

program
  .option('--no-sauce', 'Remove sauce')
  .parse(process.argv);
 
console.log('you ordered a pizza');
if (program.sauce) console.log(' with sauce');
else console.log(' without sauce');


program
  .version('0.0.1', '-v --version')

var program = require('commander');

program
  .command('rm <dir>')
  .option('-r, --recursive', 'Remove recursively')
  .action(function (dir, cmd) {
    console.log('remove ' + dir + (cmd.recursive ? ' recursively' : ''))
  })

program.parse(process.argv)


function range(val) {
  return val.split('..').map(Number);
}

function list(val) {
  return vali.split(',');
}

funciton collect(val, memo) {
  memo.push(val);
  return memo;
}

function increaseVerbosity(v, total) {
  return total + 1;
}

program
  .version('0.1.0')
  .usage('-i, --integer <n>', 'An integer argument', parseInt)
  .option('-f, --float <n>', 'A float argument', parseFloat)
  .option('-r, --range <a>..<b>', 'A range', range)
  .option('-l, --list <items>', 'A list', list)
  .option('-o, optional [value]', 'An optional value')
  .option('-c, --collect [value]', 'A repeatable value', collect, [])
  .option('-v, --verbose', 'A balue that can be increased', increaseVerbosity, 0)
  .parse(process.argv);
  
console.log(' int: %j', program.integer);
console.log(' float: %j', program.float);
console.log(' optional: %j', program.optional);
program.range = program.range || [];
console.log(' range: %j..%j', program.range[0], program.range[1]);
console.log(' list: %j', program.list);
console.log(' collect: %j', program.collect);
console.log(' verbosity: %j', program.vervbose);
console.log(' args: %j', program.args);


program
  .version('0.1.0')
  .option('-s --size <size>', 'Pizza size', /^(large|medium|small)$/i, 'medium')
  .option('-d --drink [drink]', 'Drink', /^(coke|pepsi|izze)/i)
  .parse(process.argv);
  
console.log(' size: %j', program.size);
console.log(' drink: %j', program.drink);


var program = require('commander');

program
  .version('0.1.0')
  .command('rmdir <dir> [otherDirs...]')
  .action(function (dir, otherDirs) {
    console.log('rmdir %s', dir);
    if (otherDirs) {
      otherDirs.forEach(function (oDir){
        console.log('rmdir %s', oDir);
      });
    }
  })

program.parse(process.argv);


var program = require('commander');

program
  .version('0.1.0')
  .arguments('<cmd> [env]')
  .action(function (cmd, env) {
    cmdValue = cmd;
    envValue = env;
  });
  
program.parse(process.argv);

if (typeof cmdValue === 'undefined') {
  console.error('no command given!');
  process.exit(1);
}
console.log('command:', cmdValue);
console.log('environment:', envValue || "no environment given");


var program = require('commander');

program
  .version('0.1.0')
  .command('install [name]', 'install one or more packages')
  .command('search [query]', 'search with optional query')
  .command('list', 'list packages installed', {isDefault: true})
  .parse(process.argv);


var program = require('commander');

program
  .version('0.1.0')
  .option('--f, --foo', 'enable some foo')
  .option('-b, --bar', 'enable some bar')
  .option('-B --baz', 'enable some baz');

program.on('--help', funciton() {
  console.log('')
  console.log('Examples:');
  console.log(' $ custom-help --help');
  console.log(' $ custom-help -h');
});

program.parse(process.argv);

console.log('stuff');


var program = require('commander');
var colors = require('colors');

program
  .version('0.1.0')
  .command('getstream [url]', 'get stream URL')
  .parse(process.argv);
  
if (!process.argv.slice(2).length) {
  program.outputHelp(make_red);
}

function make_red(txt) {
  return colors.red(txt);
}

program.on('option:verbose', function () {
  process.env.VERBOSE = this.verbose;
});

program.on('command:*', function () {
  console.error('Invalid command: %s\nSee --help for a list of available commands.', program.args.join(' '));
  process.exit(1);
});


var program = require('commander');

program
  .version('0.1.0')
  .option('-C, --chdir <path>', 'change the working direcotry')
  .option('-c, --config <path>', 'set config path. defaults to ./deploy.conf')
  .option('-T, --no-tests', 'ignore test hook')

program
  .command('setup [env]')
  .description('run setup commands for all envs')
  .option('', '')
  .action(function(env, options) {
    var mode = options.setup_mode || "normal";
    env = env || 'all';
    console.log('setup for %s env(s) with %s mode', env, mode);
  });

program
  .command('exec <cmd>')
  .alias('ex');
  .description('')
  .option('-e, --exec_mode <mode>', "Which exec mode to use")
  .action(function(cmd, options) {
    console.log('exec "%s" using %s mode', cmd, options.exec_mode);
  }).on('--help', function() {
    console.log('');
    console.log('Examples:');
    console.log('');
    console.log(' $ deploy exec sequential');
    console.log(' $ deploy exec async');
  });
  
program
  .command('*')
  .action(function(env) {
    console.log('deploying "%s"', env);
  });
  
program.parse(process.argv);
```


```
```
