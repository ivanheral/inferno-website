# Event Handling

To create events with Inferno, you pass a relevant event name to the props of your VNode. For example, when using JSX:

```jsx
function clickMe(event) {
  console.log('Clicked !', event);
}
```

Then you render a VNode with this event passed as props:
```
Inferno.render(
  <div onClick={ clickMe } />, 
  document.getElementById('app')
);
```
Upon clicking the `<div>`, the `clickMe()` event will fire.

Like React, Inferno also uses a light-weight synthetic event system in certain places (although both event systems differ massively). 
Inferno's event system provides highly efficient delegation and an event helper called linkEvent.
 
One major difference between Inferno and React is that Inferno does not rename events or change how they work by default. Inferno only specifies that events should be camel cased, rather than lower case. Lower case events will bypass
Inferno's event system in favour of using the native event system supplied by the browser. For example, when detecting changes on an `<input>` element, in React you'd use `onChange`, with Inferno you'd use `onInput` instead (the
native DOM event is `oninput`).

This feature is a very recent addition to Inferno, so there are only a handful of events that use Inferno's event system:
- `onClick`
- `onDblClick`
- `onMouseMove`
- `onMouseDown`
- `onMouseUp`
- `onSubmit`
- `onKeyPress`
- `onKeyDown`
- `onKeyUp`
- `onInput`
- `onChange`

More events are expected to be supported in future versions.