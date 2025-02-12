---
title: GlobalEventHandlers.ondrag
slug: Web/API/GlobalEventHandlers/ondrag
tags:
  - API
  - HTML DOM
  - Reference
  - drag and drop
browser-compat: api.GlobalEventHandlers.ondrag
---
{{ApiRef("HTML DOM")}}

A {{domxref("GlobalEventHandlers","global event handler")}} for the {{domxref("HTMLElement/drag_event", "drag")}}
event.

## Syntax

```js
var dragHandler = targetElement.ondrag;
```

### Return value

- `dragHandler`
  - : The _drag_ event handler for element `targetElement`.

## Example

This example includes the use of the _ondrag_ attribute handler to set an
element's _drag_ event handler.

```js
<!DOCTYPE html>
<html lang=en>
<title>Examples of using the ondrag Global Event Attribute</title>
<meta content="width=device-width">
<style>
  div {
    margin: 0em;
    padding: 2em;
  }
  #source {
    color: blue;
    border: 1px solid black;
  }
  #target {
    border: 1px solid black;
  }
</style>
</head>
<script>
function drag_handler(ev) {
 console.log("Drag");
}

function dragstart_handler(ev) {
 console.log("dragStart");
 ev.dataTransfer.setData("text", ev.target.id);
}

function drop_handler(ev) {
 console.log("Drop");
 ev.currentTarget.style.background = "lightyellow";

 ev.preventDefault();
 var data = ev.dataTransfer.getData("text");
 ev.target.appendChild(document.getElementById(data));
}

function dragover_handler(ev) {
 console.log("dragOver");
 ev.preventDefault();
}
</script>
<body>
<h1>Examples of <code>ondrag</code>, <code>ondrop</code>, <code>ondragstart</code>, <code>ondragover</code></h1>
 <div> <!-- <div class="source"> -->
   <p id="source" ondrag="drag_handler(event);" ondragstart="dragstart_handler(event);" draggable="true">
     Select this element, drag it to the Drop Zone and then release the selection to move the element.</p>
 </div>
 <div id="target" ondrop="drop_handler(event);" ondragover="dragover_handler(event);">Drop Zone</div>
</body>
</html>
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("Window")}}: {{domxref("Window/drag_event", "drag")}} event
- {{domxref("Document")}}: {{domxref("Document/drag_event", "drag")}} event
- {{domxref("HTMLElement")}}: {{domxref("HTMLElement/drag_event", "drag")}} event
- {{domxref("SVGElement")}}: {{domxref("SVGElement/drag_event", "drag")}} event
