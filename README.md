# vim-auto-popmenu

A tiny and lightweight script (200 lines) to provide you same experience as `YouCompleteMe` for buffer, dictionary and tags completion without installing heavy completion engines and building background servers.

## What Is It ?

Semantic completion is great, but sometimes, when you are coding in an obscure laguange which is lack of LSP support, or you are working in a temporary system and you don't want waste time to set up a heavyweight completion engine and build a background server.

In these circumstances, vim's built-in completion system is good enough for you, it can collect keywords from buffers and dictionary or ctag files, but requires you to press `<c-n>` or `<c-x><c-k>` manually.

This tiny little script will help you to popup the completion menu when you have entered 1 or 2 alphabets and provide you exactly the same experience like `YouCompleteMe`:

![](images/demo.gif)

## Features

- Popup the completion menu automatically.
- `Tab` or `shift`+`TAB` to cycle keywords, `<c-e>` to cancel.
- Same experience like `YouCompleteMe` for `buffer`, `dict` and `tags` completion.
- Green, everything is local to buffer, will not pollute your vim or disturb other plugins.
- Capable to co-exist with other completion plugins.
- No heavy engines, no need to build background servers.
- Faster and more handy than the old famous `AutoComplPop`.
- Portable, just a simple `apc.vim` script, easy to be distributed.

## Usage

That's all you need:

```VimL
Plug 'skywind3000/vim-auto-popmenu'

" enable this plugin for filetypes
let g:apc_enable_ft = {'text':1, 'markdown':1, 'php':1}

" source for dictionary, current or other loaded buffers, see ':help cpt'
set cpt=.,k,w,b

" don't select the first item.
set completeopt=menu,menuone,noselect

" suppress annoy messages.
set shortmess+=c
```

And perhaps a dictionary database plugin:

```
Plug 'skywind3000/vim-dict'
```

Then you go.

## Cooperative

If you are using `YouCompleteMe`, disable it for certain filetypes:

```VimL
let g:ycm_filetype_blacklist = {'text':1, 'markdown':1, 'php':1}
```

and enable this plugin for these files:

```VimL
let g:apc_enable_ft = {'text':1, 'markdown':1, 'php':1}
```


## Credit

- https://github.com/othree/vim-autocomplpop.
