# Static examples on top

This document describes the work needed to implement the “static examples on top” project.
The “static examples on top” project will add static examples to the tops of JavaScript and CSS reference pages.

“Static” here means that the user won’t be able to interact with them (as compared with an example on codepen.io, for example).

## CSS pages
For the CSS reference pages, there are 2 parts:
 * Add “syntax examples” to the tops of the pages
 * Add “example outcomes” to the tops of the pages
 
### Syntax examples for CSS

CSS syntax examples are syntax-highlighted PRE blocks that show the syntax of the item by example, like this:

    /* Content is not clipped */
    overflow-y: visible;

    /* Content is clipped, with no scrollbars */
    overflow-y: hidden;

    /* Content is clipped, with scrollbars */
    overflow-y: scroll;

    /* Let the browser decide */
    overflow-y: auto;


*Most* pages already have a section like this, so the only work is to move it to the top.

### Syntax outcomes for CSS
Syntax outcomes show the effect of different values for the item. For example:

<div id="div1" style="width:  200px;  height: 100px; border: 1px solid black; overflow-y: hidden; margin-bottom: 12px;">
<b><code>overflow-y:hidden</code></b></br></br>
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
</div>
<div id="div2" style="width:  200px;  height: 100px;border: 1px solid black; overflow-y: scroll; margin-bottom: 12px;">
<b><code>overflow-y:scroll</code></b></br></br>

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
</div>
<div id="div3" style="width:  200px;  height: 100px;border: 1px solid black; overflow-y: visible; margin-bottom: 50px;">
<b><code>overflow-y:visible</code></b></br></br>

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
</div>
<div id="div4" style="width:  200px;  height: 100px;border: 1px solid black; overflow-y: auto; margin-bottom: 12px;">
<b><code>overflow-y:auto</code></b></br></br>

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
</div>

Most pages have live samples or other examples that could be adapted to be effective "syntax outcomes", but rework would be needed and every case would be different.

### What work is needed?

There are 503 pages under [https://developer.mozilla.org/en-US/docs/Web/CSS/](https://developer.mozilla.org/en-US/docs/Web/CSS/) that might need updates.

This number is arrived at as the total number of pages under https://developer.mozilla.org/en-US/docs/Web/CSS/ that contain one of the following tags: `"Property"`, `"CSS Property"`, `"Selectors"`, `"CSS Pseudo-class"`, `"Pseudo-class"`,
 `"CSS Pseudo-element"`, `"Pseudo-element"`, `"CSS Function"`, `"At-rule"`,
 `"CSS Data Type"`, `"CSS Data Types"`, `"Type"`.
 
 This is an upper bound: there are probably pages in here that are obsolete and don't need to be updated.

#### Syntax examples

For syntax examples, we have already updated 215 pages.

This includes about 160 pages updated during the Write the Docs writing day. This took 12 people, in probably a little more than half a day. We could then estimate a rate of 20-40 pages per day, so 2-3 weeks of effort ought to be enough to finish this work.

Note though that this parallelizes very well indeed.

#### Syntax outcomes

For syntax outcomes we don't have a clear picture. For one thing, it's likely that syntax outcomes won't work well for many CSS items, but we don't yet have a picture of which ones these are.

For another thing, this isn't repetitive work: each outcome should be designed differently. I think for this we should do an experiment of processing, say, 50 items to add syntax outcomes (or not add them if it is not appropriate) and extrapolate from that.

## JavaScript pages

For the JavaScript reference pages, we need to add a simple code example. The outcome is generally shown as a comment in the example:

    var a = ['zero', 'one', 'two', 'three'];
    var sliced = a.slice(1, 3);

    console.log(a);      // ['zero', 'one', 'two', 'three']
    console.log(sliced); // ['one', 'two']

### What work is needed?

There are 658 pages under [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/).

Florian added examples for 35 pages that document [Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). He took 3-4 days for this, so he can produce them (in short bursts, anyway), at 10 per day.

It's unclear what factor we should add for the people doing the work not being Florian, but let's say 5 per day, including review time, for someone with solid JS skills. We should revise this as we go.

50/week would be about 13 weeks.

This work should also parallelize very well, though.

## Open questions

We're intending to go ahead with interactive examples, and they will replace static examples on all or most pages.

* Since CSS syntax examples are quick and cheap to move, they are still worth doing.

* Since JS examples would be easily reused for interactive examples, they are also still worth doing.

* Can we say the same about CSS syntax outcomes?

## What's next?

* Continue to work on CSS syntax examples, to finish them off.

* Get an estimate for time to add CSS example outcomes, by processing, say, 50 pages.

* Start adding JS examples.
