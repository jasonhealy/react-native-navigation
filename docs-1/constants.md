# Constants

!&gt; Note! iOS resolves the values from the currently displayed root. If the current root doesn't contain BottomTabs - it will return 0 as the BottomTabs height while Android will always return a static value.

## statusBarHeight

```javascript
const constants = await Navigation.constants();
const statusBarHeight = constants.statusBarHeight;
```

## topBarHeight

```javascript
const constants = await Navigation.constants();
const topBarHeight = constants.topBarHeight;
```

## bottomTabsHeight

```javascript
const constants = await Navigation.constants();
const bottomTabsHeight = constants.bottomTabsHeight;
```

