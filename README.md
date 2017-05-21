## How Well Do You Know the Web? (Google I/O '17) / The Big Web Quiz

The Video: https://www.youtube.com/watch?v=vAgKZoGIvqs

The Site: https://bigwebquiz.com/


The Questions:

**think before scroll down for the anwsers**

#1 [Script elements] Which of the following script elements blocks the parser while the script downloads?

- A.

```html
<script src=“blah.js”></script>
```

- B.

```html
<script src=“blah.js” defer></script>
```

- C.

```html
<script src=“blah.js” async></script>
```

- D.

```html
<script src=“blah.js” async=“false”></script>
```



> related articles:
> - [Understanding the Critical Rendering Path
](https://bitsofco.de/understanding-the-critical-rendering-path/)
> - [Asynchronous vs Deferred JavaScript
](https://bitsofco.de/async-vs-defer/)
> - [Tackling Render Blocking CSS for a Fast Rendering Website](https://www.sitepoint.com/critical-rendering-path-css-fast-loading-website/)


#2 [Module scripts] According to the spec, which of the following scripts executes first?

- A.

```html
<script src=“script-one” type=“module”></script>
```

- B.

```html
<script type=“module”>console.log(‘script-two’)</script>
```

- C.

```html
<script defer>console.log(‘script-three’)</script>
```

- D.

```html
<script src=“script-four” defer></script>
```

#3 [Caching headers] What does the “Cache-Control: must-revalidate,max-age:31536000” response header tell the browser to do?

- A. Don’t put this in the cache
- B. Cache it, but you can only use it after server validation
- C. Cache it, and you can use it without server validation for 31,536,000 seconds

#4 [Caching headers] What does the “Cache-Control: no-cache,max-age:31536000” response header tell the browser to do?

- A. Don’t put this in the cache
- B. Cache it, but you can only use it after server validation
- C. Cache it, and you can use it without server validation for 31,536,000 seconds

#5 [From caches to caches] Which cache does the browser check first?

- A. HTTP/2 push
- B. `<link rel=“preload”>`
- C. HTTP cache

#6 [SVG Compositing] We’re animating a `<circle>` in an SVG, which of the following animations will be automatically composited in Chrome 57?

- A. `transition: cx 2s;`
- B. `transition: cx 2s, transform 2s;`
- C. `transition: transform 2s;`
- D.  `transition: opacity 2s;`

#7 [DOM Compositing] We’re animating a `div`, which of the following animations can be automatically composited in Chrome 57?

- A. `transition: margin-left 2s;`
- B. `transition: width 2s, transform 2s;`
- C. `transition: transform 2s;`
- D.  `transition: opacity 2s;`

#8 [Animating after an event] You have an element with no transform, and the following code. According to the HTML spec, what happens next?

```js
btn.onclick = _=>{
	el.style.transform = ‘translateX(200px)’;
	el.style.transition = ‘transform 0.3s ease-out’;
	el.style.transform = ‘translateX(100px)’;
}
```

- A.  It slides to the right
- B.  It slides to the left
- C.  It does the macarena
- D.  It snaps to 100px

#9 [Animating after an event] You have an element with no transform, and the following code. According to the HTML spec, what happens next?

```js
btn.onclick = _=>{
	el.style.transform = ‘translateX(200px)’;
	el.style.transition = ‘transform 0.3s ease-out’;
	reqiestAmationFrame(_=>{
		el.style.transform = ‘translateX(100px)’;		
	})
}
```

- A.  It slides to the right
- B.  It slides to the left
- C.  It snaps to 100px
- D.  It gains sentience, and feels only sadness

#10 [Animating after an event] What could go in here to force a synchronous update in Chrome 57?

```js
btn.onclick = _=>{
	el.style.transform = ‘translateX(200px)’;
	el.style.transition = ‘transform 0.3s ease-out’;
	// answer goes here.
	el.style.transform = ‘translateX(100px)’;
}
```

- A.  `el.getBoundingClientRect`
- B.  `window.getComputedStyle(el)`
- C.  `el.offsetWidth`
- D.  el.innerText

#11 [Height priorities] What happens with:

```css
.foo {
	min-height: 300px;
	max-height: 200px;
}
```

- A. foo will be 200px tall
- B. foo will be 300px tall
- C. foo will be 0px tall
- D. Crashes all browsers in a 3 mile radius


#12 [Typed Array] After running this code, which of the following is set to 1?

```js
const array = new Int8Array(100);
array[‘.9’] = 1;
array[‘1.0’] = 1;
array[‘1.1’] = 1;
array[‘1.2’] = 1;
```

- A. `array[‘.9’]`
- B. `array[‘1.0’]`
- C. `array[‘1.1’]`
- D. `array[‘1.2’]`

#13 [Appending HTML] How many elements are created?

```js
document.body.innerHTML = ‘<p>Hello</p>’;
document.body.innerHTML += ‘<p>Everyone</p>’;
document.body.innerHTML += ‘<p>At</p>’;
document.body.innerHTML += ‘<p>I/O</p>’;
```

- A. 1
- B. 4
- C. 10
- D. 16

#14 [Which requests request?] Given this chunk of HTML, which resources are requested?

```html
<image src=“one”/>
<script source=“two”/>
<link rel=“stylesheet” media=“all” href=“three”/>
<link rel=“preload” href=“four”/>
```

- A. 1
- B. 2
- C. 3
- D. 4


The Answers:

- #1 A. note the `downloads` in the question, that’s the point.

- #2 C. type=“module” defer by default. And defer attribute’s not working on inline script.

- #3 C.

- #4. B. knowing when to cache and when not to.

- #5. B.

- #6.  none of them. SVG + Compositing

- #7.  B,C and D

- #8. A.

- #9. A.

- #10. A,C and D

- #11. B.

- #12. A and B

- #13.  C.

- #14. A. note tags that cannot self closing.
