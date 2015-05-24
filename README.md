# unite-matcher-hide-hidden-directories
## What it is
You need [unite.vim](https://github.com/Shougo/unite.vim) in order to use this
plugin. This plugin is ~~a ripoff of~~ heavily based off of
`matcher_hide_hidden_files.vim`, which is bundled with unite.vim. This plugin
was written as an attempt to resolve the issue where dot-directories are
listed first when doing `file_rec`.

Setting something like the following for unite.vim will hide any
file/directory that contains `/.` in the path (hence, anything starting with a
dot).

```vim
call unite#custom#source('file_rec/async',
        \ 'matchers', [
        \   'matcher_hide_hidden_files',
        \   'matcher_hide_hidden_directories',
        \   'converter_relative_word',
        \   ])
```

## Using with neobundle.vim
Here is a sample configuration using
[neobundle.vim](https://github.com/Shougo/neobundle.vim).

```vim
NeoBundleLazy 'NigoroJr/unite-matcher-hide-hidden-directories'
if neobundle#tap('unite-matcher-hide-hidden-directories')
  call neobundle#config({
        \ 'depends': 'Shougo/unite.vim',
        \ 'autoload': {
        \   'on_source': 'unite.vim',
        \ },
        \ })
  call neobundle#untap()
endif
```

## License
Same as unite.vim
