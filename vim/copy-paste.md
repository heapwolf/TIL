Integrating vim's copy and paste functions with macOS.

So, lets say you use `v` or `ctrl+v` to copy some text. This nifty little
setting will copy that to your pasteboard (aka clipboard) in macOS.

```vim
set clipboard=unnamed
```

Here's the [source](http://vim.wikia.com/wiki/Accessing_the_system_clipboard)
for this in case you want to know more. It's vim, so of course there are a
billion ways to do this.

