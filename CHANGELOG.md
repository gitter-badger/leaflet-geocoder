## v1.0.0-alpha
### Breaking changes
- The default endpoint is now Mapzen Search service, powered by Pelias v1.0.
- An API key is required to use Mapzen Search service. You can get a free API key from the [Mapzen developers portal](https://mapzen.com/developers/).
- File and directory structure reworked in accordance to [Leaflet Plugin Authoring Guide](http://leafletjs.com/2013/06/28/leaflet-plugin-authoring-guide.html).
- `hide_other_controls` is removed.
- `drop_pin` is renamed to `markers`.
- `bbox` is renamed to `bounds` to match Leaflet terminology.
- `latlon` is renamed to `latlng` to match Leaflet terminology.
- `expanded` now defaults to `false`. Please set it to `true` explicitly if that is your desired behavior.
- All options names that were previously snake_case are now camelCase.
- CSS class names are now namespaced to `.leaflet-pelias-*` instead of `.pelias-*`. This may affect style overrides.

### New features
- Support for Bower and npm package install
- Support module loading systems (e.g. CommonJS / AMD)
- `markers` (formerly `drop_pin`) option can accept a Leaflet Marker options object for customizable markers.
- `fullWidth` (formerly `full_width`) no longer hard codes a default mobile breakpoint. It now accepts any integer to use as a breakpoint (default remains `650` pixels). The plugin will also now resize the full-width of the input if the window size changes, which allows custom breakpoints to be meaningful for responsive design.
- New `autocomplete` option allows customizing whether results are obtained on each keystroke or only after a user presses Enter. This can help reduce queries if you need to manage your API usage.
- Support for IE8 and IE9.
- The plugin no longer attempts to "detect" a mobile environment. It relies on Leaflet's `leaflet-touch` state to alter behavior for touch-enabled environments.
- There is now support for collapsed state of the input bar. Clicking the search icon toggles the expanded state of the input, if `expanded` is not `true`.
- Improved documentation and examples.
- Added code linting ([Semistandard](https://github.com/Flet/eslint-config-semistandard)) and tests.

### Bug fixes
- If `fullWidth` is true, an expanded input box is now constrained to the width of the map container rather than the window.
- Fix a bug where typing one character into the input box improperly hides the close button.
- If geocoder is placed on the bottom of the map, the results box should now open above the input.

### Styling
- All styles have been revamped for better integration with Leaflet.
- Search/loading icon is now a separate DOM element from the input box for easier customization.
- Resize default background images to appear at the correct size in IE8.

## v0.0.2

- added layer customization to build a coarse/address geocoders easily

## v0.0.1

- initial release
- supports lat/lon, bbox, placeholder
