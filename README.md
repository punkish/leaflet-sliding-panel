# Leaflet Sliding Panel
*suitable for mobile*

Add the requisite JS and CSS to your web page

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/leaflet@1.9.4/dist/leaflet.css" integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY=" crossorigin="" />
<link rel="stylesheet" href="../src/slidingpanel.css">

<div id="map"></div>

<script src="https://cdn.jsdelivr.net/npm/leaflet@1.9.4/dist/leaflet.js" integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo=" crossorigin=""></script>
<script src="../src/slidingpanel.js"></script>
```

Then, initialize a map, a marker and a sliding panel

```js
<script>
const map = L.map('map').setView([0, 0], 6);
L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '&copy; OpenStreetMap'
}).addTo(map);

const marker = L.marker([0, 0]).addTo(map);
marker.on('click', function() {
    const content = `<h1>Center of the World</h1><p>Welcome to where it all starts</p>`;
    const features = null; // []
    const options = {
        state: 'minimal' // 'closed' | 'full'
    };

    map.openPanel(content, features, options);
});
</script>
```

Optionally, customize the look of the sliding panel by adding and modifying the following classes (see `slidingpanel.css` for more ideas)

```css
.lsp-handle {
    height: 2px;
    color: lightgray;
    background-color: lightgray;
}
.lsp-content {
    padding: 10px;
}
.lsp-card {
    background-color: lightgray;
}
.lsp-nav button {
    width: 2em;
    height: 2em;
    border-radius: 2em;
}
```