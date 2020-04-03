# options-migration

## Common Options

### navBarTextColor

Title text color

```javascript
topBar: {
  title: {
    color: 'red'
  }
}
```

### navBarTextFontSize

Title font size

```javascript
topBar: {
  title: {
    fontSize: 18
  }
}
```

### navBarTextFontFamily

Title font

```javascript
topBar: {
  title: {
    fontFamily: 'Helvetica'
  }
}
```

### navBarBackgroundColor

TopBar background color

```javascript
topBar: {
  background: {
    color: 'red'
  }
}
```

### navBarCustomView

Use a react view as the TopBar's background or use a React view instead of the textual title.

```javascript
topBar: {
  background: {
    component: {
      name: 'example.CustomTopBarBackground'
    }
  },
  title: {
    component: {
      name: 'example.CustomTopBarTitle'
    }
  }
}
```

### navBarClipToBounds

Restrict the navbar background color to the navbar, and do not flow behind the status bar.

```javascript
topBar: {
  background: {
    component: {
      name: 'example.CustomTopBarBackground',
      clipToBounds: true
    }
  },
}
```

### navBarComponentAlignment

Align the React view used as the title

```javascript
topBar: {
  title: {
    component: {
      name: 'example.CustomTopBarTitle',
      alignment: 'center' | 'fill'
    }
  }
}
```

### navBarCustomViewInitialProps

Initial props passed to the React component

```javascript
topBar: {
  background: {
    component: {
      name: 'example.CustomTopBarBackground',
      passProps: {}
    }
  },
  title: {
    component: {
      name: 'example.CustomTopBarTitle',
      passProps: {}
    }
  }
}
```

### navBarButtonColor

TopBar button color

```javascript
topBar: {
  rightButtons: [
    {
      color: 'red'
    }
  ],
  leftButtons: [
    {
      color: 'red'
    }
  ],
  backButton: {
    color: 'red'
  }
}
```

### navBarHidden

TopBar visibility. When setting `visible: false`, you probably want to set `drawBehind: true` as well. Use `animate: false` to toggle visibility without animation.

```javascript
topBar: {
  visible: false
}
```

### navBarTransparent

Transparent TopBar. Set `drawBehind: true` to draw the screen behind the transparent TopBar.

```javascript
topBar: {
  background: {
    color: 'transparent'
  }
}
```

### drawUnderNavBar

Draw the screen behind the TopBar, Useful when the TopBar is toggled or transparent

```javascript
topBar: {
  drawBehind: true
}
```

### drawUnderTabBar

Draw the screen behind the BottomTabs, Useful when toggling BottomTabs or when the BottomTabs are translucent.

```javascript
bottomTabs: {
  drawBehind: true
}
```

### tabBarHidden

BottomTabs visibility.

```javascript
bottomTabs: {
  visible: false
}
```

The BottomTab's visibility can be toggled only on **Android** using `mergeOptions`:

```javascript
Navigation.mergeOptions(this.props.componentId, {
  bottomTabs: {
    visible: false
  }
});
```

On **iOS**, BottomTab visibility can be changed only when pushing screens. This means that if you'd like to hide BottomTabs when pushing a screen, You'll need to set the property to `false` in the options passed to the `push` command or via the `static options(passProps) {}` api.

### statusBarHidden

StatusBar visibility. For android, also set `drawBehind: true`.

```javascript
statusBar: {
  visible: false
}
```

### statusBarTextColorScheme

Theme of text and icons displayed in the StatusBar

```javascript
statusBar: {
  style: 'light' | 'dark'
}
```

### navBarSubtitleColor

Subtitle color

```javascript
topBar: {
  subtitle: {
    color: 'red'
  }
}
```

### navBarSubtitleFontFamily

Subtitle font

```javascript
topBar: {
  subtitle: {
    fontFamily: 'Helvetica'
  }
}
```

### navBarSubtitleFontSize

Subtitle font size

```javascript
topBar: {
  subtitle: {
    fontSize: 14
  }
}
```

### screenBackgroundColor

Screen color, visible before the actual React view is rendered

```javascript
layout: {
  backgroundColor: 'red'
}
```

### orientation

```javascript
layout: {
  orientation: ['portrait', 'landscape'] // An array of supported orientations
}
```

### disabledButtonColor

Button color when `enabled: false` is used

```javascript
topBar: {
  rightButtons: [
    {
      disabledColor: 'grey'
    }
  ]
}
```

### navBarButtonFontSize

Button font size

```javascript
topBar: {
  rightButtons: [
    {
      fontSize: 13
    }
  ],
  leftButtons: [
    {
      fontSize: 13
    }
  ]
}
```

### navBarLeftButtonFontSize

Left button font size

```javascript
{
  topBar: {
    leftButtons: [
      {
        fontSize: 13
      }
    ]
  }
}
```

### navBarLeftButtonColor

Left button color

```javascript
{
  topBar: {
    leftButtons: [
      {
        color: 'red'
      }
    ]
  }
}
```

### navBarLeftButtonFontWeight

Left button font weight

```javascript
{
  topBar: {
    leftButtons: [
      {
        weight: '300'
      }
    ]
  }
}
```

### navBarRightButtonFontSize

Right button font size

```javascript
topBar: {
  leftButtons: [
    {
      fontSize: 13
    }
  ]
}
```

### navBarRightButtonColor

Right button color

```javascript
topBar: {
  rightButtons: [
    {
      color: 'red'
    }
  ]
}
```

### navBarRightButtonFontWeight

Right button font weight

```javascript
topBar: {
  rightButtons: [
    {
      weight: '400'
    }
  ]
}
```

### modalPresentationStyle

Controls the behavior of screens displayed modally.

#### Options supported on iOS

* overCurrentContext - Content is displayed over the previous screen. Useful for **transparent modals**
* `formSheet` - Content is centered in the screen
* `pageSheet` -Content partially covers the underlying content
* `overFullScreen` - Content covers the screen, without detaching previous content.
* `fullScreen` - Content covers the screen, previous content is detached.

#### Options supported on Android

* `overCurrentContext` - Content is displayed over the previous screen. Useful for **transparent modals**
* `none` - Previous content is detached when the Modal's show animation ends

```javascript
{
  modalPresentationStyle: 'overCurrentContext'
}
```

### navBarButtonFontFamily

Button font family

```javascript
topBar: {
  rightButtons: [
    {
      fontFamily: 'Helvetica'
    }
  ]
}
```

## iOS only

### navBarHideOnScroll

Hide TopBar when list is scrolled

```javascript
topBar: {
  hideOnScroll: true
}
```

### navBarTranslucent

Translucent TopBar, Setting `drawBehind: true` is required for this property to work as expected.

```javascript
topBar: {
  drawBehind: true,
  background: {
    translucent: true
  }
}
```

### navBarNoBorder

Remove TopBar border \(hair line\)

```javascript
topBar: {
  noBorder: true
}
```

### navBarBlur

Blur the area behind the TopBar, Setting `drawBehind: true` and topBar background `transparent: true` is required for this property to work as expected.

```javascript
topBar: {
  drawBehind: true,
  background: {
    blur: true,
    transparent: true
  }
}
```

### rootBackgroundImageName

* iOS: name of image in Images.xcassets
* Android: name of drawable

```javascript
{
  rootBackgroundImage: require('rootBackground.png')
}
```

### screenBackgroundImageName

name of image in Images.xcassets

```javascript
{
  backgroundImage: require('background.png')
}
```

### statusBarHideWithNavBar

Hide the StatusBar if the TopBar is also hidden

```javascript
statusBar: {
  hideWithTopBar: true
}
```

### statusBarBlur

Blur the area behind the StatusBar

```javascript
statusBar: {
  blur: true
}
```

### disabledBackGesture

Disable the back \(swipe\) gesture used to pop screens

```javascript
{
  popGesture: false
}
```

### largeTitle

Use iOS 11 large title

```javascript
  topBar: {
    largeTitle: {
      visible: true,
      fontSize: 30,
      color: 'red',
      fontFamily: 'Helvetica'
    }
  }
```

## Android Options

### topBarElevationShadowEnabled

TopBar elevation in dp. Set this value to `0` to disable the TopBar's shadow.

```javascript
topBar: {
  elevation: 0
}
```

### navBarTitleTextCentered

Title alignment

```javascript
topBar: {
  title: {
    alignment: 'center'|'fill'
  }
}
```

### statusBarColor

StatusBar color

```javascript
statusBar: {
  backgroundColor: 'red'
}
```

### drawUnderStatusBar

Draw content behind the StatusBar

```javascript
statusBar: {
  drawBehind: true
}
```

### navBarHeight

TopBar height in dp

```javascript
topBar: {
  height: 70
}
```

### navBarTopPadding

Content top margin

```javascript
layout: {
    topMargin: 26
  }
```

### topTabsHeight

TopTabs height

```javascript
topTabs: {
  height: 70
}
```

### topBarBorderColor

TopBar border color

```javascript
topBar: {
  borderColor: 'red'
}
```

### topBarBorderWidth

TopBar border height

```javascript
topBar: {
  borderHeight: 1.3
}
```

## Unsupported options

* disabledSimultaneousGesture
* statusBarTextColorSchemeSingleScreen
* navBarButtonFontWeight
* topBarShadowColor
* topBarShadowOpacity
* topBarShadowOffset
* topBarShadowRadius
* preferredContentSize
* navigationBarColor
* navBarSubTitleTextCentered
* collapsingToolBarImage
* collapsingToolBarCollapsedColor
* navBarTextFontBold

