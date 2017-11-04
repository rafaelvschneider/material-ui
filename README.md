# Material-UI pickers
[![npm package](https://img.shields.io/npm/v/material-ui-pickers.svg)](https://www.npmjs.org/package/material-ui-pickers)
[![Build Status](https://api.travis-ci.org/dmtrKovalenko/material-ui-pickers.svg?branch=master)](https://travis-ci.org/dmtrKovalenko/material-ui-pickers)
> Components, that implements material design date and time pickers for material-ui v1

## [Click here for demo](https://material-ui-pic.firebaseapp.com/)

### Recently updated?
Changelog available [here](https://github.com/dmtrKovalenko/material-ui-pickers/releases)

### Installation
Available as npm package
```sh
npm install material-ui-pickers -S
```

We are using material-ui-icons font to display icons. We are working on additional way to pass icons,but for now its required. Just add this to your html 
```html
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

### Usage
Here is a quick example of how to use this package

```jsx
import { TimePicker, DatePicker, DateTimePicker } from 'material-ui-pickers'

class App extends Component {
  state = {
    selectedDate: new Date(),
    selectedTime: new Date(),
    selectedDateTime: new Date()
  }

  handleDateChange = date => {
    this.setState({ selectedDate: date })
  }

  handleTimeChange = time => {
    this.setState({ selectedTime: time })
  }

  handleDateTimeChange = dateTime => {
    this.setState({ selectedDateTime: dateTime })
  }

  render() {
    const { selectedDate, selectedTime, selectedDateTime } = this.state

    return (
      <div>
        <DatePicker
          value={selectedDate}
          onChange={this.handleDateChange}
        />

        <TimePicker
          value={selectedTime}
          onChange={this.handleDateChange}
        />

        <DateTimePicker
          value={this.state.selectedDateTime}
          onChange={this.handleDateTimeChange}
        />
      </div>
    )
  }
}
```

### Props documentation
Here is a list of available props

#### Datepicker
* date - string, number, Date object, Moment object ([anything](https://momentjs.com/docs/#/parsing/), that can be parsed by moment)

Prop | Type | Default | Definition
------------ | ------------- | ------------- | -------------
value | date | new Date() | Datepicker value
format | string | 'MMMM Do' | Moment format string for input
autoOk | boolean | false | Auto accept date on selection
disableFuture | boolean | false | Disable future dates
animateYearScrolling | boolean | false | Will animate year selection (note that will work for browser supports scrollIntoView api)
openToYearSelection | boolean | false | Open datepicker from year selection
minDate | date | '1900-01-01' | Minimum selectable date
maxDate | date | '2100-01-01' | Maximum selectable date
onChange | func | required | Callback firing when date accepted
returnMoment | boolean | true | Will return moment object in onChange
invalidLabel | string | 'Unknown' | Displayed string if date cant be parsed (or null)
leftArrowIcon | react node, string | 'keyboard_arrow_left'| Left arrow icon
rightArrowIcon | react node, string | 'keyboard_arrow_right'| Right arrow icon

#### Timepicker
Prop | Type | Default | Definition
------------ | ------------- | ------------- | -------------
value | date | new Date() | Timepicker value
format | string | 'MMMM Do' | Moment format string for input
autoOk | boolean | false | Auto accept time on selection
onChange | func | required | Callback firing when date accepted
returnMoment | boolean | true | Will return moment object in onChange
invalidLabel | string | 'Unknown' | Displayed string if date cant be parsed (or null)

#### DateTimepicker
Prop | Type | Default | Definition
------------ | ------------- | ------------- | -------------
value | date | new Date() | Timepicker value
format | string | 'MMMM Do hh:mm a' | Moment format string for input
autoOk | boolean | false | Auto accept time on selection
autoSubmit | boolean | true | On change show next time input (year -> date -> hour -> minute)
showTabs | boolean | false | Show date/time tabs
openTo | one of 'year', 'date', 'hour', 'minutes' | 'date' | Open to particular view
animateYearScrolling | boolean | false | Will animate year selection
minDate | date | '1900-01-01' | Minimum selectable date
maxDate | date | '2100-01-01' | Maximum selectable date
onChange | func | required | Callback firing when date accepted
returnMoment | boolean | true | Will return moment object in onChangeg
invalidLabel | string | 'Unknown' | Displayed string if date cant be parsed (or null)
leftArrowIcon | react node, string | 'keyboard_arrow_left'| Left arrow icon
rightArrowIcon | react node, string | 'keyboard_arrow_right'| Right arrow icon
dateRangeIcon | react node, string | 'date_range'| Date tab icon 
timeIcon | react node, string | 'access_time'| Time tab icon


### Known Issues
1. 24 hour displaying for timepicker (now supporting only am/pm)

They would be added/fixed in one of the nearest release :)

### Contributing
For information about how to contribute, see the [CONTRIBUTING](https://github.com/dmtrKovalenko/material-ui-pickers/blob/master/CONTRIBUTING.md) file.

### LICENSE
The project is licensed under the terms of [MIT license](https://github.com/dmtrKovalenko/material-ui-pickers/blob/master/LICENSE)
