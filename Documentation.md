# Introduction #

How to use the datepickr code, with some examples and a list of config options available.


# Details #

The simplest method to get up and running:

```
new datepickr('inputElementId');
```

Obviously replace 'inputElementId' with the actual id of the input element you will be using.

You can also customize the datepickr experience by passing in some extra options. The default values that can be overridden are:

## Config Options ##

```
new datepickr('inputElementId', {
    fullCurrentMonth: true,
    dateFormat: 'F jS, Y',
    weekdays: ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'],
    months: ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'],
    suffix: { 1: 'st', 2: 'nd', 3: 'rd', 21: 'st', 22: 'nd', 23: 'rd', 31: 'st' },
    defaultSuffix: 'th'
});
```

| **Config Option** | **Data Type** | **Description** |
|:------------------|:--------------|:----------------|
| fullCurrentMonth  | boolean       | Whether or not the full month name should be shown in the calendar. If set to false, only the first three characters of the month will be displayed. |
| dateFormat        | string        | A string of characters which are used to define how the date will be displayed in the input box. Very similar to the PHP date function, but with less options. The supported characters are defined below. |
| weekdays          | array         | An array of strings to define the weekdays, for localization purposes, starts at Sunday. |
| months            | array         | An array of strings to define the months, for localization purposes, starts at January. |
| suffix            | object        | A list of suffixes, for localization purposes, each key (day) should be associated with the correct suffix. |
| defaultSuffix     | string        | A default suffix, for localization purposes, that will be used if there is no suffix defined for a key (day). |

## Date Format ##

| **Character** | **Description** | **Example** |
|:--------------|:----------------|:------------|
| **d**         | Day of the month, 2 digits with leading zeros | **01** to **31** |
| **D**         | A textual representation of a day, three letters | **Mon** through **Sun** |
| **j**         | Day of the month without leading zeros | **1** to **31** |
| **l** (lowercase 'L') | A full textual representation of the day of the week | **Sunday** through **Saturday** |
| **S**         | Ordinal suffix for the day of the month, as defined by the suffix config option | **st**, **nd**, **rd** or **th**. |
| **w**         | Numeric representation of the day of the week | **0** (for Sunday) through **6** (for Saturday) |
| **F**         | A full textual representation of a month | **January** through **December** |
| **m**         | Numeric representation of a month, with leading zero | **00** through **11** |
| **M**         | A short textual representation of a month, three letters | **Jan** through **Dec** |
| **n**         | Numeric representation of a month, without leading zeros | **0** through **11** |
| **Y**         | A full numeric representation of a year, 4 digits | **1999** or **2003** |
| **y**         | A two digit representation of a year | **99** or **03** |

## Escaping date format characters ##

To escape a character (if you need to use one of the reserved format characters above) use a double backslash: \\

Example:

```
dateFormat: '\\Da\\y picke\\d: Y/m/d'
```

To get something like:

**Day picked: 2013/02/12**

If you do not escape the characters you would end up with something like this instead:

**Tuea13 picke12: 2013/02/12**

Which is probably not what you want...