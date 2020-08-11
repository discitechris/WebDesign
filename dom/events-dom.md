# Events DOM

## Event Listeners & Event Object

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", function (e) {
  console.log("Hello World");
  // used to prevent default Actions for eg.
  // forms by default submit on clicks and refreshes the page
  e.preventDefault();
});
```

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", onClick);

function onClick(e) {
  console.log("Clicked");
  val = e;
}
```

### Event target Element

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", function (e) {
  val = e.target;
  val = e.target.id;
  val = e.className;
  val = e.target.classList;
  console.log(val);
});
```

### Event Type

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", function (e) {
  val = e.type;
  console.log(val);
});
```

### Timestamp

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", function (e) {
  val = e.timestamp;
  console.log(val);
});
```

### Co-ordinates relative to Window

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", function (e) {
  val = e.clientY;
  val = e.clientX;
  console.log(val);
});
```

### Co-ordinates relative to Element

```javascript
document.querySelector(".clear-tasks").addEventListeners("click", function (e) {
  val = e.offsetY;
  val = e.offsetX;
  console.log(val);
});
```

## MouseEvents

```javascript
const clearBtn = document.querySelector('.clear-tasks');
const card = document.querySelector('.card');
// Event handler
function runEvent(e){
    console.log(`Event Type: ${e.type}`);
}
```

### click

```javascript
clearBtn.addEventListener('click',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### DoubleClick

```javascript
clearBtn.addEventListener('dblclick',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mousedown

```javascript
clearBtn.addEventListener('mousedown',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mouseup

```javascript
clearBtn.addEventListener('mouseup',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mouseenter

MouseEnter and MouseLeave will fire off on the main element only

```javascript
card.addEventListener('mouseenter',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mouseleave

MouseEnter and MouseLeave will fire off on the main element only

```javascript
card.addEventListener('mouseleave',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mouseover

Mouseover and Mouseout will fire off on the main element and moving from inside child elements also will fire off.

```javascript
card.addEventListener('mouseover',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mouseout

Mouseover and Mouseout will fire off on the main element and moving from inside child elements also will fire off.

```javascript
card.addEventListener('mouseout',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

### Mousemove

Mousemovements anywhere in the document

```javascript
card.addEventListener('mousemove',function(e){
    console.log(`Event Type: ${e.type}`);
});
```

## InputEvents

```javascript
const form = document.querySelector('form');
const taskInput = document.getElementById('task');
//clear input
taskInput.value = '';
form.addEventListener('submit',runEvent);
function runEvent(e){
    console.log(`EventType: ${e.type}`);
    console.log(taskInput.value);
    e.preventDefault();
}
```

| Event Name | Fired When |
| :--- | :--- |
| \`\`[`change`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/change_event)\`\` | The event occurs when the content of a form element, the selection, or the checked state have changed \(for `<input>`, `<select>`, and `<textarea>`\) |
| \`\`[`input`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/input_event)\`\` | The event occurs when an element gets user input |
| \`\`[`select`](https://developer.mozilla.org/en-US/docs/Web/API/Element/select_event)\`\` | The event occurs after the user selects some text \(for `<input>` and `<textarea>`\) |
| \`\`[`storage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/storage_event)\`\` | The event occurs when a Web Storage area is updated |
| \`\`[`toggle`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/toggle)\`\` | The event occurs when the user opens or closes the `<details>` element |

## Resource Events <a id="resource-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`error`](https://developer.mozilla.org/en-US/docs/Web/Events/error)​ | A resource failed to load. |
| ​[`abort`](https://developer.mozilla.org/en-US/docs/Web/Events/abort)​ | The loading of a resource has been aborted. |
| ​[`load`](https://developer.mozilla.org/en-US/docs/Web/Events/load)​ | A resource and its dependent resources have finished loading. |
| ​[`beforeunload`](https://developer.mozilla.org/en-US/docs/Web/Events/beforeunload)​ | The window, the document and its resources are about to be unloaded. |
| ​[`unload`](https://developer.mozilla.org/en-US/docs/Web/Events/unload)​ | The document or a dependent resource is being unloaded. |

‌

## Focus Events <a id="focus-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`focus`](https://developer.mozilla.org/en-US/docs/Web/Events/focus)​ | An element has received focus \(does not bubble\). |
| ​[`blur`](https://developer.mozilla.org/en-US/docs/Web/Events/blur)​ | An element has lost focus \(does not bubble\). |
| ​[`focusin`](https://developer.mozilla.org/en-US/docs/Web/Events/focusin)​ | An element is about to receive focus \(does bubble\). |
| ​[`focusout`](https://developer.mozilla.org/en-US/docs/Web/Events/focusout)​ | An element is about to lose focus \(does bubble\). |

‌

## Session History Events <a id="session-history-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`pagehide`](https://developer.mozilla.org/en-US/docs/Web/Events/pagehide)​ | A session history entry is being traversed from. |
| ​[`pageshow`](https://developer.mozilla.org/en-US/docs/Web/Events/pageshow)​ | A session history entry is being traversed to. |
| ​[`popstate`](https://developer.mozilla.org/en-US/docs/Web/Events/popstate)​ | A session history entry is being navigated to \(in certain cases\). |

‌

## Form Events <a id="form-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`reset`](https://developer.mozilla.org/en-US/docs/Web/Events/reset)​ | The reset button is pressed |
| ​[`submit`](https://developer.mozilla.org/en-US/docs/Web/Events/submit)​ | The submit button is pressed |

‌

## Printing Events <a id="printing-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`beforeprint`](https://developer.mozilla.org/en-US/docs/Web/Events/beforeprint)​ | The print dialog is opened |
| ​[`afterprint`](https://developer.mozilla.org/en-US/docs/Web/Events/afterprint)​ | The print dialog is closed |

‌

## View Events <a id="view-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`fullscreenchange`](https://developer.mozilla.org/en-US/docs/Web/Events/fullscreenchange)​ | An element was toggled to or from fullscreen mode. |
| ​[`fullscreenerror`](https://developer.mozilla.org/en-US/docs/Web/Events/fullscreenerror)​ | It was impossible to switch to fullscreen mode for technical reasons or because the permission was denied. |
| ​[`resize`](https://developer.mozilla.org/en-US/docs/Web/Events/resize)​ | The document view has been resized. |
| ​[`scroll`](https://developer.mozilla.org/en-US/docs/Web/Events/scroll)​ | The document view or an element has been scrolled. |

‌

## Clipboard Events <a id="clipboard-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`cut`](https://developer.mozilla.org/en-US/docs/Web/Events/cut)​ | The selection has been cut and copied to the clipboard |
| ​[`copy`](https://developer.mozilla.org/en-US/docs/Web/Events/copy)​ | The selection has been copied to the clipboard |
| ​[`paste`](https://developer.mozilla.org/en-US/docs/Web/Events/paste)​ | The item from the clipboard has been pasted |

‌

## Keyboard Events <a id="keyboard-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`keydown`](https://developer.mozilla.org/en-US/docs/Web/Events/keydown)​ | ANY key is pressed |
| ​[`keypress`](https://developer.mozilla.org/en-US/docs/Web/Events/keypress)​ | ANY key \(except Shift, Fn, or CapsLock\) is in pressed position. \(Fired continously.\) |
| ​[`keyup`](https://developer.mozilla.org/en-US/docs/Web/Events/keyup)​ | ANY key is released |

‌

## Mouse Events <a id="mouse-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`auxclick`](https://developer.mozilla.org/en-US/docs/Web/Events/auxclick)​ | A pointing device button \(ANY non-primary button\) has been pressed and released on an element. |
| ​[`click`](https://developer.mozilla.org/en-US/docs/Web/Events/click)​ | A pointing device button \(ANY button; soon to be primary button only\) has been pressed and released on an element. |
| ​[`contextmenu`](https://developer.mozilla.org/en-US/docs/Web/Events/contextmenu)​ | The right button of the mouse is clicked \(before the context menu is displayed\). |
| ​[`dblclick`](https://developer.mozilla.org/en-US/docs/Web/Events/dblclick)​ | A pointing device button is clicked twice on an element. |
| ​[`mousedown`](https://developer.mozilla.org/en-US/docs/Web/Events/mousedown)​ | A pointing device button is pressed on an element. |
| ​[`mouseenter`](https://developer.mozilla.org/en-US/docs/Web/Events/mouseenter)​ | A pointing device is moved onto the element that has the listener attached. |
| ​[`mouseleave`](https://developer.mozilla.org/en-US/docs/Web/Events/mouseleave)​ | A pointing device is moved off the element that has the listener attached. |
| ​[`mousemove`](https://developer.mozilla.org/en-US/docs/Web/Events/mousemove)​ | A pointing device is moved over an element. \(Fired continously as the mouse moves.\) |
| ​[`mouseover`](https://developer.mozilla.org/en-US/docs/Web/Events/mouseover)​ | A pointing device is moved onto the element that has the listener attached or onto one of its children. |
| ​[`mouseout`](https://developer.mozilla.org/en-US/docs/Web/Events/mouseout)​ | A pointing device is moved off the element that has the listener attached or off one of its children. |
| ​[`mouseup`](https://developer.mozilla.org/en-US/docs/Web/Events/mouseup)​ | A pointing device button is released over an element. |
| ​[`pointerlockchange`](https://developer.mozilla.org/en-US/docs/Web/Events/pointerlockchange)​ | The pointer was locked or released. |
| ​[`pointerlockerror`](https://developer.mozilla.org/en-US/docs/Web/Events/pointerlockerror)​ | It was impossible to lock the pointer for technical reasons or because the permission was denied. |
| ​[`select`](https://developer.mozilla.org/en-US/docs/Web/Events/select)​ | Some text is being selected. |
| ​[`wheel`](https://developer.mozilla.org/en-US/docs/Web/Events/wheel)​ | A wheel button of a pointing device is rotated in any direction. |

‌

## Drag & Drop Events <a id="drag-and-drop-events"></a>

| Event Name | Fired When |
| :--- | :--- |
| ​[`drag`](https://developer.mozilla.org/en-US/docs/Web/Events/drag)​ | An element or text selection is being dragged. \(Fired continuously every 350ms\) |
| ​[`dragend`](https://developer.mozilla.org/en-US/docs/Web/Events/dragend)​ | A drag operation is being ended \(by releasing a mouse button or hitting the escape key\). |
| ​[`dragenter`](https://developer.mozilla.org/en-US/docs/Web/Events/dragenter)​ | A dragged element or text selection enters a valid drop target. |
| ​[`dragstart`](https://developer.mozilla.org/en-US/docs/Web/Events/dragstart)​ | The user starts dragging an element or text selection. |
| ​[`dragleave`](https://developer.mozilla.org/en-US/docs/Web/Events/dragleave)​ | A dragged element or text selection leaves a valid drop target. |
| ​[`dragover`](https://developer.mozilla.org/en-US/docs/Web/Events/dragover)​ | An element or text selection is being dragged over a valid drop target. \(Fired continuously every 350ms\) |
| ​[`drop`](https://developer.mozilla.org/en-US/docs/Web/Events/drop)​ | An element is dropped on a valid drop target. |

‌

## Media Events <a id="media-events"></a>

| ​ | ​ |
| :--- | :--- |
| Event Name | Fired When |
| ​[`audioprocess`](https://developer.mozilla.org/en-US/docs/Web/Events/audioprocess)​ | The input buffer of a [`ScriptProcessorNode`](https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode) is ready to be processed. |
| ​[`canplay`](https://developer.mozilla.org/en-US/docs/Web/Events/canplay)​ | The browser can play the media, but estimates that not enough data has been loaded to play the media up to its end without having to stop for further buffering of content. |
| ​[`canplaythrough`](https://developer.mozilla.org/en-US/docs/Web/Events/canplaythrough)​ | The browser estimates it can play the media up to its end without stopping for content buffering. |
| ​[`complete`](https://developer.mozilla.org/en-US/docs/Web/Events/complete)​ | The rendering of an [`OfflineAudioContext`](https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext) is terminated. |
| ​[`durationchange`](https://developer.mozilla.org/en-US/docs/Web/Events/durationchange)​ | The `duration` attribute has been updated. |
| ​[`emptied`](https://developer.mozilla.org/en-US/docs/Web/Events/emptied)​ | The media has become empty; for example, this event is sent if the media has already been loaded \(or partially loaded\), and the [`load()`](https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/NsIDOMHTMLMediaElement) method is called to reload it. |
| ​[`ended`](https://developer.mozilla.org/en-US/docs/Web/Events/ended)​ | Playback has stopped because the end of the media was reached. |
| ​[`loadeddata`](https://developer.mozilla.org/en-US/docs/Web/Events/loadeddata)​ | The first frame of the media has finished loading. |
| ​[`loadedmetadata`](https://developer.mozilla.org/en-US/docs/Web/Events/loadedmetadata)​ | The metadata has been loaded. |
| ​[`pause`](https://developer.mozilla.org/en-US/docs/Web/Events/pause)​ | Playback has been paused. |
| ​[`play`](https://developer.mozilla.org/en-US/docs/Web/Events/play)​ | Playback has begun. |
| ​[`playing`](https://developer.mozilla.org/en-US/docs/Web/Events/playing)​ | Playback is ready to start after having been paused or delayed due to lack of data. |
| ​[`ratechange`](https://developer.mozilla.org/en-US/docs/Web/Events/ratechange)​ | The playback rate has changed. |
| ​[`seeked`](https://developer.mozilla.org/en-US/docs/Web/Events/seeked)​ | A _seek_ operation completed. |
| ​[`seeking`](https://developer.mozilla.org/en-US/docs/Web/Events/seeking)​ | A _seek_ operation began. |
| ​[`stalled`](https://developer.mozilla.org/en-US/docs/Web/Events/stalled)​ | The user agent is trying to fetch media data, but data is unexpectedly not forthcoming. |
| ​[`suspend`](https://developer.mozilla.org/en-US/docs/Web/Events/suspend)​ | Media data loading has been suspended. |
| ​[`timeupdate`](https://developer.mozilla.org/en-US/docs/Web/Events/timeupdate)​ | The time indicated by the `currentTime` attribute has been updated. |
| ​[`volumechange`](https://developer.mozilla.org/en-US/docs/Web/Events/volumechange)​ | The volume has changed. |
| ​[`waiting`](https://developer.mozilla.org/en-US/docs/Web/Events/waiting)​ | Playback has stopped because of a temporary lack of data. |



