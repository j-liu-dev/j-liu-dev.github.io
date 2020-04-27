---
layout: blog_post
title: Living as a custom hook in the React world
category: blog
---

As confusing as the title is, the life cycle of my custom hooks confused me big time.  
If you've ever wondered why `useState` and other hooks/functions wouldn't behave as expected inside a custom hook, this article could shed a light on your confusion.

## the Prelude - hooks
We all remember that inspiring moment when React v16.8 introduced hooks and context API.  
Fascinated by hooks and the new potential of functional components, I immediately started adapting those in my React projects.  

The default hooks, namely `useState`, `useEffect`, `useLayoutEffect`, `useReducer` and `useCallback`, opened a new world to us developers and affected the way we use dependencies like `Redux`; in a good way.  
I literally couldn't complain until I faced the biggest confusion of my React-ish life.  

## enter Custom hooks
At one point in my hooks journey, I knew I was ready to ditch HOCs(High Order Components) and bring about the new level of DRY(Do not Repeat Yourself).  
But how? Using __custom hooks__!  

I enjoyed the initial success and was more than eager to hookerize each and every bit of my React codebase.

***
<video width="100%" autoplay loop>
  <source src="/video/animationhook.webm" type="video/mp4">
</video>
**hamburger menu animation hook in action, and the code below**
```javascript
import { useState, useEffect } from 'react';
import { Animated } from 'react-native';
import { Metrics } from '../Themes';

const useMenuAnimation = (isExpanded, fullSize = Metrics.mainMenuWidth) => {
  const [animation] = useState(new Animated.Value(0));

  useEffect(() => {
    if (isExpanded === undefined) {
      animation.setValue(0);
      return;
    }

    let initialValue;
    let finalValue;
    if (isExpanded) {
      initialValue = 0;
      finalValue = fullSize;
    } else {
      initialValue = fullSize;
      finalValue = 0;
    }

    animation.setValue(initialValue);
    Animated.spring(animation, {
      toValue: finalValue
    }).start();
  }, [isExpanded]);

  return [animation];
};

export default useMenuAnimation;

```
Custom hooks were quite intriguing, and I loved the applauds of the teammates who appreciated the smarter sharing of logic between the components.  

## the Challenge
Being the advocate of hooks, I voluntarily trained junior teammates on the concepts and usage of hooks and context API.  
When they asked about custom hooks, I wrote them a counter hook on the spot. I didn't doubt that it'd work.  
```javascript
import { useState } from 'react'

const useCounter = (initialValue, step) => {
  const [counter, setCounter] = useState(initialValue)

  const increase = () => {
    setCounter(counter + step)
  }

  const decrease = () => {
    setCounter(counter - step)
  }

  return {
    counter,
    increase,
    decrease,
  }
}

export default useCounter
```
Surprisingly enough, it didn't work!  
It took me as long as 3 hours to figure out why.  

## a Component equivalent
```jsx
import React, { useState } from 'react'

const Counter = ({
  initialValue,
  step,
}) => {
  const [counter, setCounter] = useState(initialValue)

  const increase = () => {
    setCounter(counter + step)
  }

  const decrease = () => {
    setCounter(counter - step)
  }

  return (
    <div className="counter">
      <button onClick={decrease}>-</button>
      <span className="value">{counter}</span>
      <button onClick={increase}>+</button>
    </div>
  )
}

export default Counter
```
We know this component works.

## the Discovery
After a long haul, I discovered that my assumption about custom hooks' life cycle was completely wrong.  

Components re-render themselves when a state value changes, meaning that `increase` and `decrease` are redefined whenever `counter` changes.  
However, they remained the same in the counter hook.  
Why? Custom hooks are just functions - the normal functions.  

```javascript
...
// a console output that signals function definition
console.log('`increase` function will be defined')

// a console output for every increase action
const increase = () => {
  console.log(counter)
  setCounter(counter + step)
}
...
```
The console output of the hook went on like __0, 0, 0, 0, ...__, whereas __0, 1, 2, 3, ...__ showed for the component.  
Then I understood that a custom hook was to be treated as a function, not a component.  
> There's no such thing as re-render for custom hooks

## Solutions
With the new finding in mind, I wrote 2 separate solutions for the counter hook.  

The first one was forcefully redefining `increase` and `decrease` functions whenever `counter` value changed, thus mimicking the component's behavior.
```javascript
...
const increase = useCallback(() => {
  setCounter(counter + step)
}, [counter])

const decrease = useCallback(() => {
  setCounter(counter - step)
}, [counter])
...
```
<small>(please note that I intentionally avoided `useCallback` in the component implementation for the presentation purpose)</small>

The second one was rather simple:
```javascript
...
const increase = () => {
  setCounter(counter => counter + step)
}
const decrease = () => {
  setCounter(counter => counter - step)
}
...
```
<small>(precaution: the above solution wouldn't work well in the scenarios where more than one state value are involved)</small>

## the conclusion
__A hook is just a function, and you are the one who defines its behavior and life cycle.__

The experience reminded me of the quote
> You will never learn if you don't make mistakes
