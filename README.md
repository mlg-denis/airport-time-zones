# Airport time zones

The time zone of each of 9397 airports, as used by a flight log app to work out flight times. One row per airport in `airport-time-zones.csv`:

- `ourairports_id`: the airport's id in OurAirports
- `iata`, `icao`: its codes (`icao` is empty where it has none)
- `name`
- `latitude`, `longitude`: in degrees, from OurAirports
- `time_zone`: its IANA time zone, e.g. `Europe/London`

## How it's made

Each airport gets the zone whose area contains its coordinates, in timezone-boundary-builder's map, release 2026c: the full set, with oceans (a point just offshore gets an ocean zone such as `Etc/GMT+8`). Where the map has two zones over the same place, airports there get the one their flights use:

- `Asia/Shanghai`, not `Asia/Urumqi`
- `Europe/Moscow`, not `Asia/Tbilisi`

## Sources

- Airports and their coordinates: [OurAirports](https://ourairports.com/data/) (Public domain).
- Time zone areas: [timezone-boundary-builder](https://github.com/evansiroky/timezone-boundary-builder) (ODbL 1.0), made from OpenStreetMap data, © OpenStreetMap contributors.

## Licence

This table is made available under the [Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/), as it's derived from timezone-boundary-builder's map.
