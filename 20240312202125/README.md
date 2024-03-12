# Go: Configuring neovim 

How to setup nvim for go lang development

- [Programming Go in Neovim](https://www.getman.io/posts/programming-go-in-neovim/)

---

# Seting up LSP

```
require'lspconfig'.gopls.setup{}
```

# Creating config file

Noevim config file should be located in `~/.config/nvim`, if folder doesn't exists create it.
Base file configuration is `init.lua`, if it doesn't exist create it.

# Error navigation

```
buf_set_keymap('n', 'gep', '<cmd>lua vim.lsp.diagnostic.goto_prev()<CR>', opts)
buf_set_keymap('n', 'gen', '<cmd>lua vim.lsp.diagnostic.goto_next()<CR>', opts)
```
# Formating

```
if client.resolved_capabilities.document_formatting then
    buf_set_keymap("n", "ff", "<cmd>lua vim.lsp.buf.formatting()<CR>", opts)
elseif client.resolved_capabilities.document_range_formatting then
    buf_set_keymap("n", "ff", "<cmd>lua vim.lsp.buf.range_formatting()<CR>", opts)
end
```

## Format on save

```
autocmd BufWritePre *.go lua vim.lsp.buf.formatting()
```

# Code actions

```
buf_set_keymap('n', 'ca', '<Cmd>lua vim.lsp.buf.code_action()<CR>', opts)
```

# Code navigation

```
buf_set_keymap('n', 'gD', '<Cmd>lua vim.lsp.buf.declaration()<CR>', opts)
buf_set_keymap('n', 'gd', '<Cmd>lua vim.lsp.buf.definition()<CR>', opts)
buf_set_keymap('n', '<space>D', '<cmd>lua vim.lsp.buf.type_definition()<CR>', opts)
buf_set_keymap('n', 'gi', '<cmd>lua vim.lsp.buf.implementation()<CR>', opts)
buf_set_keymap('n', 'gr', '<cmd>lua vim.lsp.buf.references()<CR>', opts)
```

# Refactor

```
buf_set_keymap('n', 'cr', '<cmd>lua vim.lsp.buf.rename()<CR>', opts)
```
