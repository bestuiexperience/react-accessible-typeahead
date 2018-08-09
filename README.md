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
@import /path/to/node_modules/react-accessible-typeahead/build/main.css
```

```js
import Typeahead from 'react-accessible-typeahead';

<Typeahead
  // required
  // text that will be used to update the aria live region
  // probably use the onExpand, onCollapse, onSelectedindexUpdate, onSelect hook to update it with appropriate text
  // so that a screen reader user will be aware of the changes
  ariaLiveText={this.state.ariaLiveText}

  // optional
  // default value is false, pass it if you need to clear out the textbox on selection.
  clearInputOnSelect={true}

  // required
  // use the onSelectedindexUpdate, onSelect hook to perform any action corresponding to the events
  onSelectedindexUpdate={this.onSelectedindexUpdate}
  onSelect={this.onSelect}

  // optional
  // use the onExpand, onCollapse hook to perform any action corresponding to the events
  onExpand={this.onExpand}
  onCollapse={this.onCollapse}
>
  <Input
    // required
    // use onChange to fetch data and update this.state.options
    onChange={this.onChange}

    // optional
    // pass any other props if needed
    {...props}
  />
  <Options
    // required
    // options will be used by the TypeAhead to identify the text for the currently selected option
    options={this.state.options}

    // optional
    // pass any other props if needed
    {...props}
  />
</Typeahead>
```

Refer [example directory](example) for a concrete example.

Contributing
------------------------------------------------------------------------------
Please refer [CONTRIBUTING.md](contributing.md) for instructions to [get started](CONTRIBUTING.md#Get_Started)

License
------------------------------------------------------------------------------

This project is licensed under the [MIT](LICENSE).
