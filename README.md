# react-advanced-time-input

Advanced React time input time, based in [react-simple-timefield](https://github.com/antonfisher/react-simple-timefield).

[![npm](https://img.shields.io/npm/dt/react-advanced-time-input.svg?colorB=brightgreen)](https://www.npmjs.com/package/react-advanced-time-input)
[![npm](https://img.shields.io/npm/v/react-advanced-time-input.svg?colorB=brightgreen)](https://www.npmjs.com/package/react-advanced-time-input)
[![GitHub license](https://img.shields.io/github/license/vitorgiovane/react-advanced-time-input.svg)](https://github.com/vitorgiovane/react-advanced-time-input/blob/master/LICENSE)

[![Demo](docs/demo.gif)](https://antonfisher.com/react-simple-timefield/)

## Installation
### With NPM
```bash
npm install --save react-advanced-time-input

#for React <16 use: npm install --save react-advanced-time-input@1
```
### With Yarn
```
yarn add react-advanced-time-input
```

## Usage
```jsx
import TimeInput from 'react-advanced-time-input';
...
<TimeInput
    value={time}                       // {String}   required, format '00:00' or '00:00:00'
    onChange={(event, value) => {...}} // {Function} required
    input={<MyCustomInputElement />}   // {Element}  default: <input type="text" />
    inputRef={(ref) => {...}}          // {Function} input's ref
    colon=":"                          // {String}   default: ":"
    showSeconds                        // {Boolean}  default: false
    maxHours                           // {Integer}  default: 23
    maxMinutes                         // {Integer}  default: 59
    maxSeconds                         // {Integer}  default: 59
/>
```

## Real world example
```jsx
import TimeInput from 'react-advanced-time-input';

class App extends React.Component {
  constructor(...args) {
    super(...args);

    this.state = {
      time: '12:34'
    };

    this.onTimeChange = this.onTimeChange.bind(this);
  }

  onTimeChange(event, time) {
    this.setState({time});
  }

  render() {
    const {time} = this.state;

    return (
      <TimeInput value={time} onChange={this.onTimeChange} />
    );
  }
}
```

## Migrate version 2.x to version 3.x

There is a breaking change in version 3.
The `onChange` callback property will be called with two arguments.

```jsx
// Before:
<TimeInput onChange={(value) => console.log(value)} />

// After:
<TimeInput onChange={(event, value) => console.log(event, value)} />
```

## Contributing

#### Run demo:
For running demo locally, replace:
```javascript
import TimeInput from '../';
// to
import TimeInput from '../src';
```
in `demo/index.tsx` file.

```bash
# run development mode
cd demo
npm install
npm install --only=dev
npm run dev
```

#### Build:
```bash
npm install
npm install --only=dev
npm test
npm run format
npm run build
```

## License
MIT License. Free use and change.
