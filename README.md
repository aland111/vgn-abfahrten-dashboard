# Abfahrten v3.1

This project is a single HTML file that shows upcoming departures for VGN stops, with a simple tap-to-filter UI and a walking-time countdown.

## File
- `abfahrten.html`

## How To Use
Open the file in a browser. You can optionally pass stops and a refresh interval via query parameters.

### Stops Parameter (with walking time)
Format:
```
?stops=<id>:<name>:<walk>,<id>:<name>:<walk>,...
```

Example:
```
abfahrten.html?stops=503:Maffeiplatz:15,545:Wodanstraße:6
```

- `<id>` is the VGN stop ID
- `<name>` is the label shown in the UI (URL-encode spaces)
- `<walk>` is the walking time in minutes for that station

### Refresh Parameter
```
&refresh=30
```

- `refresh` is the refresh interval in seconds (minimum 5)

## UI Behavior
- Tap any row to filter the table to that station.
- Tap the same station again to clear the filter.

## Walking Time Column
The **"Losgehen in"** column shows how long you have before you should start walking:

```
time until departure (including delay) - walking time
```

Trips that are no longer reachable (negative result) are hidden.

## Default Stations (No Query Params)
You can permanently set defaults inside the file:

```js
const DEFAULT_STOPS = [
  { id: 561, name: 'Frankenstraße', walk: 3 }
];
```

