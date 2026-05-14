# input-dates

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A lightweight, dependency-free web component for selecting single or multiple dates from a calendar view.

## Demo

[Try the live demo](https://code4fukui.github.io/input-dates/)

<img src="https://user-images.githubusercontent.com/1715217/122636184-cd656680-d122-11eb-8ca3-a4808ca5398a.png" width="300" alt="Screenshot of the input-dates calendar component">

## Features

- **Multi-Date Selection**: Select multiple individual dates.
- **Single-Date Mode**: Restrict selection to a single date.
- **Date Highlighting**: Automatically highlights weekends and Japanese holidays.
- **Availability Control**: Programmatically define which dates are selectable.
- **Zero Dependencies**: A standalone web component imported directly as an ES module.
- **Simple API**: Interact with the component using standard properties and events.

## Usage

Add the script tag to your HTML file. No build step or installation is required.

```html
<script type="module" src="https://code4fukui.github.io/input-dates/input-dates.js"></script>

<input-dates id="my-calendar"></input-dates>

<script type="module">
  const calendar = document.getElementById('my-calendar');

  // Set initial selected dates
  calendar.value = "2021-06-19,2021-06-18";

  // Listen for changes
  calendar.onchange = () => {
    console.log('Selected dates:', calendar.value);
  };
</script>
```

## API Reference

### Attributes

- `single`
  - If this boolean attribute is present, the component will operate in single-date selection mode.
  - **Example**: `<input-dates single></input-dates>`

### Properties

- `.value`
  - **Type**: `String`
  - **Description**: A getter/setter for the selected dates. The value is a comma-separated string of dates in `YYYY-MM-DD` format.
  - **Example**: `calendar.value = "2023-10-26,2023-10-31";`

### Methods

- `.setAvailable(dates)`
  - **Description**: Restricts the set of dates that the user can select. All other dates will be disabled.
  - **Parameters**:
    - `dates`: `String` | `Array<String|Day>` - A comma-separated string of dates, or an array of date strings or `Day` objects from the `day-es` library.
  - **Example**:
    ```javascript
    // Using a comma-separated string
    calendar.setAvailable("2023-12-24,2023-12-25,2023-12-31");

    // Using an array of strings
    calendar.setAvailable(["2024-01-01", "2024-01-02"]);
    ```

- `.clear()`
  - **Description**: Deselects all currently selected dates.

### Events

- `onchange`
  - **Description**: A handler that fires whenever the selection is changed by the user.
  - **Example**: `calendar.onchange = () => { /* ... */ };`

## Dependencies

- This component utilizes the [day-es](https://github.com/code4fukui/day-es/) library for date calculations and Japanese holiday detection. It is loaded dynamically and does not need to be installed separately.

## License

MIT License