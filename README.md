# Set Up My Mac

> _Congrats! Opening up this page seems you've got a brand new Mac!  
> Now let's set this beast up for development environment just like what you what._

- [Command Line](#command-line)
  - [Command Line Tools](#command-line-tools)
  - [AutoBoot](#autoboot)
  - [Hushlogin](#hushlogin)
- [Homebrew](#homebrew)
- [iTerm2](#iterm2)
  - [Font](#font)
  - [Profile](#profile)
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

### Font

[Cascadia Code](https://github.com/microsoft/cascadia-code.git) is one of my favorite font for development environment. It is a fun new coding font with gorgeous coding experience. Get `Cascadia Code` [here](https://github.com/microsoft/cascadia-code/releases). Download the package and open all font files to install them into the system.

### Profile

My customized profile for iTerm is included in the repository `src/Default.json`. Simply import it into iTerm and things are all done!

The color theme `Atom One Dark` for both __Terminal__ and __iTerm__ is also available [here](https://github.com/nathanbuchar/atom-one-dark-terminal.git)! Check this out if the theme in profile above is not working.

👉 __Note:__ I have also included both copies of the __theme and font__ within the repository under `src/Atom_One_Dark_Theme` and `src/Cascadia_Code`. _Update them if there are newer releases!_

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
         Zsh Syntax Highlighting
         Zsh AutoSuggestions
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
