# devcontainer-nix
Dev Container with Nix enabled

```shell
mkdir project && cd project
```
Now depending on the development language you can proceed:

  - with Haskell `nix flake init --template "github:DeterminateSystems/zero-to-nix#haskell-dev"`
  - with Python `nix flake init --template "github:DeterminateSystems/zero-to-nix#python-dev"`
  - with Javascript `nix flake init --template "github:DeterminateSystems/zero-to-nix#javascript-dev"`
  - ...

More details about Nix development [here][def]

[def]: https://zero-to-nix.com/start/nix-develop#flake
