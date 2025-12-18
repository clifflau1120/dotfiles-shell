# Dotfiles

This repository contains dotfiles that configure my shell.

## Pre-requisites

### AUR helper

- [`paru`](https://github.com/Morganamilo/paru)

### Symlinks

- [`stow`](https://www.gnu.org/software/stow/) - creates symlinks for dotfiles

### Shell

- [`zsh`](https://www.zsh.org/)
- [`ohmyzsh`](https://ohmyz.sh/) - manage `zsh` configurations
- [`starship`](https://starship.rs/) - a minimal and blazing-fast prompt built in rust

### Fonts

- `apple-fonts`
- `ttf-iosevka-nerd`
- `ttf-iosevkaterm-nerd`
- `otf-font-awesome`

### User utilities

- [`bat`](https://github.com/sharkdp/bat) - replaces `cat` with syntax highlighting and git support
- [`btop`](https://github.com/aristocratos/btop) - replaces `top` more gestures and prettier tui
- [`delta`](https://github.com/dandavison/delta) - enhances `git diff` with more user friendly displays
- [`dust`](https://github.com/bootandy/dust) - replaces `du` with more intuitive overview
- [`direnv`](https://direnv.net/) - load/unload environment variables depending on current working directory
- [`eza`](https://eza.rocks/) - replaces `ls` with hyperlinks, git status support and more
- [`fd`](https://github.com/sharkdp/fd) - replaces `find` with more intuitive syntax
- [`fzf`](https://junegunn.github.io/fzf/) - a general purpose fuzzy-finder
- [`neovim`](https://neovim.io/) - replaces `vim` with better extensibility
- [`ripgrep`](https://github.com/BurntSushi/ripgrep) - replaces `grep` with better performance and modern ignores
- [`zoxide`](https://github.com/ajeetdsouza/zoxide) - replaces `cd` with intelligent ranking and frequency database

### Development utilities

- [`podman`](https://podman.io/)
- [`k9s`](https://k9scli.io/)
- [`kubectl`](https://kubernetes.io/docs/reference/kubectl/)
- [`kubectx`](https://github.com/ahmetb/kubectx/)
- [`bun`](https://bun.com/)
- [`pnpm`](https://pnpm.io/)
- [`rust`](https://rust-lang.org/)
- [`uv`](https://docs.astral.sh/uv/)
- [`flutter`](https://docs.flutter.dev/)
- [`mc`](https://docs.min.io/enterprise/aistor-object-store/reference/cli/)
- [`gcloud`](https://docs.cloud.google.com/sdk/docs/install)
- [`helm`](https://helm.sh/)
- [`terraform`](https://developer.hashicorp.com/terraform/)
- [`opentofu`](https://opentofu.org/)
- [`trivy`](https://trivy.dev/)


## Installation

1. Install all [pre-requisites](#pre-requisites)

2. Create `zsh` completions for those not built-in:

    ```zsh
    export ZSH_COMPLETIONS=~/.oh-my-zsh/completions
    mkdir -p $ZSH_COMPLETIONS && \
        bat --completion zsh > $ZSH_COMPLETIONS/_bat && \
        pnpm completion zsh > $ZSH_COMPLETIONS/_pnpm && \
        rg --generate complete-zsh > $ZSH_COMPLETIONS/_rg && \
        trivy completion zsh > $ZSH_COMPLETIONS\_trivy &&
        curl https://raw.githubusercontent.com/bootandy/dust/master/completions/_dust > $ZSH_COMPLETIONS/_dust && \
        curl https://raw.githubusercontent.com/sharkdp/fd/master/contrib/completion/_fd  > $ZSH_COMPLETIONS/_fd
    ```

3. Create symlinks for the dotfiles

    ```sh
    stow -t ~/ .
    ```
