# Longdo Map region's overlay example

This repo shows you how to overlays Thailand's region on Longdo Map.

![Longdo Map region's overlay example](https://github.com/MetamediaTechnology/longdo-map-overlay-region/blob/main/thumbnail-region.jpg)

## Demo
- [Longdo Map draws region's overlay](https://mapdemo.longdo.com/map-region/)

## Usage

### STEP 1: Get a Key API & Loading the Map API's script

Entering [Longdo map console website](https://map.longdo.com/console) for registering to be a member of Longdo Map.

```javascript
<script src="https://api.longdo.com/map/?key=[YOUR_KEY_API]"></script>
```

### STEP 2: Initialize the Map

Using JavaScript function for creating longdo.Map object within a tag

```javascript
var map;
function init() {
  map = new longdo.Map({
    placeholder: document.getElementById('map')
  });
}
```

### STEP 3: Complete with HTML

To create Div element and use `onload` function for creating map within tag

```php
<body onload="init();">
  <div id="map"></div>
</body>
```
### STEP 4: Create district object

```javascript
// Region by geographical
var region_geographical = [
    { 'name': 'กลาง', 'color': '#ffadadaa', 'pivot': { lat: 15.464000, lon: 100.281979 }, 'geocode': '1_;26;60;61;62;64;65;66;67;72;73;74;75' },
    { 'name': 'ใต้', 'color': '#ffd6a5aa', 'pivot': { lat: 8.624196, lon: 98.908688 }, 'geocode': '80;81;82;83;84;85;86;90;91;92;93;94;95;96' },
    { 'name': 'เหนือ', 'color': '#9bf6ffaa', 'pivot': { lat: 18.843649, lon: 99.556881 }, 'geocode': '5_' },
    { 'name': 'ตะวันออกเฉียงเหนือ', 'color': '#bdb2ffaa', 'pivot': { lat: 16.182756, lon: 102.589108 }, 'geocode': '3_;4_' },
    { 'name': 'ตะวันตก', 'color': '#caffbfaa', 'pivot': { lat: 14.476964, lon: 98.980099 }, 'geocode': '63;70;71;76;77' },
    { 'name': 'ตะวันออก', 'color': '#a0c4ffaa', 'pivot': { lat: 13.330559, lon: 101.633297 }, 'geocode': '20;21;22;23;24;25;27' }
]

region_geographical.forEach(element => {
    let object = new longdo.Overlays.Object(element.geocode, 'IG', {
        title: element.name,
        label: element.name,
        pivot: element.pivot,
        lineColor: '#000',
        lineWidth: 1,
        fillColor: element.color,
        combine: true
    });

    map.Overlays.load(object);
});
```

Learn more: [District Object](https://map.longdo.com/docs/javascript/geometry/districtobject)

## Reference
- [JavaScript Documentation](https://map.longdo.com/docs/)
