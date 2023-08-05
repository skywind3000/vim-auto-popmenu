# vim-auto-popmenu

A tiny and portable script (169 lines) to provide you `YouCompleteMe` like experience for `buffer`, `dictionary` and `tags` completion without installing heavy completion engines and building background servers.

## What Is It ?

Semantic completion is great, but sometimes, when you are coding in an obscure laguange which is lack of LSP support, or you are working in a temporary system and you don't want waste time to set up a heavyweight completion engine and build a background server.

In these circumstances, vim's built-in completion system is good enough for you, it can collect keywords from buffers and dictionary or ctag files, but requires you to press `<c-n>` or `<c-x><c-k>` manually.

This tiny little script will help you to trigger the completion menu when you have entered 1 or 2 alphabets and provide you exact the same experience like `YouCompleteMe`:

![](https://skywind3000.github.io/images/p/auto-popmenu/demo.gif)

## Features

- Popup the completion menu automatically.
- `Tab` or `shift`+`TAB` to cycle keywords, `<c-e>` to cancel.
- Same experience like `YouCompleteMe` for `buffer`, `dict` and `tags` completion.
- Green, everything is local to buffer, will not pollute your vim or disturb other plugins.
- Capable to co-exist with other completion plugins.
- No heavy engines, no need to build background servers.
- Faster and more handy than the old famous `AutoComplPop`.
- Portable, just a simple `apc.vim` script, easy to be distributed.
- Only **169 lines**, you can even copy it to your `vimrc`.
- Convenience as a backup way for big completion plugins.

## Usage

That's all you need:

```VimL
Plug 'skywind3000/vim-auto-popmenu'

" enable this plugin for filetypes, '*' for all files.
let g:apc_enable_ft = {'text':1, 'markdown':1, 'php':1}

" source for dictionary, current or other loaded buffers, see ':help cpt'
set cpt=.,k,w,b

" don't select the first item.
set completeopt=menu,menuone,noselect

" suppress annoy messages.
set shortmess+=c
```

And perhaps a dictionary database plugin for many languages:

```
Plug 'skywind3000/vim-dict'
```

Then you go.

## Commands

### ApcEnable

Enable plugin for the current buffer manually. Useful when you didn't set `g:apc_enable_ft`.

### ApcDisable

Disable plugin for the current buffer.

## Cooperative

If you are using `YouCompleteMe`, disable it for certain filetypes:

```VimL
let g:ycm_filetype_blacklist = {'text':1, 'markdown':1, 'php':1}
```

and enable this plugin for these files:

```VimL
let g:apc_enable_ft = {'text':1, 'markdown':1, 'php':1}
```

## Configuration

1\) `g:apc_enable`

Default: 1
Set to 0 to disable this plugin.

2\) `b:apc_enable`

Default: unset
Set to 0 to disable this plugin for certain buffer.

3\) `g:apc_min_length`

Default: 2
Minimal characters to trigger the completion popup menu.

4\) `g:apc_trigger`

Default: `"\<c-n>"`
Key to trigger the completion popup menu.
Set to `"\<c-x>\<c-o>"` to trigger omni completion.

5\) `b:apc_trigger`

Default: unset
Specify trigger key for certain buffer, will override `g:apc_trigger` for certain buffer.

6\) `g:apc_cr_confirm`

Default: 0

Set to 1 to allow you choose the current keyword by ENTER.

## Credit

- https://github.com/othree/vim-autocomplpop.
