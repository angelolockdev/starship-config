# starship-config
My starship configurations

<p align="center">
  <img
    width="400"
    src="https://raw.githubusercontent.com/starship/starship/master/media/logo.png"
    alt="Starship – Cross-shell prompt"
  />
</p>

<p align="center">
  <a href="https://github.com/starship/starship/actions"
    ><img
      src="https://img.shields.io/github/workflow/status/starship/starship/Main workflow/master?label=workflow&style=flat-square"
      alt="GitHub Actions workflow status"
  /></a>
  <a href="https://crates.io/crates/starship"
    ><img
      src="https://img.shields.io/crates/v/starship?style=flat-square"
      alt="Crates.io version"
  /></a>
  <a href="https://repology.org/project/starship/versions"
    ><img
      src="https://img.shields.io/repology/repositories/starship?label=in%20repositories&style=flat-square"
      alt="Packaging status"/></a
  ><br />
  <a href="https://discord.gg/starship"
    ><img
      src="https://img.shields.io/discord/567163873606500352?label=discord&logoColor=white&style=flat-square"
      alt="Chat on Discord"
  /></a>
  <a href="https://twitter.com/StarshipPrompt"
    ><img
      src="https://img.shields.io/badge/twitter-@StarshipPrompt-1DA1F3?style=flat-square"
      alt="Follow @StarshipPrompt on Twitter"
  /></a>
</p>

<p align="center">
  <a href="https://starship.rs">Website</a>
  ·
  <a href="#🚀-installation">Installation</a>
  ·
  <a href="https://starship.rs/config/">Configuration</a>
</p>

<h1></h1>

<img
  src="https://raw.githubusercontent.com/starship/starship/master/media/demo.gif"
  alt="Starship with iTerm2 and the Snazzy theme"
  width="50%"
  align="right"
/>

**The minimal, blazing-fast, and infinitely customizable prompt for any shell!**

- **Fast:** it's fast – _really really_ fast! 🚀
- **Customizable:** configure every aspect of your prompt.
- **Universal:** works on any shell, on any operating system.
- **Intelligent:** shows relevant information at a glance.
- **Feature rich:** support for all your favorite tools.
- **Easy:** quick to install – start using it in minutes.

<p align="center">
<a href="https://starship.rs/config/"><strong>Explore the Starship docs&nbsp;&nbsp;▶</strong></a>
</p>

<a name="🚀-installation"></a>

## 🚀 Installation

### Prerequisites

- A [Nerd Font](https://www.nerdfonts.com/) installed and enabled in your terminal (for example, try the [Fira Code Nerd Font](https://www.nerdfonts.com/font-downloads)).

### Step 1. Install Starship

Select your operating system from the list below to view installation instructions:

<details>
<summary>Android</summary>

Install Starship using any of the following package managers:

| Repository | Instructions           |
| ---------- | ---------------------- |
| [Termux]   | `pkg install starship` |

</details>

<details>
<summary>BSD</summary>

Install Starship using any of the following package managers:

| Distribution | Repository      | Instructions                      |
| ------------ | --------------- | --------------------------------- |
| **_Any_**    | **[crates.io]** | `cargo install starship --locked` |
| FreeBSD      | [FreshPorts]    | `pkg install starship`            |
| NetBSD       | [pkgsrc]        | `pkgin install starship`          |

</details>

<details>
<summary>Linux</summary>

Install the latest version for your system:

```sh
curl -sS https://starship.rs/install.sh | sh
```

Alternatively, install Starship using any of the following package managers:

| Distribution       | Repository              | Instructions                                                  |
| ------------------ | ----------------------- | ------------------------------------------------------------- |
| **_Any_**          | **[crates.io]**         | `cargo install starship --locked`                             |
| _Any_              | [conda-forge]           | `conda install -c conda-forge starship`                       |
| _Any_              | [Linuxbrew]             | `brew install starship`                                       |
| _Any_              | [Snapcraft]             | `snap install starship`                                       |
| Alpine Linux 3.13+ | [Alpine Linux Packages] | `apk add starship`                                            |
| Arch Linux         | [Arch Linux Community]  | `pacman -S starship`                                          |
| CentOS 7+          | [Copr]                  | `dnf copr enable atim/starship` <br /> `dnf install starship` |
| Fedora 31+         | [Fedora Packages]       | `dnf install starship`                                        |
| Gentoo             | [Gentoo Packages]       | `emerge app-shells/starship`                                  |
| Manjaro            |                         | `pacman -S starship`                                          |
| NixOS              | [nixpkgs]               | `nix-env -iA nixpkgs.starship`                                |
| Void Linux         | [Void Linux Packages]   | `xbps-install -S starship`                                    |

</details>

<details>
<summary>macOS</summary>

Install the latest version for your system:

```sh
curl -sS https://starship.rs/install.sh | sh
```

Alternatively, install Starship using any of the following package managers:

| Repository      | Instructions                            |
| --------------- | --------------------------------------- |
| **[crates.io]** | `cargo install starship --locked`       |
| [conda-forge]   | `conda install -c conda-forge starship` |
| [Homebrew]      | `brew install starship`                 |
| [MacPorts]      | `port install starship`                 |

</details>

<details>
<summary>Windows</summary>

Install the latest version for your system with the MSI-installers from the [releases section](https://github.com/starship/starship/releases/latest).

Install Starship using any of the following package managers:

| Repository      | Instructions                            |
| --------------- | --------------------------------------- |
| **[crates.io]** | `cargo install starship --locked`       |
| [Chocolatey]    | `choco install starship`                |
| [conda-forge]   | `conda install -c conda-forge starship` |
| [Scoop]         | `scoop install starship`                |
| [winget]        | `winget install --id Starship.Starship` |

</details>

### Step 2. Setup your shell to use Starship

Configure your shell to initialize starship. Select yours from the list below:

<details>
<summary>Bash</summary>

Add the following to the end of `~/.bashrc`:

```sh
eval "$(starship init bash)"
```

</details>

<details>
<summary>Cmd</summary>

You need to use [Clink](https://chrisant996.github.io/clink/clink.html) (v1.2.30+) with Cmd.
Create a file at this path `%LocalAppData%\clink\starship.lua` with the following contents:

```lua
load(io.popen('starship init cmd'):read("*a"))()
```

</details>

<details>
<summary>Elvish</summary>

Add the following to the end of `~/.elvish/rc.elv`:

```sh
eval (starship init elvish)
```

Note: Only Elvish v0.18+ is supported

</details>

<details>
<summary>Fish</summary>

Add the following to the end of `~/.config/fish/config.fish`:

```fish
starship init fish | source
```

</details>

<details>
<summary>Ion</summary>

Add the following to the end of `~/.config/ion/initrc`:

```sh
eval $(starship init ion)
```

</details>

<details>
<summary>Nushell</summary>

Add the following to the end of your Nushell env file (find it by running `$nu.env-path` in Nushell):

```sh
mkdir ~/.cache/starship
starship init nu | save ~/.cache/starship/init.nu
```

And add the following to the end of your Nushell configuration (find it by running `$nu.config-path`):

```sh
source ~/.cache/starship/init.nu
```

Note: Only Nushell v0.61+ is supported

</details>

<details>
<summary>PowerShell</summary>

Add the following to the end of your PowerShell configuration (find it by running `$PROFILE`):

```powershell
Invoke-Expression (&starship init powershell)
```

</details>

<details>
<summary>Tcsh</summary>

Add the following to the end of `~/.tcshrc`:

```sh
eval `starship init tcsh`
```

</details>

<details>
<summary>Xonsh</summary>

Add the following to the end of `~/.xonshrc`:

```python
execx($(starship init xonsh))
```

</details>

<details>
<summary>Zsh</summary>

Add the following to the end of `~/.zshrc`:

```sh
eval "$(starship init zsh)"
```

</details>

### Step 3. Configure Starship

Start a new shell instance, and you should see your beautiful new shell prompt.
If you're happy with the defaults, enjoy!

If you're looking to further customize Starship:

- **[Configuration](https://starship.rs/config/)** – learn how to configure Starship to tweak your prompt to your liking

- **[Presets](https://starship.rs/presets/)** – get inspired by the pre-built configuration of others

## 💭 Inspired By

Please check out these previous works that helped inspire the creation of starship. 🙏

- **[denysdovhan/spaceship-prompt](https://github.com/denysdovhan/spaceship-prompt)** – A ZSH prompt for astronauts.

- **[denysdovhan/robbyrussell-node](https://github.com/denysdovhan/robbyrussell-node)** – Cross-shell robbyrussell theme written in JavaScript.

- **[reujab/silver](https://github.com/reujab/silver)** – A cross-shell customizable powerline-like prompt with icons.

- **[starship/starship](https://github.com/starship/starship)** – A cross-shell customizable.

<p align="center">
    <br>
    <img width="100" src="https://raw.githubusercontent.com/starship/starship/master/media/icon.png" alt="Starship rocket icon">
</p>

## 📝 License

Copyright © 2022-present, [Starship Contributors](https://github.com/starship/starship/graphs/contributors).<br>
This project is [ISC](https://github.com/starship/starship/blob/master/LICENSE) licensed.

[alpine linux packages]: https://pkgs.alpinelinux.org/packages?name=starship
[arch linux community]: https://archlinux.org/packages/community/x86_64/starship
[chocolatey]: https://community.chocolatey.org/packages/starship
[conda-forge]: https://anaconda.org/conda-forge/starship
[copr]: https://copr.fedorainfracloud.org/coprs/atim/starship
[crates.io]: https://crates.io/crates/starship
[fedora packages]: https://src.fedoraproject.org/rpms/rust-starship
[freshports]: https://www.freshports.org/shells/starship
[gentoo packages]: https://packages.gentoo.org/packages/app-shells/starship
[linuxbrew]: https://formulae.brew.sh/formula/starship
[homebrew]: https://formulae.brew.sh/formula/starship
[macports]: https://ports.macports.org/port/starship
[nixpkgs]: https://github.com/NixOS/nixpkgs/blob/master/pkgs/tools/misc/starship/default.nix
[pkgsrc]: https://pkgsrc.se/shells/starship
[scoop]: https://github.com/ScoopInstaller/Main/blob/master/bucket/starship.json
[snapcraft]: https://snapcraft.io/starship
[termux]: https://github.com/termux/termux-packages/tree/master/packages/starship
[void linux packages]: https://github.com/void-linux/void-packages/tree/master/srcpkgs/starship
[winget]: https://github.com/microsoft/winget-pkgs/tree/master/manifests/s/Starship/Starship
