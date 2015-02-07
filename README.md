threex.loop
=============

threex.loop is a 
[threex game extension for three.js](http://www.threejsgames.com/extensions/).
It provides loops for your game. 
You can easily add your own functions in/from the loop.
You can create different kind of loops: Rendering loop which are updated with [requestAnimationFrame](https://developer.mozilla.org/en/docs/Web/API/window.requestAnimationFrame), Physics loop which are regurlarly updated based on [setTimeout](https://developer.mozilla.org/en/docs/Web/API/window.setTimeout) with a rate you choose and the plain loop is up to you to update manually.


Show Don't Tell
===============
* [examples/basic.html](http://jeromeetienne.github.io/threex.loop/examples/basic.html)
\[[view source](https://github.com/jeromeetienne/threex.loop/blob/master/examples/basic.html)\] :
It shows this feature, and that one which is coded like that.

A Screenshot
============
[![screenshot](https://raw.githubusercontent.com/jeromeetienne/threex.loop/master/examples/images/screenshot-threex-loop-512x512.jpg)](http://jeromeetienne.github.io/threex.loop/examples/basic.html)

How To Install It
=================

You can install it via script tag

```html
<script src='threex.loop.js'></script>
```

Or you can install with [bower](http://bower.io/), as you wish.

```bash
bower install threex.loop
```

How To Use Basic Loop ?
=======================

You create the basic loop like this

```
var loop    = new THREEx.Loop()
```

Then you add functions to this loop. Then those functions will then be updated in the same order you added them.

```
function function1(delta){
    console.log('function1')
})
loop.add(function1)
```

If you need to remove the function from the loop, ```loop.remove(function1)```.Then you update the loop with a delay in second. It will call all the functions added to the loop.

```
loop.update(60/1000)
```

How To Use A Rendering Loop ?
=============================

First you create the loop

```
var loop    = new THREEx.RenderingLoop()
```

Here you can add/remove functions to the loop the same way you did it for the basic loop. Those functions will be updated based on [requestAnimationFrame](https://developer.mozilla.org/en/docs/Web/API/window.requestAnimationFrame). So it depends on your [FPS](http://en.wikipedia.org/wiki/Frame_rate) or if the [page is visible](http://www.w3.org/TR/page-visibility/) by the user.

```
loop.start()
```

It is that simple. Then you can stop it with ```loop.stop()``` or test if it is running with ```loop.isRunning()```. 

How To Use A Physics Loop ?
===========================

First you create the loop. It will regurlarly updated based on [setTimeout](https://developer.mozilla.org/en/docs/Web/API/window.setTimeout) with a rate you choose. Let's update our loop 10 time per second

```
var loop    = new THREEx.PhysicsLoop(10)
```


Here you can add/remove functions to the loop the same way you did it for the basic loop. You can change the update rate by changing ```loop.rate   = 15```

```
loop.start()
```

It is that simple. Then you can stop it with ```loop.stop()``` or test if it is running with ```loop.isRunning()```. 
