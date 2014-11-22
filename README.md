# &lt;left-swipe-action&gt;

## Polymer Web Component &lt;left-swipe-action&gt;

&lt;left-swipe-action&gt; is built with [Polymer](http://www.polymer-project.org/) to enables a left swipe gesture to open a content and show behind action buttons like iOS item list.

This component wraps your own element and the wrapper handles gesture events. The main content will be opened by a left swipe and specified buttons &lt;left-swipe-action-button&gt; will be shown behind of the content. The other gestures on the component will close the content.

```html
<left-swipe-action>
    <div>
        <!-- 
          Your content to be swiped here
        -->
    </div>
    <left-swipe-action-button>
      <!-- 
        Your action here
      -->
    </left-swipe-action-button>
</left-swipe-action>
```

Screen example 1  
![screen1](http://www.tejitak.com/blog/wp-content/uploads/2014/08/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2014-08-07-12.10.16.png)


Screen example 2  
![screen2](http://www.tejitak.com/blog/wp-content/uploads/2014/08/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88-2014-08-07-12.04.19.png)


The elements other than left-swipe-action-button will be inserted to shadow DOM as main content.
'left-swipe-action-button' is a button to be fit with a content height. These are aligned as table cells.

CSS for both the main content and buttons in light DOM will be just applied.

## Demo
[http://tejitak.github.io/left-swipe-action/demo.html](http://tejitak.github.io/left-swipe-action/demo.html)

## Usage

### Simple example
```html
<left-swipe-action shadow>
    <div style="padding: 18px;">
        <div>My first Polymer project</div>
        <div><strong>Swipe me to left</strong></div>
    </div>
    <left-swipe-action-button style="background-color: #E81D62;" onclick="alert('delete')">Delete</left-swipe-action-button>
</left-swipe-action>
```

### Multi actions example with paper elements
```html
<left-swipe-action shadow>
    <div  style="padding: 18px;">
        <p>See how many actions are behind<br><strong>Swipe me to left</strong></p>
    </div>
    <left-swipe-action-button onclick="alert('delete')"><paper-fab icon="delete"></paper-fab></left-swipe-action-button>
    <left-swipe-action-button onclick="alert('star')"><paper-fab icon="star"></paper-fab></left-swipe-action-button>
</left-swipe-action>
```

This can be worked with Polymer &lt;template repeat&gt; or other MVC library ([Angular.js](https://angularjs.org/), [Vue.js](http://vuejs.org/) etc.) like the following.

#### Template repeat example

```html
<template repeat="{{[1,2,3,4,5]}}">
  <left-swipe-action shadow offset="40">
      <div class="list-container">
          <div class="list-thumb"><a href="https://twitter.com/tejitak" target="_blank"><paper-icon-button icon="social:person"></paper-icon-button></a></div>
          <div class="list-content">
              <div class="list-message">Tejitak</div>
              <div class="list-info">Repeated by &lt;template repeat&gt; ...</div>
          </div>
      </div>
      <left-swipe-action-button onclick="alert('delete')"><paper-fab icon="delete"></paper-fab></left-swipe-action-button>
      <left-swipe-action-button onclick="alert('star')"><paper-fab icon="star"></paper-fab></left-swipe-action-button>
      <left-swipe-action-button onclick="alert('schedule')"><paper-fab icon="schedule"></paper-fab></left-swipe-action-button>
  </left-swipe-action>
</template>
```

### Attributes
<table>
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<th>open</th>
<td>boolean</td>
<td>false</td>
<td>If true, the content will be opened by default</td>
</tr>
<tr>
<th>nodrag</th>
<td>boolean</td>
<td>false</td>
<td>If true, drag (touch move) action is disabled and a content is automatically opened by click/touch</td>
</tr>
<tr>
<th>offset</th>
<td>number</td>
<td>60</td>
<td>Offset pixcel position for opened state</td>
</tr>
<tr>
<th>shadow</th>
<td>boolean</td>
<td>false</td>
<td>If true, box shadow is added</td>
</tr>
</tbody>
</table>


## Getting Started

1. Install with bower  
`bower install left-swipe-action --save`

2. Load the web component and the dependencies

```html
<script src="bower_components/webcomponentsjs/webcomponents.js"></script>
<link rel="import" href="bower_components/polymer/polymer.html">
<link rel="import" href="bower_components/left-swipe-action/left-swipe-action.html">
```

3. Markup with &lt;left-swipe-action&gt;

4. Done

### Supported Browsers

[Same as Polymer](http://www.polymer-project.org/resources/compatibility.html)
