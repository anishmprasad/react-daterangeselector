# react-daterangeselector

### Options

The beginning date of the initially selected date range. If you provide a string, it must match the date format string set in your locale setting.

| Name                 | Type                        | Required | Description                                                                                                                                                                                                                                                                                     |
| -------------------- | --------------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| startDate            | `(Date or string)`          | `true`   | The beginning date of the initially selected date range. If you provide a string, it must match the date format string set in your locale setting.                                                                                                                                              |
| endDate              | `(Date or string)`          | `true`   | The end date of the initially selected date range.                                                                                                                                                                                                                                              |
| minDate              | `(Date or string)`          | `true`   | The earliest date a user may select.                                                                                                                                                                                                                                                            |
| maxDate              | `(Date or string)`          | `true`   | The latest date a user may select.                                                                                                                                                                                                                                                              |
| maxSpan              | `(object)`                  | `true`   | e maximum span between the selected start and end dates. Check off maxSpan in the configuration generator for an example of how to use this. You can provide any object the moment library would let you add to a date.                                                                         |
| showDropdowns        | `(true/false)`              | `true`   | Show year and month select boxes above calendars to jump to a specific month and year.                                                                                                                                                                                                          |
| minYear              | `(number)`                  | `true`   | The minimum year shown in the dropdowns when showDropdowns is set to true.                                                                                                                                                                                                                      |
| maxYear              | `(number)`                  | `true`   | The maximum year shown in the dropdowns when showDropdowns is set to true.                                                                                                                                                                                                                      |
| showWeekNumbers      | `(true/false)`              | `true`   | Show localized week numbers at the start of each week on the calendars.                                                                                                                                                                                                                         |
| showISOWeekNumbers   | `(true/false)`              | `true`   | Show ISO week numbers at the start of each week on the calendars.                                                                                                                                                                                                                               |
| timePicker           | `(true/false)`              | `true`   | Adds select boxes to choose times in addition to dates.                                                                                                                                                                                                                                         |
| timePickerIncrement  | `(number)`                  | `true`   | Increment of the minutes selection list for times (i.e. 30 to allow only selection of times ending in 0 or 30).                                                                                                                                                                                 |
| timePicker24Hour     | `(true/false)`              | `true`   | Use 24-hour instead of 12-hour times, removing the AM/PM selection.                                                                                                                                                                                                                             |
| timePickerSeconds    | `(true/false)`              | `true`   | Show seconds in the timePicker.                                                                                                                                                                                                                                                                 |
| ranges               | `(object)`                  | `true`   | Set predefined date ranges the user can select from. Each key is the label for the range, and its value an array with two dates representing the bounds of the range.                                                                                                                           |
| showCustomRangeLabel | `(true/false)`              | `true`   | Displays "Custom Range" at the end of the list of predefined ranges, when the ranges option is used. This option will be highlighted whenever the current date range selection does not match one of the predefined ranges. Clicking it will display the calendars to select a new range.       |
| alwaysShowCalendars  | `(true/false)`              | `true`   | Normally, if you use the ranges option to specify pre-defined date ranges, calendars for choosing a custom date range are not shown until the user clicks "Custom Range". When this option is set to true, the calendars for choosing a custom date range are always shown instead.             |
| opens                | `('left'/'right'/'center')` | `true`   | Whether the picker appears aligned to the left, to the right, or centered under the HTML element it's attached to.                                                                                                                                                                              |
| drops                | `('down'/'up')`             | `true`   | Whether the picker appears below (default) or above the HTML element it's attached to.                                                                                                                                                                                                          |
| buttonClasses        | `(string)`                  | `true`   | CSS class names that will be added to both the apply and cancel buttons.                                                                                                                                                                                                                        |
| applyButtonClasses   | `(string)`                  | `true`   | CSS class names that will be added only to the apply button.                                                                                                                                                                                                                                    |
| cancelButtonClasses  | `(string)`                  | `true`   | CSS class names that will be added only to the cancel button.                                                                                                                                                                                                                                   |
| locale               | `(object)`                  | `true`   | Allows you to provide localized strings for buttons and labels, customize the date format, and change the first day of week for the calendars.                                                                                                                                                  |
| singleDatePicker     | `(true/false)`              | `true`   | Show only a single calendar to choose one date, instead of a range picker with two calendars. The start and end dates provided to your callback will be the same single date chosen.                                                                                                            |
| autoApply            | `(true/false)`              | `true`   | Hide the apply and cancel buttons, and automatically apply a new date range as soon as two dates are clicked.                                                                                                                                                                                   |
| linkedCalendars      | `(true/false)`              | `true`   | When enabled, the two calendars displayed will always be for two sequential months (i.e. January and February), and both will be advanced when clicking the left or right arrows above the calendars. When disabled, the two calendars can be individually advanced and display any month/year. |
| isInvalidDate        | `(function)`                | `true`   | A function that is passed each date in the two calendars before they are displayed, and may return true or false to indicate whether that date should be available for selection or not.                                                                                                        |
| isCustomDate         | `(function)`                | `true`   | A function that is passed each date in the two calendars before they are displayed, and may return a string or array of CSS class names to apply to that date's calendar cell.                                                                                                                  |
| autoUpdateInput      | `(true/false)`              | `true`   | Indicates whether the date range picker should automatically update the value of the <input> element it's attached to at initialization and when the selected dates change.                                                                                                                     |
| parentEl             | `(string)`                  | `true`   | jQuery selector of the parent element that the date range picker will be added to, if not provided this will be 'body'                                                                                                                                                                          |
