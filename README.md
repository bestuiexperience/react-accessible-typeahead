react-accessible-typeahead
==============================================================================

Composable, accessible, keyboard and screen reader friendly


<img src="logo/logo.png" alt="" width="240px">

Installation
------------------------------------------------------------------------------

```
npm i react-accessible-typeahead --save
```

Usage
------------------------------------------------------------------------------

```css
@import /path/to/node_modules/react-accessible-typeahead/build/main.css;
```

```js
import Typeahead from 'react-accessible-typeahead';

<Typeahead
  // required
  // text that will be used to update the aria live region
  // probably use the onExpand, onCollapse, onSelectedindexUpdate, onSelect hook to update it with appropriate text
  // so that a screen reader user will be aware of the changes
  ariaLiveText={this.state.ariaLiveText}
  // number of available options
  numberOfOptions={this.state.numberOfOptions}

  // required
  // use the onSelectedindexUpdate, onSelect hook to perform any action corresponding to the events
  onSelectedindexUpdate={this.onSelectedindexUpdate}
  onSelect={this.onSelect}
  // getSelectedIndex accepts the HTML node that is currently mouseover-ed and returns the corresponding index
  getSelectedIndex={this.getSelectedIndex}
  // getSelectedIndex accepts the selectedindex and returns the corresponding value for it
  getSelectedValue={this.getSelectedValue}

  // optional
  // use the onExpand, onCollapse hook to perform any action corresponding to the events
  onExpand={this.onExpand}
  onCollapse={this.onCollapse}
>
  <Input
    // required
    // use onChange to fetch data, update this.state.options and numberOfOptions
    // this method will be called from TypeAhead's onChange method
    // which will be passed to Input as props
    onChange={this.onChange}

    // optional
    // pass any other props if needed
    {...props}
  />
  <Options
    // optional
    // pass any other props if needed
    {...props}
  />
</Typeahead>
```

Refer [example directory](example) for a concrete example.

The example components are also part of the distribution please access them like so:

```js
import Input from '/path/to/node_modules/react-accessible-typeahead/build/example/component/input.js';
import Options from '/path/to/node_modules/react-accessible-typeahead/build/example/component/options.js';
import TypeaheadWikipedia from '/path/to/node_modules/react-accessible-typeahead/build/example/component/typeahead-wikipedia.js';
```

Please ensure to `import` the `/path/to/node_modules/react-accessible-typeahead/build/example/main.css`

```css
@import /path/to/node_modules/react-accessible-typeahead/build/example/main.css;
```

Contributing
------------------------------------------------------------------------------
Please refer [CONTRIBUTING.md](contributing.md) for instructions to [get started](CONTRIBUTING.md#Get_Started)

License
------------------------------------------------------------------------------

This project is licensed under the [MIT](LICENSE).
