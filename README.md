# react-advanced-input

Advanced React time input field, based in [react-advanced-input](https://github.com/vitorgiovane/advanced-input/).

[![npm](https://img.shields.io/npm/dt/react-advanced-input.svg?colorB=brightgreen)](https://www.npmjs.com/package/react-advanced-input)
[![npm](https://img.shields.io/npm/v/react-advanced-input.svg?colorB=brightgreen)](https://www.npmjs.com/package/react-advanced-input)
[![GitHub license](https://img.shields.io/github/license/vitorgiovane/react-advanced-input.svg)](https://github.com/vitorgiovane/react-advanced-input/blob/master/LICENSE)

[![Demo](docs/demo.gif)](https://antonfisher.com/react-simple-timefield/)

## Installation
### With NPM
```bash
npm install --save react-advanced-input

#for React <16 use: npm install --save react-advanced-input@1
```
### With Yarn
```
yarn add react-advanced-input
```

## Usage
```jsx
import TimeField from 'react-simple-timefield';
...
<TimeField
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
import TimeField from 'react-simple-timefield';

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
      <TimeField value={time} onChange={this.onTimeChange} />
    );
  }
}
```

## Migrate version 2.x to version 3.x

There is a breaking change in version 3.
The `onChange` callback property will be called with two arguments.

```jsx
// Before:
<TimeField onChange={(value) => console.log(value)} />

// After:
<TimeField onChange={(event, value) => console.log(event, value)} />
```

## Contributing

#### Run demo:
For running demo locally, replace:
```javascript
import TimeField from '../';
// to
import TimeField from '../src';
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
