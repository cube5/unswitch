# Unswitch

[![npm version](https://img.shields.io/npm/v/unswitch.svg)](https://www.npmjs.com/package/unswitch)
[![gzip size](http://img.badgesize.io/https://unpkg.com/unswitch/dist/unswitch.es.js?compression=gzip)](https://unpkg.com/unswitch)
[![license](https://img.shields.io/npm/l/unswitch.svg)](https://github.com/vaneenige/unswitch/blob/master/LICENSE)
[![dependencies](https://img.shields.io/badge/dependencies-none-ff69b4.svg)](https://github.com/vaneenige/unswitch/blob/master/package.json)

Unswitch is a tiny (400b) event handler for Switch controllers on the web based on the Gamepad API. Attach callbacks to button presses (up & down) and the joystick!

## Install

```
$ npm install --save unswitch
```

## Usage

```js
// Import the library
import Unswitch from 'unswitch';

// Create the listener
const unswitch = new Unswitch({
  b: (pressed) => {},
  a: (pressed) => {},
  y: (pressed) => {},
  x: (pressed) => {},
  l: (pressed) => {},
  r: (pressed) => {},
  axes: (position) => {},
});

function render() {
  // Check for button stateupdates
  unswitch.update();
  requestAnimationFrame(render);
}

render();
```

Calling `unswitch.update()` will check every button for a change in state. If a callback is provided the new state is passed along. The axis works in the same way, but instead of a `boolean` it will return a `number` from 0 to 8. Number 0 to 7 are for the joystick positions going clockwise, number 8 is used as default (center).

> Buttons are mapped based on a single controller positioned horizontally.

## Contribute

Are you excited about this library and have interesting ideas on how to improve it? Please tell me or contribute directly! 🙌

```
npm install > npm run demo > http://localhost:8080
```

## License

MIT © <a href="https://use-the-platform.com">Colin van Eenige</a>
