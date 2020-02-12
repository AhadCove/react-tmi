# React-Tmi.js

[![Build Status](https://secure.travis-ci.org/tmijs/tmi.js.png?branch=master)](https://travis-ci.org/tmijs/tmi.js)
[![Npm Version](https://img.shields.io/npm/v/tmi.js.svg?style=flat)](https://www.npmjs.org/package/tmi.js)
[![Downloads](https://img.shields.io/npm/dm/tmi.js.svg?style=flat)](https://www.npmjs.org/package/tmi.js)
[![Issues](https://img.shields.io/github/issues/tmijs/tmi.js.svg?style=flat)](https://github.com/tmijs/tmi.js/issues)
[![Node Version](https://img.shields.io/node/v/tmi.js.svg?style=flat)](https://www.npmjs.org/package/tmi.js)

![](https://i.imgur.com/r1N7y1c.png)

## Works with Create React App
This version works with Create React App for production.
There was a problem with the original tmi.js when it came to building that didn't work with CRA. Using this version will get rid of the issue and will work on CRA.


[Website](https://tmijs.com/) |
[Documentation currently at tmijs/docs](https://github.com/tmijs/docs/tree/gh-pages/_posts) |
Changelog on the [release page](https://github.com/tmijs/tmi.js/releases)

## Install

### Node

```bash
npm i tmi.js
```

```js
const tmi = require('tmi.js');
const client = new tmi.Client({
	options: { debug: true },
	connection: {
		reconnect: true,
		secure: true
	},
	identity: {
		username: 'bot-name',
		password: 'oauth:my-bot-token'
	},
	channels: [ 'my-channel' ]
});
client.connect();
client.on('message', (channel, tags, message, self) => {
	if(self) return;
	if(message.toLowerCase() === '!hello') {
		client.say(channel, `@${tags.username}, heya!`);
	}
});
```

~~~ bash
yarn add react-tmi
~~~

### Changes from forked TMI.js
Emote-sets will no longer work considering the url was sending 400 errors


#### Build Yourself

```bash
$ git clone https://github.com/ahadcove/react-tmi.git
$ yarn
$ yarn build
```

### Type Definitions

```bash
yarn add -D @types/tmi.js
```
