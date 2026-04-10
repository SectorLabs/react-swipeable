# react-swipeable

Fork of [dogfessional/react-swipeable](https://github.com/dogfessional/react-swipeable). Swipe bindings for React.

## Changes from upstream

* Fix `preventDefault` timing to prevent unwanted scrolling during swipe on non-Chrome mobile browsers and iOS

## Install

```
npm install @sector-labs/react-swipeable
```

## Usage

```js
import Swipeable from '@sector-labs/react-swipeable'

class SwipeComponent extends React.Component {
  render() {
    return (
      <Swipeable
        onSwiping={(e, deltaX, deltaY) => console.log('Swiping...', deltaX, deltaY)}
        onSwiped={(e, deltaX, deltaY, isFlick) => console.log('Swiped', deltaX, deltaY)}
        onSwipedLeft={(e, absX) => console.log('Swiped left', absX)}>
        You can swipe here!
      </Swipeable>
    )
  }
}
```

## Props

### Event Props

| Prop | Signature |
|------|-----------|
| `onSwiping` | `(e, deltaX, deltaY, absX, absY, velocity)` |
| `onSwiped` | `(e, deltaX, deltaY, isFlick, velocity)` |
| `onSwipingUp/Right/Down/Left` | `(e, delta)` |
| `onSwipedUp/Right/Down/Left` | `(e, delta, isFlick)` |
| `onTap` | `(e)` |

### Config Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `flickThreshold` | `number` | `0.6` | Max velocity before considered a flick |
| `delta` | `number` | `10` | px threshold before firing events |
| `preventDefaultTouchmoveEvent` | `bool` | `false` | Prevent browser touchmove |
| `stopPropagation` | `bool` | `false` | Stop event propagation |
| `nodeName` | `string` | `'div'` | HTML element to render |
| `trackMouse` | `bool` | `false` | Track mouse swipes |
| `disabled` | `bool` | `false` | Disable swipe tracking |
| `innerRef` | `func` | — | Access inner DOM node ref |
| `rotationAngle` | `number` | `0` | Rotation angle for swipe direction |

## License

MIT
