# About send-action

`send-action` is meant to be the smallest, simplest redux-like state management library. The focus is on providing a concise method for triggering actions, and on avoiding complex middleware & development dependencies.

The API is significantly different from redux, but the pattern is similar. 

Using `send-action` you trigger actions, modify state based on those actions, and listen to the changes to render your application.

## Source code
- [GitHub repo](https://github.com/sethvincent/send-action)
- [send-action on npm](http://npmjs.com/send-action)

## Install using npm

```sh
npm i --save send-action
```

If you don't have node & npm installed already, install the latest from [nodejs.org](https://nodejs.org).

## Basic example

```js
var sendAction = require('send-action')

/*
* Create send function.
*/
var send = sendAction({
  onaction: function (action, state) {
    // modify the state based on actions
    return state
  },
  onchange: function (action, state, oldstate) {
    // render your application
    console.log(action, state, oldstate)
  },
  state: {}
})

/*
* Send an action to the store
*/
send({ type: 'example' value: 'cool' })
```
