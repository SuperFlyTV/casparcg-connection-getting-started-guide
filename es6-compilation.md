# Compiling for ES2015 \(ES6\)

For various reasons we have chosen to keep the default compilation targeting ES5 for now. In most cases you would like to have a modern and clean output from ES2015 instead of the much less readable code you get with the current ES5 target.

Switching to ES2015 is easy, and done in less than a minute.

You just need to change the `target`parameter of `tsconfig.json` to "ES66". At the same time, you should remove the settings for `lib`,  which we just use for the current ES5 approach.

Remember to rebuild once you have done the change to compile against the right setting.

## ES5

![](/assets/es5.png)

## ES2015 \(ES6\)

![](/assets/es6.png)

