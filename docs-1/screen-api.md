# Screen API

This API is relevant when in a screen component context - it allows a screen to push other screens, pop screens, change its navigator style, etc. Access to this API is available through the `Navigation` module and expect to receive the current presented component id from screen `props.componentId`. Component must initialize in stack in order to push another component.

## push\(componentId, layout\)

Push a new screen into this screen's navigation stack.

```javascript
Navigation.push(this.props.componentId, {
  component: {
    name: 'example.PushedScreen',
    passProps: {
      text: 'Pushed screen'
    },
    options: {
      topBar: {
        title: {
          text: 'Pushed screen title'
        }
      }
    }
  }
});
```

## pop\(componentId, mergeOptions?\)

Pop the top screen from this screen's navigation stack.

```javascript
Navigation.pop(this.props.componentId);
```

## popToRoot\(componentId, mergeOptions?\)

Pop all the screens until the root from this screen's navigation stack.

```javascript
Navigation.popToRoot(this.props.componentId);
```

## popTo\(componentId, mergeOptions?\)

Pop the stack to a given component.

```javascript
Navigation.popTo(componentId);
```

## setStackRoot\(componentId, params\)

Reset the current navigation stack to a new screen component \(the stack root is changed, accepts multiple children\).

```javascript
Navigation.setStackRoot(this.props.componentId, [
    {
    component: {
          name: 'example.NewRootScreen',
          passProps: {
            text: 'Root screen'
          },
          options: {
            animations: {
              setStackRoot: {
                enabled: true
              }
            }
          }
        }
  }
]);
```

## showModal\(layout = {}\)

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
              text: 'Modal'
            }
          }
        }
      }
    }]
  }
});
```

## dismissModal\(componentId, mergeOptions?\)

Dismiss the current modal.

```javascript
Navigation.dismissModal(this.props.componentId);
```

## dismissAllModals\(mergeOptions?\)

Dismiss all the current modals at the same time.

```javascript
Navigation.dismissAllModals();
```

## mergeOptions\(componentId, options = {}\)

Set options dynamically for component.

WARNING! this is called after the component has been rendered at least once. If you want the options to apply as soon as the screen is created, use `static options(passProps){...}` or pass the options as part of the push/modal etc command.

```javascript
Navigation.mergeOptions(this.props.componentId, {
  topBar: {
    visible: true,
    title: {
      text: 'Title'
    }
  },
  bottomTabs: {

  },
  bottomTab: {

  },
  sideMenu: {

  },
  overlay: {

  }
});
```

