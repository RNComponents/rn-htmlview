rn-htmlview
---

> This is a custom fork of [react-native-htmlview](https://github.com/jsdf/react-native-htmlview)

A component which takes HTML content and renders it as native views, with
customizable style and handling of links, etc.

### Usage

props:

- `direction`: the flexDirection of element of the children
- `value`: a string of HTML content to render
- `onLinkPress`: a function which will be called with a url when a link is pressed.
  Passing this prop will override how links are handled (defaults to calling `LinkingIOS.openURL(url)`)
- `stylesheet`: a stylesheet object keyed by tag name, which will override the
  styles applied to those respective tags.
- `renderNode`: a custom function to render HTML nodes however you see fit. If
  the function returns `undefined` (not `null`), the default renderer will be
  used for that node.

### Example

```js
var React = require('rn-htmlview')
var {Text, View, ListView} = React

var HTMLView = require('react-native-htmlview')

var ContentView = React.createClass({
  render() {
    return (
      var htmlContent = '<p><a href="">&hearts; nice job!</a></p>'
      <HTMLView
        value={htmlContent}
        onLinkPress={(url) => console.log('navigating to: ', url)}
        stylesheet={styles}
      />
    )
  }
})

var styles = StyleSheet.create({
  a: {
    fontWeight: '300',
    color: '#FF3366', // pink links
  },
})
```

### History

See [HISTORY](HISTORY.md)
