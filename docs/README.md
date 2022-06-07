<div align="center"><table><tr><td>
  <a title="ZI" target="_self" href="https://github.com/z-shell/zi/">
<h1><img align="center" style="width:60px;height:auto" src="https://github.com/z-shell/zi/raw/main/docs/images/logo.svg" alt="ZI Logo" /></a>
  ❮ ZI ❯ Package - Brew Completions </h1>
<h2>

| **Package source:** | Tarball | Binary | Git | Node | Gem |        Mod         |
| :-----------------: | :-----: | :----: | :-: | :--: | :-: | :----------------: |
|     **Status:**     |   :x:   |  :x:   | :x: | :x:  | :x: | :heavy_check_mark: |

</h2>
  <h3>
  <p> A package brings <a href="https://docs.brew.sh/Shell-Completion">Homebrew Shell Completion</a> under the control of Zsh & ZI. </p>
  <p><img align="center" src="https://user-images.githubusercontent.com/59910950/167327056-05f71a75-c733-41ab-b7fa-082847caf934.png" alt="Brew Completion System" width="100%" height="auto" /></p>
  </h3></td></tr></table></div><hr />

## Available `pack''` invocations

Selectively enable or disable the completions with `cenable` and `cdisable`.

### Default Profile

```shell
zi pack for brew-completions
```

```shell
# Utilize Turbo
zi wait pack for brew-completions
```

```shell
# Utilize Turbo and initialize the completion system
zi wait pack atload=+"zicompinit; zicdreplay" for brew-completions
```

The ZI command executed will be equivalent to:

```shell
zi has'brew' id-as='brew-completions' wait as='completion' lucid \
  atclone='print Installing Brew completions...; \
    mkdir -p $ZPFX/brew_comps; \
    command cp -f $(brew --prefix)/share/zsh/site-functions/^_* $ZPFX/brew_comps; \
    zi creinstall -q $(brew --prefix)/share/zsh/site-functions' \
      atload='fpath=( ${(u)fpath[@]:#$(brew --prefix)/share/zsh/*} ); fpath+=( $ZPFX/brew_comps )' \
        atpull='%atclone' nocompile run-atpull for \
          z-shell/0
```

---

> This repository compatible with [ZI](https://github.com/z-shell/zi)

The [ZI](https://github.com/z-shell/zi) zsh package that can use the NPM package registry to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.
