# `conf.d`

| Prefix | Purpose                    | Description                                                     |
| ------ | -------------------------- | --------------------------------------------------------------- |
| `00_`  | Core environment variables | `EDITOR`, `LANG`, `LC_*`, etc.                                  |
| `10_`  | Fish shell configuration   | Theme settings, abbreviations, and Fish-specific options.       |
| `20_`  | Shell UX                   | `fzf`, `starship`, `zoxide`, etc. — may depend on `00_`.        |
| `30_`  | Language runtimes          | `node`, `python`, `rust`, etc. — may depend on `00_` and `20_`. |
| `40_`  | Development tools          | `cargo`, `pnpm`, `poetry`, etc. — may depend on `30_`.          |
| `99_`  | Final tweaks               | Last-to-load configurations.                                    |
