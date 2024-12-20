# Set Up My Mac

> _Congrats! Opening up this page seems you've got a brand new Mac!  
> Now let's set this beast up for development environment just like what you what._

- [Command Line](#command-line)
  - [Command Line Tools](#command-line-tools)
  - [AutoBoot](#autoboot)
  - [Hushlogin](#hushlogin)
- [Homebrew](#homebrew)
- [iTerm2](#iterm2)
  - [Fonts](#fonts)
  - [Profiles](#profiles)
- [Oh My Zsh](#oh-my-zsh)
- [Powerlevel10k](#powerlevel10k)

You can setup an SSH key to clone this repo from GitHub with SSH. See [SetupSSH.md](docs/SetupSSH.md). \
To manage your configuration files, refer to [Configurations.md](docs/Configurations.md).

## Command Line

### Command Line Tools

The _very first_ thing to do is definitely install Apple's `Command Line Tools`, which is the prerequisites for all development setups.

```
xcode-select --install
```

### AutoBoot

Apple implements the new feature **_Boot on Lid Open_** in mac, starting the computer when opening up the lid, which I find really annoying. Pressing the start key is what I prefer. To disable this feature, run this line with your login password:

```
sudo nvram AutoBoot=%00
```

### Hushlogin

Run the following command to create a `.hushlogin` file in your root directory to **_prevent getting the login banner_** `Last Login: blah blah blah` every time you start a new terminal session.

```
touch .hushlogin
```

## Homebrew

🍺 [Homebrew](https://brew.sh) is a **_must_**.

Homebrew is the Missing Package Manager for macOS, similar to those that are provided with mainstream Linux distributions. It installs **_the stuff you need that Apple didn’t_**.

Install `Homebrew` by running the following line in Terminal:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## iTerm2

Next, get [iTerm2](https://iterm2.com) ready for the ultimate command line experience.

iTerm2 is a terminal emulator for macOS that **_does amazing things_**. It is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.14 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.

`iTerm2` package can be downloaded via their official website. Since we have installed Homebrew, just ask it to do it for you with this line:

```
brew install --cask iterm2
```

> _Let iTerm do the rest of the work onwards_ 👇  

### Fonts

- [`Cascadia Code`](https://github.com/microsoft/cascadia-code)
- [`Consolas`](https://learn.microsoft.com/en-us/typography/font-list/consolas)
- [`Fira`](https://github.com/mozilla/Fira)
- [`MesloLGS NF`](https://github.com/romkatv/powerlevel10k-media)
- [`Source Code Pro`](https://github.com/adobe-fonts/source-code-pro)

Some fonts are included under `src/`, while you can quickly install them using HomeBrew:

```
# brew tap homebrew/cask-fonts # New version of brew no longer requires this command (deprecated).
brew install font-cascadia-code font-fira-mono font-fira-sans font-meslo-for-powerlevel10k font-source-code-pro
```

### Profiles

My customized profile for iTerm is included in the repository `src/Default.json`. Simply import it into iTerm and things are all done!

I also attached two color presets (themes) for iTerm, which is also under `src/` ending with `.itermcolors`
- **One Dark**, my enduring loved color theme for all IDEs.
- **Night Owl**, newly found refreshing!

## Oh My Zsh

[Oh My Zsh](https://ohmyz.sh) is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

> **_Oh My Zsh will not make you a 10x developer...but you may feel like one._**

Run the following line to install `Oh My Zsh` now:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

💡 __Attention:__ A couple of zsh bundles by [zsh-users](https://github.com/zsh-users) to make your zsh more productive:
- [Zsh Syntax Highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

  ```
  git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
  ```

- [Zsh AutoSuggestions](https://github.com/zsh-users/zsh-autosuggestions)
  
  ```
  git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
  ```

Do not forget to __activate__ those plugins in `~/.zshrc` after installing them:

```
plugins=([plugins...]
         zsh-syntax-highlighting
         zsh-autosuggestions
)
```

## Powerlevel10k

[Powerlevel10k](https://github.com/romkatv/powerlevel10k) is a theme for Zsh. It emphasizes _speed_, _flexibility_ and _out-of-the-box experience_. It is always my first choice for zsh themes, so do try it out!

Install `Powerlevel10k` with __Oh My Zsh__:

```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

👉 __Note:__ Set the theme in `~/.zshrc`:

```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Reload zsh by `exec zsh` or simply restart Terminal, the __Configuration Wizard__ is supposed to automatically pop out. If not, type `p10k configure`  to access it right from your Terminal. Just follow the instructions shown on screen to complete the set up!

Additionally, Powerlevel10k comes with dozens of **_built-in high quality segments_**. Many of these segments get enabled by default while others can be manually enabled by opening `~/.p10k.zsh` and uncommenting them. You can enable as many segments as you like to enhance your command line experience.

---

_To be continued..._
