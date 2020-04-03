# Top Level API

So as to make the navigation API as consistent and homogenous as possible, we begin with a single, unifying function -- setRoot. SetRoot receives properties for any kind of layout, whether tabs or stacks, or a combination of both \(as seen in this example.\)

See [Layout types](https://github.com/jasonhealy/react-native-navigation/tree/1581780d2ca66acebdb149751afa1bb4afc1c59e/docs/docs/docs/layout-types/README.md)

## setRoot\(layout\)

```javascript
Navigation.setRoot({
  root: {
    bottomTabs: {
      children: [{
        stack: {
          children: [{
            component: {
              name: 'example.FirstTabScreen',
              passProps: {
                text: 'This is tab 1'
              }
            }
          }],
          options: {
            bottomTab: {
              text: 'Tab 1',
              icon: require('../images/one.png'),
              testID: 'FIRST_TAB_BAR_BUTTON'
            }
          }
        }
      },
      {
        component: {
          name: 'navigation.playground.TextScreen',
          passProps: {
            text: 'This is tab 2'
          },
          options: {
            bottomTab: {
              text: 'Tab 2',
              icon: require('../images/two.png'),
              testID: 'SECOND_TAB_BAR_BUTTON'
            }
          }
        }
      }]
    }
  }
});
```

## showOverlay\(layout = {}\)

Shows a component as an overlay.

```javascript
Navigation.showOverlay({
  component: {
    name: 'example.Overlay',
    options: {
      overlay: {
        interceptTouchOutside: true
      }
    }
  }
});
```

## dismissOverlay\(componentId\)

Dismisses an overlay matching the given overlay componentId.

```javascript
Navigation.dismissOverlay(this.props.componentId);
```

