# react-daterangeselector

A React component for choosing date ranges, dates and times.

### Getting Started

To get started

```jsx
import React from 'react';
import DateRangeSelector from 'react-daterangeselector';
import 'react-daterangeselector/dist/styles.min.css';

function App() {
	function callback(start, end) {
		console.log(start, end);
	}
	return (
		<>
			<h2>Date Range Selector</h2>
			<DateRangeSelector
				inputComponent={<input type='text' name='dates' className='form-control pull-right' />}
				options={{
					opens: 'left',
					buttonClasses: ['btn btn-sm'],
					applyClass: 'btn-primary',
					separator: ' to ',
					format: 'L',
					dateLimit: { days: 90 },
					ranges: {
						'Last 7 Days': [new Date('2019-10-13T00:00:00.000Z'), new Date('2019-10-19T23:59:59.999Z')],
						'Last 28 Days': [new Date('2019-09-22T00:00:00.000Z'), new Date('2019-10-19T23:59:59.999Z')],
						'October 2019': [new Date('2019-10-01T00:00:00.000Z'), new Date('2019-10-31T23:59:59.999Z')],
						'September 2019': [new Date('2019-09-01T00:00:00.000Z'), new Date('2019-09-30T23:59:59.999Z')],
						'August 2019': [new Date('2019-08-01T00:00:00.000Z'), new Date('2019-08-31T23:59:59.999Z')],
						'July 2019': [new Date('2019-07-01T00:00:00.000Z'), new Date('2019-07-31T23:59:59.999Z')],
						'June 2019': [new Date('2019-06-01T00:00:00.000Z'), new Date('2019-06-30T23:59:59.999Z')]
					},
					locale: {
						applyLabel: 'Update',
						cancelLabel: 'Clear',
						fromLabel: 'Start date',
						toLabel: 'End date',
						customRangeLabel: 'Custom'
					},
					minDate: new Date('2013-10-01T00:00:00.000Z'),
					alwaysShowCalendars: true
				}}
				callback={callback}
			/>
		</>
	);
}

export default App;
```

### Options

| Name                 | Type                        | Required | Description                                                                                                                                                                                                                                                                                     |
| -------------------- | --------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| inputComponent       | `(HTMLElement)`             | `true`   | A Component for render react-datetimeselector.                                                                                                                                                                                                                                                  |
| selectedComponent    | `(function)`                | `true`   | A function which return a string ( arguments are startDate,selector,endDate ).                                                                                                                                                                                                                  |
| updateOnOutsideClick | `(boolean)`                 | `true`   | Option to control update calender component when click outside                                                                                                                                                                                                                                  |
| callback             | `(function)`                | `true`   | A function which returns updated date.                                                                                                                                                                                                                                                          |
| hideOnScroll         | `(true or false)`           | `false`  | The component will hide on scroll body                                                                                                                                                                                                                                                          |
| state                | `(function)`                | `false`  | A callback function to get component open state (boolean)                                                                                                                                                                                                                                       |
| fixedScroll          | `(true or false)`           | `false`  | The component will block scroll while opening                                                                                                                                                                                                                                                   |
| title                | `(string)`                  | `false`  | Title of the component                                                                                                                                                                                                                                                                          |
| rangeBoundaryLabel   | `(object)`                  | `false`  | Title of the calender {left : 'Start Date', right: 'End Date' }                                                                                                                                                                                                                                 |
| dateLimit            | `(object)`                  | `false`  | Option to controll maximum selectable date limit. ex: option = {{dateLimit: { days: 90 }}}                                                                                                                                                                                                      |
| startDate            | `(Date or string)`          | `false`  | The beginning date of the initially selected date range. If you provide a string, it must match the date format string set in your locale setting.                                                                                                                                              |
| endDate              | `(Date or string)`          | `false`  | The end date of the initially selected date range.                                                                                                                                                                                                                                              |
| minDate              | `(Date or string)`          | `false`  | The earliest date a user may select.                                                                                                                                                                                                                                                            |
| maxDate              | `(Date or string)`          | `false`  | The latest date a user may select.                                                                                                                                                                                                                                                              |
| maxSpan              | `(object)`                  | `false`  | e maximum span between the selected start and end dates. Check off maxSpan in the configuration generator for an example of how to use this. You can provide any object the moment library would let you add to a date.                                                                         |
| showDropdowns        | `(true/false)`              | `false`  | Show year and month select boxes above calendars to jump to a specific month and year.                                                                                                                                                                                                          |
| minYear              | `(number)`                  | `false`  | The minimum year shown in the dropdowns when showDropdowns is set to true.                                                                                                                                                                                                                      |
| maxYear              | `(number)`                  | `false`  | The maximum year shown in the dropdowns when showDropdowns is set to true.                                                                                                                                                                                                                      |
| showWeekNumbers      | `(true/false)`              | `false`  | Show localized week numbers at the start of each week on the calendars.                                                                                                                                                                                                                         |
| showISOWeekNumbers   | `(true/false)`              | `false`  | Show ISO week numbers at the start of each week on the calendars.                                                                                                                                                                                                                               |
| timePicker           | `(true/false)`              | `false`  | Adds select boxes to choose times in addition to dates.                                                                                                                                                                                                                                         |
| timePickerIncrement  | `(number)`                  | `false`  | Increment of the minutes selection list for times (i.e. 30 to allow only selection of times ending in 0 or 30).                                                                                                                                                                                 |
| timePicker24Hour     | `(true/false)`              | `false`  | Use 24-hour instead of 12-hour times, removing the AM/PM selection.                                                                                                                                                                                                                             |
| timePickerSeconds    | `(true/false)`              | `false`  | Show seconds in the timePicker.                                                                                                                                                                                                                                                                 |
| ranges               | `(object)`                  | `false`  | Set predefined date ranges the user can select from. Each key is the label for the range, and its value an array with two dates representing the bounds of the range.                                                                                                                           |
| showCustomRangeLabel | `(true/false)`              | `false`  | Displays "Custom Range" at the end of the list of predefined ranges, when the ranges option is used. This option will be highlighted whenever the current date range selection does not match one of the predefined ranges. Clicking it will display the calendars to select a new range.       |
| alwaysShowCalendars  | `(true/false)`              | `false`  | Normally, if you use the ranges option to specify pre-defined date ranges, calendars for choosing a custom date range are not shown until the user clicks "Custom Range". When this option is set to true, the calendars for choosing a custom date range are always shown instead.             |
| opens                | `('left'/'right'/'center')` | `false`  | Whether the picker appears aligned to the left, to the right, or centered under the HTML element it's attached to.                                                                                                                                                                              |
| drops                | `('down'/'up')`             | `false`  | Whether the picker appears below (default) or above the HTML element it's attached to.                                                                                                                                                                                                          |
| buttonClasses        | `(string)`                  | `false`  | CSS class names that will be added to both the apply and cancel buttons.                                                                                                                                                                                                                        |
| applyButtonClasses   | `(string)`                  | `false`  | CSS class names that will be added only to the apply button.                                                                                                                                                                                                                                    |
| cancelButtonClasses  | `(string)`                  | `false`  | CSS class names that will be added only to the cancel button.                                                                                                                                                                                                                                   |
| locale               | `(object)`                  | `false`  | Allows you to provide localized strings for buttons and labels, customize the date format, and change the first day of week for the calendars.                                                                                                                                                  |
| singleDatePicker     | `(true/false)`              | `false`  | Show only a single calendar to choose one date, instead of a range picker with two calendars. The start and end dates provided to your callback will be the same single date chosen.                                                                                                            |
| autoApply            | `(true/false)`              | `false`  | Hide the apply and cancel buttons, and automatically apply a new date range as soon as two dates are clicked.                                                                                                                                                                                   |
| linkedCalendars      | `(true/false)`              | `false`  | When enabled, the two calendars displayed will always be for two sequential months (i.e. January and February), and both will be advanced when clicking the left or right arrows above the calendars. When disabled, the two calendars can be individually advanced and display any month/year. |
| isInvalidDate        | `(function)`                | `false`  | A function that is passed each date in the two calendars before they are displayed, and may return true or false to indicate whether that date should be available for selection or not.                                                                                                        |
| isCustomDate         | `(function)`                | `false`  | A function that is passed each date in the two calendars before they are displayed, and may return a string or array of CSS class names to apply to that date's calendar cell.                                                                                                                  |
| autoUpdateInput      | `(true/false)`              | `false`  | Indicates whether the date range picker should automatically update the value of the <input> element it's attached to at initialization and when the selected dates change.                                                                                                                     |
| parentEl             | `(string)`                  | `false`  | html selector of the parent element that the date range picker will be added to, if not provided this will be 'body'                                                                                                                                                                            |
| class             | `(string)`                  | `false`  | A custom class which append in root level (for overide css properties)                                                                                                                                                                           |

### Screenshot

![Preview][screenshot]

[screenshot]: https://raw.githubusercontent.com/anishmprasad/react-daterangeselector/master/screenshot/react-daterangeselector-01.png 'Preview screenshot'

### Licence

Apache 2.0
