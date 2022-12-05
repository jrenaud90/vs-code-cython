# vscode-cython

[![Version](https://vsmarketplacebadge.apphb.com/version/ktnrg45.vscode-cython.svg)](https://marketplace.visualstudio.com/items?itemName=ktnrg45.vscode-cython) [![Installs](https://vsmarketplacebadge.apphb.com/installs-short/ktnrg45.vscode-cython.svg)](https://marketplace.visualstudio.com/items?itemName=ktnrg45.vscode-cython)

[Main Repository](https://github.com/ktnrg45/vs-code-cython)

[Cyright LSP Repository](https://github.com/ktnrg45/cyright)

## Cython Language Extension for VS Code

![VS Code Cython Demo](https://github.com/ktnrg45/vs-code-cython/raw/master/assets/demo.gif)

# Features

- Syntax Highlighting
- Static Syntax Checking
- Go to definitions
- Import resolver for .pyx and .pxd files

# About

This extension provides syntax highlighting and a Static Syntax checker for the Cython language.
Cython is a superset of Python with it's own C-styled syntax mixed with Python syntax.

The static checker is based on [Pyright](https://github.com/microsoft/pyright) and will only support Cython/Python syntax version 3.0 and above.

This extension uses the configured Python interpreter/venv path from the `VS Code Python` extension.

# Limitations

These features would be nice to have but are not implemented.

- In-depth type analysis
- C headers analysis / inline C code analysis
- Cython C++ syntax parsing

# FAQ

- If no problems are reported will my code compile?

  > No. There are no guarantees that code will be compiled correctly

# Issues

Please report any issues in this repo.

# Installing

## Install with VS Code

Install normally through the extensions tab.

## Install from source

- Clone repo. For installation clone in the `<user home>/.vscode/extensions` folder.

- Ensure submodules are fetched with:

  ```
  git submodule update --init --recursive

  ```

- Install `npm`
- Run:
  ```
  make install
  ```

# Development

## Setup

To setup development environment:

- Follow the instructions for `Installing from source` (repo can be cloned anywhere on filesystem)

- Install development npm packages:

  ```
  make dev
  ```

- To rebuild lang-server and syntax file, Run:

  ```
  make build
  ```

## Syntax highlighting changes

Any changes should be made to `./grammars/cython.syntax.yaml`

The syntax file will need to be re-generated for VS Code to see changes.

To re-generate syntax file run:

```
make syntax
```

## Language Server (Cyright) Developement

If you would like to develop the Language server you can setup the development environment as such:

- Fork the [Cyright Repository](https://github.com/ktnrg45/cyright)

- Change the submodule remote:
  ```
  git submodule set-url -- cyright <URL of your Cyright Fork>
  ```

Pull requests should be created under the [Cyright Repository](https://github.com/ktnrg45/cyright).

**Do Not** submit a pull request in this repo with any submodule changes.
