<img src="https://raw.githubusercontent.com/ahdcreative/vpilotshub-branding/main/SVG/logo.svg" width="300px" height="auto">
# vPilotsHub API Client

Official Javascript client for the vPHub API.
This library supports Javascript and Typescript.

## Install
Install via npm:
    $ npm i @ahdcreative/vpilotshub-api

## Use
### client init
```ts
import { NXApi } from '@ahdcreative/vpilotshub-api';

NXApi.url = new URL('http://localhost:3000');
```

By default, the URL is set to `https://api.ahd-creative.agency/vpilotshub`. Can be changed to whatever url you like.

### METAR
```ts
import { Metar } from '@ahdcreative/vpilotshub-api';

Metar.get(icao, source)
  .then(data => {
    console.log(data);
  }).catch(err => {
    console.error(err);
});
```

- `icao` is a string of the ICAO code of the Airport for getting the METAR.
- `source` is the selected datasource for the METAR and is _optional_.

Valid Sources are:
- vatsim
- ms
- ivao
- pilotedge
- aviationweather

### TAF
```ts
import { Taf } from '@ahdcreative/vpilotshub-api';

Taf.get(icao, source)
  .then(data => {
    console.log(data);
  }).catch(err => {
    console.error(err);
});
```

- `icao` is a string of the ICAO code of the Airport for getting the TAF.
- `source` is the selected datasource for the METAR and is _optional_.

Valid Sources are:
- aviationweather
- faa

### ATIS
```ts
import { Atis } from '@ahdcreative/vpilotshub-api';

Atis.get(icao, source)
  .then(data => {
    console.log(data);
  }).catch(err => {
    console.error(err);
});
```

- `icao` is a string of the ICAO code of the Airport for getting the ATIS.
- `source` is the selected datasource for the METAR and is _optional_.

Valid Sources are:
- vatsim
- faa
- ivao
- pilotedge

### Airport
```ts
import { Airport } from '@ahdcreative/vpilotshub-api';

Airport.get(icao)
  .then(data => {
    console.log(data);
  }).catch(err => {
    console.error(err);
});
```

- `icao` is a string of the ICAO code of the Airport.

### ATC
```ts
import { ATC } from '@ahdcreative/vpilotshub-api';

ATC.get(source)
  .then(data => {
    console.log(data);
  }).catch(err => {
    console.error(err);
});
```

- `source` is the selected datasource for the ATC.
  Valid sources are:
    - vatsim
    - ivao

### Hoppie

#### Send the request
```ts
import { Hoppie } from '@ahdcreative/vpilotshub-api';

const body {
  logon: 'XXXXXXXXX',
  from: 'TEST0',
  to: 'TEST0',
  type: 'poll'
}
Hoppie.post(body)
  .then(data => {
    console.log(data);
  }).catch(err => {
    console.error(err);
});
```
