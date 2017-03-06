# Unique arrays
`Array.from` is pretty handy. It will convert array-like objects to actual
arrays. Like the odd-ball `arguments` object (which you really shouln't need
anymore). You can also generate values with it, for example,
`Array.from(Array(100), Math.random)`. But the most useful thing I've been
finding lately is how when combined with the `Set` value-container type, I can
create unique arrays.

`Set`'s constructor takes array-like values. And since Sets must be unique, it
will automatically reduce the values. Returned to Array.from we get a unique
array...

```js
Array.from(new Set([1,2,2,3])) // [1,2,3]
```

But it gets more useful. Let's say we are programming in the browser and we
have a nodeList, but we want only unique references to elements. Consider an
array of elements that has been merged from different sources...

```js
const nodeList = document.querySelectorAll('.stuff, .other-stuff')
const list = Array.from(nodeList) // bummer, now we have a haystack
```

The quick fix for this is simple!

```js
const uniqueList = Array.from(new Set(list))
```

This works because equality is checked by the `Set` constructor based on either
the primitive type or the reference of the object.

