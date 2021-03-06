<table align="center"><tr><td>
<h1 align="center">
  <p><a arget="_self" href="https://github.com/z-shell/zi/">
  <img align="center" src="https://github.com/z-shell/zi/raw/main/docs/images/logo.svg" alt="ZI Logo" width="60px" height="60px" /></a>
  ❮ ZI ❯ Package - Brew Completions </p>
</h1>
<h2 align="center">
  <p> A package brings <a href="https://docs.brew.sh/Shell-Completion">Homebrew Shell Completion</a> under the control of Zsh & ZI </p>
</h2>
<h3 align="center">
<table>
    <tr>
        <td><b>Package source:</b></td>
        <td>Tarball</td>
        <td>Binary</td>
        <td>Git</td>
        <td>Node</td>
        <td>Gem</td>
        <td>Mod</td>
    </tr>
    <tr>
        <td><b>Status:</b></td>
        <td>❌</td>
        <td>❌</td>
        <td>❌</td>
        <td>❌</td>
        <td>❌</td>
        <td>✔️ (default)</td>
    </tr>
</table></h3>
  <p><img align="center" src="https://user-images.githubusercontent.com/59910950/167327056-05f71a75-c733-41ab-b7fa-082847caf934.png" alt="Brew Completion System" width="100%" height="auto" /></p>
</td></tr></table><hr />

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

```shell
# Utilize Turbo and initialize the completion with fast compinit
zi wait pack atload=+"zicompinit_fast; zicdreplay" for brew-completions
```

The ZI command executed will be equivalent to:

```shell
zi has'brew' id-as='brew-completions' wait as='completion' lucid \
  atclone="+zi-message 'Installing Brew completions...'; \
    command mkdir -p ${ZPFX}/completions; \
    command cp -f $(brew --prefix)/share/zsh/site-functions/_* ${ZPFX}/completions; \
    zi creinstall -q $(brew --prefix)/share/zsh/site-functions" \
  atload='fpath=( ${(u)fpath[@]:#$(brew --prefix)/share/zsh/*} ); fpath+=( ${ZPFX}/completions )' \
  atpull='%atclone' run-atpull nocompile countdown for \
    z-shell/0
```

---

> This repository compatible with [ZI](https://github.com/z-shell/zi)

The [ZI](https://github.com/z-shell/zi) package that uses the [zsh-string-lib](https://github.com/z-shell/zsh-string-lib) to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.
