---
title: Tailwind is the Worst of All Worlds
description: Apparently this horse hasn't been beaten enough.
date: 2025-07-21
tags: React,CSS,Tailwind,HTML
---
{% raw %}
Tailwind is the worst of all worlds. It is a regrettable step backwards that takes everything bad about CSS and modern web development and brings it all together in one library. To understand why, lets go back a bit.

## History

The history of web development is full of regrettable twists and turns. JavaScript was famously built in 10 days. For around 15 years none of the browsers could agree on how basic functionality should be implemented. The way the internet decisively coalesced on a series of technologies (HTML, JavaScript, and CSS), that everyone hated is a stick in the craw of many developers to this very day.

To some extent that reputation is earned. But to a larger extent that reputation has been invalidated through a slow but sure march of standardization and modernization that has led to the browser to be the best way to develop many types of applications. Far from it's origins, JavaScript is actually a solid little scripting language when you ignore the bad parts. Modern CSS is powerful but easy to get started with. HTML, wielded correctly, is a great language for building UI with accessibility in mind.

People still complain, but I've yet to see someone put forward a decent argument that any of the other platforms of modern UI development, Android, IOS, Windows, etc, actually offer a holistically better development experience. For the most part, developers have come around on web dev. We no longer hate JavaScript because 20 years ago you could redefine `undefined`, we now appreciate that first class functions were built in from the start.

## CSS

Of all the web technologies that underlie the modern web, the one that has received the fewest fundamental changes is CSS. We've gotten amazing things like flexbox, grid, container queries, and more which have supercharged the ability to quickly build responsive styles. While we're far from the days of using tables for layout and googling "how to vertically center css" once a week, the language itself hasn't had to change much. This is because CSS offers two well rounded ways of applying styles that work pretty well: inline styles and stylesheets.

Inline styles let you quickly add targeted rules to a single element. Much maligned historically due to the fact that many abused them and thus failed to keep their code DRY, there's really nothing wrong with inline styles. If there **is** something wrong with them, it's simply that an HTML attribute is a kind of clunky place to write out styles. When you're writing in a plain string it's harder to get nice formatting or static analysis. But if you're a good developer you won't use inline styles this way very often.

Stylesheets are the much more powerful feature. They let you assign a set of rules to zero, one, or many elements at once with the minimum amount of code. They also include all the fancy features like media queries, container queries, and pseudo-elements, which are not available inline. Flaws that existed in the early days of stylesheets have largely been remedied, albeit not always in the most desirable way. SCSS variables had broader support (since they simply compiled to basic CSS) and were prettier than CSS variables, but eventually SCSS started losing steam as the features it offered became less and less important in the face of an improving CSS.

CSS definitely isn't perfect in its fundamentals. Like JavaScript's `==` operator, some ideas were bad then and are still bad. CSS chooses which styles overwrite others based on selector specificity, leading some style debugging to be a bit of a rat's nest where the developer ends up bailing out to `!important` tags, which just kick the can down the road. Worse yet, when two rules have the same specificity, the default functionality is to pick whichever is defined last in the stylesheet. So, in this example, the styles of `two` win out over `one`, because the `.two` rule is declared after the `.one` rule, even though the `one` class comes second on the div.

```html
<style>
.one {
	text: red
}
.two {
	text: blue
}
</style>
<div class="two one"></div>
```

With modern multi-sheet websites and bundlers, this can get confusing fast as it can be hard to keep track of which sheet was loaded first on every page.

Additionally, CSS's status as a separate language from JavaScript is a blessing and a curse. It's a blessing in that CSS can be downloaded, parsed, and rendered in parallel extremely quickly by modern browsers, sidestepping the single-threadedness of JavaScript. But a curse in that modern apps simply require some amount of JavaScript-CSS interop, including sometimes sharing variables. As separate languages, this means duplicating code between the two languages.

## Modern Tooling

These, however, are solvable problems especially with modern tooling which can bridge the gaps, albeit often with their own caveats. Tools like [styled-components](https://styled-components.com/) brought JS and CSS together fairly seamlessly, giving you all the power of JavaScript (functions, etc) in your CSS. The caveat is that styles are compiled into Javascript (slow, single threaded) rather than CSS (fast, parallel). Tools like [vanilla-extract](https://vanilla-extract.style/) have done an admirable job giving you fully typed CSS-in-JS-in-CSS, compiling styles into separately bundled CSS files. Lastly, tools like React have made inline styling vastly better by naturally translating inline CSS into st typed objects.

## Okay, now can we dunk on Tailwind?

For reasons we'll get into later, Tailwind decided to burst on to the scene and become the default styling solution for all modern web development despite taking each and every one of these problems, exacerbating them, and applying them to places that didn't have them before. Let's start with the simple, basic model that CSS offers: inline styles and stylesheets. Inline styles let you control single element styles simply and fairly explicitly: `background: red; color: blue;`. Classes let you control multi-element styles simply, with the slight annoyance that it's easy to misspell your class name and spend way too long debugging before realizing it: `class="todo-item"`.

For no discernible reason, Tailwind exclusively offers inline styles via classes. Classes are single strings separated by spaces, not key-value pairs. So the classes must be something like `class="bg-red txt-blue"`. Key and value must be obscured into a single string. These are plain strings, so if you misspell something your editor is not going to tell you and you'll just have to find out once you get into the browser. Did you notice that `txt-blue` is wrong, and it should actually be `text-blue`? No? Get used to it, you'll make that mistake and more every day and only find out after spending too much time staring at the HTML inspector.

## Rule sets

What about applying a set of rules to multiple elements, as you do in style sheets with class rule sets, what does Tailwind offer for that?

Nothing. The answer is nothing. Tailwind's official recommendation for this is to ignore everything you've ever learned about constants and duplicate your class names, and simply remember to always use multi-cursor editing any time you touch them:

<img src="./multi-cursor-editing.png" alt="When duplication is localized to a group of elements in a single file, the easiest way to deal with it is to use multi-cursor editing to quickly select and edit the class list for each element at once.">

You can, of course, disobey the Tailwind overlords and create constants or components, but those solutions end up clunky because you are dealing purely with strings instead of objects. An element with a mere 10 CSS rules, will inevitably wrap in your editor and be more difficult to read and extend than a simple object would be:

```jsx
const sharedClass = `mx-auto max-w-md overflow-hidden rounded-xl bg-white shadow-md text-black border border-black border-solid`;
return <div className={
	clsx(sharedClass, {'display-none': !visible})
}></div>
```

vs.

```jsx
const sharedInline = {
	marginLeft: 'auto',
	marginRight: 'auto',
	maxWidth: MEDIUM_WIDTH,
	overflow: 'hidden',
	borderRadius: EXTRA_LARGE_ROUNDED,
	background: 'white',
	boxShadow: MEDIUM_BOX_SHADOW,
	color: 'black',
	border: '1px solid black',
};
return <div styles={{
	...sharedInline, display: visible ? 'block' : 'none'
}}></div>
````

## CSS's Problems are Tailwind's Problems

Tailwind offers no solution to the built in problems of CSS. Namely, it offers nothing to deal with the specificity based conflict resolution. Worse yet, tailwind classes are generated dynamically outside of your purview by the bundler and thus make it even harder to understand who will win a specificity conflict. For example:

```jsx
<div className={clsx('color-red', {
	'color-blue': currentPage === activePage})
}></div>
```

This seems straightforward, right? Red when not active, blue when active. In practice? Not so simple. Whichever class tailwind put first in its stylesheets, something basically totally out of your control, wins. Tailwind's recommendation is to, once again, ignore basic coding principles and duplicate your business logic:

```jsx
<div className={clsx({
	'color-red': currentPage !== activePage
	'color-blue': currentPage === activePage
})}></div>
```

Compare this to, say, simply using inline styles:

```jsx
<div styles={{
	color: currentPage === activePage ? 'blue' : 'red'
}}></div>
```

As a result, tailwind developers fall back on the same trick as the CSS developers of yore: spamming important tags (in the form of `!` suffixes on their class names) every time things don't work out nicely.

## Did you really say bundler?

Oh yeah, did I mention that? Despite offering no real solutions to CSS's problems and instead making them worse, Tailwind requires a plugin and a bundler to function. It can not be simply imported and placed in a plain web page. This bundler is doing code processing so basic it's almost admirable. It simply searches all your files and looks for things that look like Tailwind classes, and then it makes CSS rule sets for each one.

The oft-touted benefit of this system is that Tailwind will minimize your bundle sizes by only including what you need. Unfortunately this benefit does not hold up to basic scrutiny on medium-to-large codebases. By the time your codebase gets big enough to actually worry about how much CSS you have, you will have one class for every individual possible CSS rule you'll ever use. Still, this isn't much of a problem since CSS loads in parallel and it loads fast.

The problem is what it does to your *JavaScript bundle sizes*. Tailwind expects you to define styles via several classes on basically every element in your codebase. Meaning every time you use it you are writing out long strings which increase your slow, single-threaded, fully blocking JavaScript bundle size. Consider the following simple example with plain CSS:

```
// CSS
.todo-item {
	color: red;
	background: blue;
}
// JS
<div className='todo'>1</div>
<div className='todo'>2</div>
<div className='todo'>3</div>
```

And this one with tailwind:
```
// CSS (Generated by Tailwind)
.text-red {
	color: red;
}
bg-blue: {
	background: blue;
}
// JS
<div className='text-red bg-blue'>1</div>
<div className='text-red bg-blue'>2</div>
<div className='text-red bg-blue'>3</div>
```

In this simple but common example, tailwind generates a larger CSS bundle and a larger JS bundle! Lets give the benefit of the doubt and say the codebase designed around the first style, with plain CSS classes, is going to have lots of duplicated properties. Across various selectors you'll likely repeat things like `color: var(--warning-color)` several times. This will generate more CSS. But *that's just fine*.

CSS bundle size matters an order of magnitude less than JavaScript bundle size. On the tailwind side of things you are basically using inline styles but stuffed into a className block. That means tons of repeasts of the same class, like `txt-warning`. But this time it's increasing your *Javascript* bundle size, halting your entire app while that larger file is downloaded, parsed, and run.

# Developer Friendliness

Tailwind does nothing to reduce the mental load on your developers to understand, read, and write in your codebase. In fact it does the opposite. Your developers are not spared the hassle of learning CSS by instead learning tailwind's abstractions. In order to understand and debug your code you will still need to understand every CSS rule that tailwind translates to. So now, with the magic of tailwind, developers have to understand not just that `background-color` is the CSS key to set a background color, but they also must understand that classes prefixed with `bg-` mean background color.

Tailwind offers no type safety and little in the way of developer tooling outside of editor extensions that let you hover over a class to see the actual CSS that it translates to. Writing code with Tailwind means constantly hovering your cursor over class names and waiting a moment to see that your class translates to `align-items: center`. And when no hover comes up you know you mistyped and now you have to google "tailwind flexbox align items center" to remember it's not `align-items-center` or even `align-center`, it's `items-center`. All problems in Tailwind must be solved this way, squinting at the HTML inspector or squinting at codebase hovers.

When Tailwind does a major version update, it will sometimes rework its class names a bit. Every time this happens you need to use the codemods that Tailwind distributes with each update. You must run the program then carefully inspect the thousands of changes it has made, as it can only do so much to understand your codebase and realize what is a tailwind class and what is a plain string. It should be stressed here that this is entirely a manufactured problem for Tailwind. When other libraries change APIs, they can make the process easy through type systems, deprecation warnings, and clear error messages because they did not decide to base their entire library on parsing arbitrary strings.

## But what about using media queries inline?

The one decent thing about Tailwind is the relative ease with which CSS's "stylesheet only" features can be accessed inline. For example you can set up a CSS rule that only applies to an element on large screens with the simple matter of prefixing that class with `lg:`. This is kind of nice and is something that is, objectively, annoying to do in raw CSS. However, every other CSS-in-JS tool I've used also offers a convenient way to do this. More importantly, these solutions scale better. If you have five rules that should be different on large screens, you must write `lg:` five times and hover each one to make sure it's working. In a tool like `vanilla-extract` you would define one media query with all your rules underneath.

There are some things that Tailwind simply can not do and in this case developers simply fall back to plain CSS or inline styles with JavaScript. Meaning that, once again, the mental load of understanding the codebase is increased. You need to understand not only that you might be reading tailwind classes at any given point in time but that you are also dealing with plain CSS classes and you'll need to track down where those are in your style sheets what they are interacting with. You will also need to understand how to read and use inline styles in conjunction with everything else.

Do you see what I mean when I say the worst of all worlds?

## So what's the best of all worlds?

I like [vanilla-extract](https://vanilla-extract.style/). It's not the best of all worlds but it's great at almost everything. I also don't mind writing apps with plain CSS, though this has problems as it can get hard to keep track of which styles are applying to what. I've also written decently sized apps purely using inline styles in React with some basic constants set up and it works pretty well, though that too has problems like the lack of media queries and increasing JS bundle size. My point here isn't to say that there is a best of all worlds. My point is to say that Tailwind is the worst of all worlds.

## Okay, so why does everyone use tailwind if it's the worst of all worlds?

I think the first and most important factor that led to Tailwind's success is that Tailwind does one thing very correctly: it demands the developer who installs it set up a config file that lays out all their codebase-wide constants: colors, margin sizes, fonts, border radii, etc. Writing individual styles that do not use a pre-configured size/color/etc from the config file is clunky and annoying in Tailwind. This is a good thing. This is an unironic win for Tailwind. More than anything else, this is what a large codebase with multiple frontend devs needs: a rigid set of global constants that everyone is strongly incentivized to use. This one thing can outweigh all of Tailwind's faults when compared to a codebase with no such centralized standards.

I believe this is where Tailwind has succeeded and other libraries have struggled. Libraries like [vanilla-extract](https://vanilla-extract.style/) are legitimately great. But when I set up vanilla-extract in a new codebase I have to set up my own structure for global constants and make sure everyone is importing from that. For me, this works. I like to set up my own structure. I like having Javascript tools available in those files do things like generate colors by inverting or tinting other colors. But creating this kind of structure requires foresight and discipline to do it right and ensure it is followed. Every developer must read the docs on how our constants work and not stray from them. Code reviewers must know the system and know how to identify off-limits behavior.

Since Tailwind has a single magical config file that instantly makes all items inside it globally available, the documentation of how constants work is outsourced to the tailwind docs. Questions of "why do we structure our constants this way?" can be answered simply: that's just how Tailwind works. There's no room to bicker about little things the way we all used to quarrel about where the line breaks should be before prettier came along and let us defer that decision making to the tool. This is not a bad thing. I like that I no longer worry about trailing commas, I just `ctrl-s` and a library ensures me and every other developer in my codebase uses them.

When I see companies adopting Tailwind, they are mostly doing it because the problem they recognized was a lack of standards and consistent colors, which Tailwind offers an out of the box solution for. I think there are better libraries than Tailwind. Libraries that lead to smaller file sizes and better consistency. But to succeed some of these libraries may need to start being more authoritative. I love that vanilla-extract lets me do my own thing, but providing an easy to use default structure, that can be replaced if desired, would help adoption.

Lastly, Tailwind has also been buoyed by being by being the default styling that just about any LLM or vibe coding tool will produce unless it is explicitly asked not to. This feels like both uncharted and charted territory. Plenty of developers started using jQuery because the first StackOverflow result in their search explained how to solve that problem with jQuery.

But today we have a much larger set of decisions about codebase design being made all at once by a single tool. And despite repeated claims that "English is the programming language of the future", English is not in fact the language of the present. Developers who outsource these crucial decisions to LLMs are going to keep getting the worst of all worlds once the codebase becomes to unwieldy for vibes and needs actual developers.

{% endraw %}
