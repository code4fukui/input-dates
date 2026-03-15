# input-dates

A date range selection component.

## Demo
[Sample application](https://code4fukui.github.io/input-dates/)

<img src=https://user-images.githubusercontent.com/1715217/122636184-cd656680-d122-11eb-8ca3-a4808ca5398a.png width=300>

## Features
- Select multiple dates
- Highlights weekends and holidays

## Usage

```html
<script type="module" src="https://code4fukui.github.io/input-dates/input-dates.js"></script>
<input-dates id="inputdates"></input-dates>

<script type="module">
inputdates.value = "2021-06-19,2021-06-18";
inputdates.onchange = () => {
  console.log(inputdates.value);
};
</script>
```

## Data / API
- Utilizes the [day-es](https://github.com/code4fukui/day-es/) library for date processing and holiday detection.

## License
MIT