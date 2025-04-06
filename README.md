# slip community packages

This repository contains community-maintained `slipfiles` — installation instructions and metadata for packages used with [slip](https://github.com/slippkg/cli).

Slipfiles define how a package is installed using Git repositories, archive URLs, or script-based logic. They are written in plain Lua and live in a structured, namespaced folder hierarchy.

---

## 📁 Structure

```
slipfiles/
  github.com/
    starship/
      starship.lua
    junegunn/
      fzf.lua
  gitlab.com/
    user/
      tool.lua
  archive.slip.run/
    mytool/
      mytool.lua
```

Each package is stored in a directory that mirrors its source domain and namespace. The `.lua` file is named after the package itself.

This format allows for:
- Avoidance of naming collisions
- Easier mirroring of upstream sources
- Clean resolution by `slip` CLI tools

---

## 🧩 What is a slipfile?

A `slipfile` is a Lua script that defines:

- How to fetch the package (git, tarball, binary)
- How to install it (e.g. where to move files)
- How to determine its version
- Optional config or post-install behavior

Slipfiles are designed to be portable, auditable, and version-controlled. They are not required for `slip` to work — but they offer a shared standard and save time.

---

## 📦 Contributing

Contributions are welcome. Each PR is automatically validated for structure and safety.

To contribute:

1. Fork this repo
2. Add a new directory under `slipfiles/<source>/<namespace>/<package>.lua`
3. Include a Lua file with install logic and metadata
4. Submit a pull request

Guidelines and schema: [docs.slip.run](https://docs.slip.run)

---

## 🔐 License

All content in this repository is licensed under the [MIT License](https://opensource.org/licenses/MIT). You may use, modify, distribute, and reuse the contents freely.


