# vim-auto-popmenu

A tiny and lightweight script (200 lines) to provide you same experience as YouCompleteMe for buffer, dictionary and tags completion without installing heavy completion engines and sources.

## What Is It ?

Semantic completion is great, but sometimes, when you are coding in an obscure laguange which is lack of LSP support, or you are working in a temporary system and you don't want waste time to set up a heavyweight completion engine and rebuild a background server.

In these circumstance, vim's built-in completion system is good enough for you, it can collect keywords from buffers and dictionary or ctag files, but requires you to press `<c-n>` or `<c-x><c-k>` manually.

This tiny little script will help you to popup the completion menu when you have entered 1 or 2 alphabets and provide you exactly the same experience as YouCompleteMe:

