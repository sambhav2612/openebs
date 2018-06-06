# Setting up vim-go on Ubuntu 16.04

## Pre-requisites

Let us assume that you already have a working Go environment. You to make sure that your `$GOPATH/bin` is included in your PATH.

### Install vim, if not already done

```bash
sudo apt-get install vim
```

### Install and setup vim-go

The following link has detailed instructions on setting up `vim-go` on your system and using the shortcuts.

- [https://github.com/fatih/vim-go-tutorial#quick-setup](https://github.com/fatih/vim-go-tutorial#quick-setup)

The following is an extract of the command required to install on Ubuntu.

### Step 1: Download the vim-plugin and vim-go plugins

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
git clone https://github.com/fatih/vim-go.git ~/.vim/plugged/vim-go
```

### Step 2: Setup vimrc to use the downloaded plugins

Create a vim config file `~/.vimrc` with the following content:

```bash
call plug#begin()
Plug 'fatih/vim-go', { 'do': ':GoInstallBinaries' }
call plug#end()
```

### Step 3: Verify plugins are installed and initialize go dependencies

Launch vim. In the vim editor, type the following:

```bash
:PlugInstall
```

The above should show a window that the required plugins have been installed.

Now, run the following in the same vim editor:

```bash
:GoInstallBinaries
```

You should see the dependent go binaries downloaded and installed in your `GOPATH/bin`.

### Using vim-go

The `vim-go` repository provides a large number of additional plugins and shortcuts that can be added to the `.vimrc`. However, with the default `.vimrc` use above, you can already get going:

- Initiate the build `:GoBuild`.
- Navigate to the definition `ctrl-{`.
- Navigate back `ctrl-o`.

If you need any help with git, refer to this [git cheat sheet](./git-cheatsheet.md) and go back to the [**contributing to OpenEBS Documentation**](../../CONTRIBUTING.md) guide to proceed.