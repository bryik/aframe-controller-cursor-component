## aframe-controller-cursor-component

[A-Frame](https://aframe.io) component for adding a laser-style cursor to a
tracked controls (e.g., HTC Vive, Oculus Touch).

<p align="center">
  <img src="http://i.imgur.com/QCgZWd7.gif"/>
</p>

### API

| Property | Description                    | Default Value |
|----------|--------------------------------|---------------|
| color    | Laser color.                   | #74BEC1       |
| radius   | Laser radius (top and bottom). | 0.001         |

### Usage

Attach the component to an entity alongside a tracked controls entity.

```html
<a-entity hand-controls="right" controller-cursor></a-entity>
```

The controller cursor component is based on A-Frame's [built-in
cursor](https://aframe.io/docs/master/components/cursor.html), many of the
events and states are shared.

`mouseup` and `mousedown` are mapped to the trigger. Pulling the trigger will
emit the same events as clicking.

### Notes

To avoid intersecting with the laser, the raycaster's `near` property is set to
0.03. Thus, you may see odd results when the top of the controller is held
extremely close to the entity you wish to intersect.

This component was built for the Vive controller model. If you are using a
different model, you may need to modify the raycaster and position of the
laser. In the future, this should be made more easily configurable.

#### Browser

Install and use by directly including the [browser files](dist):

```html
<head>
  <title>My A-Frame Scene</title>
  <script src="https://aframe.io/releases/0.5.0/aframe.min.js"></script>
  <script src="https://unpkg.com/aframe-controller-cursor-component/dist/aframe-controller-component.min.js"></script>
</head>

<body>
  <a-scene>
    <a-entity vive-controls="hand: left"></a-entity>
    <a-entity vive-controls="hand: right" controller-cursor></a-entity>
  </a-scene>
</body>
```

#### npm

Install via npm:

```bash
npm install aframe-controller-cursor-component
```

Then register and use.

```js
require('aframe');
require('aframe-controller-cursor-component');
```
