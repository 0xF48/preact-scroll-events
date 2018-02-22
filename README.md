# preact-scroll-events

<a href="https://npmjs.com/package/preact-scroll-events" alt="npm link"><img src="https://img.shields.io/npm/v/preact-scroll-events.svg?style=flat-square" /></a>


## MinMaxEvent
Adds onMaxReached and onMinReached events with a few extra variables to the nested component.

**`offsetMaxBeta`**  *`100`* when scroll reaches % of scrollable element from end [---->|..(100)%..] this event will fired once, until the scroll is less than the max, then it will be able to fire again. 

**`offsetMinBeta`**  *`100`* when scroll reaches % of scrollable element from start [..(100)%..|<----]

**`offsetMin`**  *`100`* when scroll reaches px of scrollable element from end [..(X)px..|<----]

**`offsetMax`**  *`100`* when scroll reaches px of scrollable element from start [---->|..(X)px..]

**`vert`**  *`true`* vertical of horizontal scroll?

**`onMaxReached`**  *`null`* Event fired when scroll reaches max bottom/right

**`onMinReached`**  *`null`* Event fired when scroll reaches min top/left



### jsx
```jsx
import {MinMaxEvent} from preact-scroll-events

//......

render: function(){
	<MinMaxEvent vert=true offsetMinBeta=0 offsetMaxBeta=100 onMaxReached=this.onMaxReachedCallback onMinReached=this.onMinReachedCallback>
		<div style={overflowY:"scroll"}>Im scrollable, when my scroll reaches 100% of my height from bottom, one onMaxReached event will be fired</div>
	</MinMaxEvent>
}
```


### coffeescript
```coffeescript
{MinMaxEvent} = require('preact-scroll-events')

#.......

render: ->
	h MinMaxEvent,
		vert: true
		offsetMinBeta: 0
		offsetMaxBeta: 100
		onMaxReached: @onMaxReachedCallback
		onMinReached: @onMinReachedCallback
		h 'div',
			style:
				overflowY: 'scroll'
			'Im scrollable, when my scroll reaches 100% of my height from bottom, I will dispatch one onMaxReached event.'
```