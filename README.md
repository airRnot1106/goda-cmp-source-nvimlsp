# goda-cmp-ext-nvimlsp.vim

Neovim LSP completion for [goda-cmp.vim](https://github.com/Shougo/goda-cmp.vim).

This source asks the LSP clients that Neovim already has attached to the buffer. It starts no language server, so your servers stay configured in one place and run once per language. Its behavior and parameters follow [ddc-source-lsp](https://github.com/Shougo/ddc-source-lsp).

## Dependencies

- [goda-cmp.vim](https://github.com/Shougo/goda-cmp.vim)
- [goda.vim](https://github.com/Shougo/goda.vim)
- Neovim nightly (0.13). Completion did not appear in testing with 0.12.6.

## Install

The source is a Go package that your goda-cmp configuration imports. Its Neovim side is embedded in the binary, so no plugin needs to be installed.

```sh
cd ~/.config/nvim/goda-cmp
go get github.com/airRnot1106/goda-cmp-ext-nvimlsp.vim
```

## Configuration

```go
import "github.com/airRnot1106/goda-cmp-ext-nvimlsp.vim/ext/source/nvimlsp"

b.AddSource(nvimlsp.New(nvimlsp.Params{
	EnableResolveItem:        true,
	EnableAdditionalTextEdit: true,
}))
```

Add `"nvimlsp"` to `Sources`, then rebuild with `:call goda_cmp#build()`.

See `:help goda-cmp-ext-nvimlsp`.
