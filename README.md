## aframe-vive-cursor-component

    Note: This component only works with A-Frame's master branch (soon to be released as 0.3.0).

This is an [A-Frame](https://aframe.io) component for adding a cursor to an HTC Vive controller.

![cursor-gif](http://i.imgur.com/QCgZWd7.gif)

### API

| Property |          Description          | Default Value |
|:--------:|:-----------------------------:|:-------------:|
|   color  |          Laser color          |    0x0000ff   |
|  radius  | Laser radius (top and bottom) |     0.001     |

### Usage

Simply attach the component to an entity alongside the vive-controls component.

```html
    <a-entity vive-controls="hand: right" vive-cursor></a-entity>
```

As it is based on [A-Frame's built-in cursor](https://aframe.io/docs/master/components/cursor.html), many of the events and states are shared.

Note that "mouseup" and "mousedown" have been mapped to the trigger. In other words, pulling the trigger is the same as clicking the right-mouse button.

### Notes

To avoid intersecting with the laser, the raycaster's "near" property is set to 0.03. As a result, you may see odd results when the top of the controller is held extremely close to the entity you wish to intersect.

Generally, this component assumes the Vive controller model. If you are using the hand model or a different model entirely, you may need to change the position of the laser.

#### Browser

Install and use by directly including the [browser files](dist):

```html
<head>
  <title>My A-Frame Scene</title>
  <script src="https://cdn.rawgit.com/aframevr/aframe/master/dist/aframe.min.js"></script>
  <script src="https://rawgit.com/aframe-vive-cursor-component/master/dist/aframe-vive-cursor-component.min.js"></script>
</head>

<body>
  <a-scene>
    <a-entity vive-controls="hand: left"></a-entity>
    <a-entity vive-controls="hand: right" vive-cursor></a-entity>
  </a-scene>
</body>
```

#### npm

Install via npm:

```bash
npm install aframe-vive-cursor-component
```

Then register and use.

```js
require('aframe');
require('aframe-vive-cursor-component');
```

