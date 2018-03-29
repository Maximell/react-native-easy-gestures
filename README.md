# React Native Easy Gestures

React Native Gestures. Support: Drag, Scale and Rotate a Component.

![example](https://raw.githubusercontent.com/keske/react-native-easy-gestures/master/static/gestures.gif)

## Instalation

### RN > 0.46 👶

```
$ npm install --save react-native-easy-gestures
```

### RN < 0.46 👴

```
$ npm install --save react-native-easy-gestures@1.0.x
```

## Usage

```javascript
import Gestures from 'react-native-easy-gestures';

/* Simple example: */
<Gestures>
  <Image
    source={photo}
    style={{
      width: 200,
      height: 300,
    }}
  />
</Gestures>

/* Only drag example witn `onChange` event: */
<Gestures
  rotatable={false}
  scalable={false}
  onChange={(event, styles) => {
    console.log(styles);
  }}
>
  <Image
    source={photo}
    style={{
      width: 200,
      height: 300,
    }}
  />
</Gestures>

/**
 * Another example:
 * Drag only on x axis;
 * Scale from 0.1 to 7;
 * Do not rotate;
 * On release callback;
 */
<Gestures
  draggable={{
    y: false,
  }}
  scalable={{
    min: 0.1,
    max: 7,
  }}
  rotatable={false}
  onRelease={(event, styles) => {
    console.log(styles);
  }}
>
  <Image
    source={photo}
    style={{
      width,
      height,
    }}
  />
</Gestures>
```

## Props

### Behavior

```javascript
draggable?: boolean = true | object = { x?: boolean = true, y?: boolean = true }
```

```javascript
rotatable?: boolean = true
```

```javascript
scalable?: boolean = true | object = { min?: number = 0.33, max?: number = 2, scale?: number = 1 }
```

### Styles

```javascript
styles?: object // React Native styles
```

### Callbacks

```javascript
onStart?(event: object, styles: object): void
```

```javascript
onChange?(event: object, styles: object): void
```

```javascript
onRelease?(event: object, styles: object): void
```

# Development

```
$ git clone https://github.com/keske/react-native-easy-gestures.git
$ cd react-native-easy-gestures
$ npm install
$ react-native run-ios
```

# TODO

- [ ] Rotate step, ex: every 90deg
- [ ] Guidelines and center snap
