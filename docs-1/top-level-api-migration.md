# Top Level API Migration

In order to make our API homogenous as much as possible, we provide setRoot function that will receive layout of any kind.

## registerComponent

Registering screens without redux or any wrapping providers is the same as in v1.

```javascript
Navigation.registerComponent('example.FirstTabScreen', () => FirstTabScreen);
```

### Registering screens with wrapping provider component

```javascript
Navigation.registerComponent('navigation.playground.ReduxScreen', () => (props) => (
  <Provider store={reduxStore}>
    <ReduxScreen {...props} />
  </Provider>
), () => ReduxScreen);
```

!&gt;Note that `Navigation.registerComponentWithRedux` is deprecated

## startTabBasedApp\(params\) -&gt; setRoot\({bottomTabs}\)

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

## startSingleScreenApp\(params\) -&gt; setRoot\({stack}\)

Change your app root into an app based on a single screen \(like the iOS Calendar or Settings app\). The screen will receive its own navigation stack with a native nav bar

```javascript
Navigation.setRoot({
  root: {
    stack: {
      children: [{
        component: {
          name: 'example.WelcomeScreen',
          passProps: {
            text: 'stack with one child'
          }
        }
      }],
      options: {
        topBar: {
          title: {
            text: 'Welcome screen'
          }
        }
      }
    }
  }
});
```

## showModal\(params = {}\) -&gt; showModal\(layout = {}\)

Show a screen as a modal.

```javascript
Navigation.showModal({
  stack: {
    children: [{
      component: {
        name: 'example.ModalScreen',
        passProps: {
          text: 'stack with one child'
        },
        options: {
          topBar: {
            title: {
              text: 'Modal with stack'
            }
          }
        }
      }
    }]
  }
});
```

## dismissModal\(params = {}\) -&gt; dismissModal\(componentId\)

Dismiss the current modal.

```javascript
Navigation.dismissModal(this.props.componentId);
```

## dismissAllModals\(params = {}\) -&gt; dismissAllModals\(\)

Dismiss all the current modals at the same time.

```javascript
Navigation.dismissAllModals();
```

