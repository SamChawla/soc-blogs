---
title: "Install node using nvm on ubuntu/Mac"
datePublished: Thu Nov 30 2023 09:35:03 GMT+0000 (Coordinated Universal Time)
cuid: clpl02crp000409l33abm2i9l
slug: install-node-using-nvm-on-ubuntumac
tags: nvm

---

NVM stands for Node Version Manager. It helps you install, manage and switch between multiple Node.js versions on your system. Here are the steps to install Node.js using NVM:

## Install NVM

You can install NVM using a script as follows:

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

Or using `wget`:

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

This will clone the NVM repository and install it on your system.

You'll then need to add the following lines to your `.bashrc` or `.zshrc` file:

```bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
```

After reloading your terminal, you can verify the installation with:

```bash
nvm --version
```

## Install Node.js

You can install Node.js with NVM using:

```bash
nvm install node
```

This will install the latest Node.js version. You can also specify a specific version:

```bash
nvm install 14.17.6
```

To install the latest LTS version, use:

```bash
nvm install --lts
```

## Switch Node Versions

To switch to a Node.js version, use:

```bash
nvm use 14.17.6
```

You can also use an alias like `node` or `lts`:

```bash
nvm use node   # latest version
nvm use lts    # latest LTS version
```

Hope this helps! Let me know if you have any other questions.