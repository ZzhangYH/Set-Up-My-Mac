# Set Up My Mac

> 🎊 Congrats! Opening up this page seems you've got a brand new Mac!  
> Now let's set this beast up for development environment just like what you what.
- [Set Up My Mac](#set-up-my-mac)
  - [Homebrew](#homebrew)
  - [iTerm2](#iterm2)
    - [Font](#font)
    - [Profile](#profile)
  - [Oh My Zsh](#oh-my-zsh)
  - [Powerlevel10k](#powerlevel10k)

## Homebrew
The _very first_ thing to do is definitely install [Homebrew](https://brew.sh) 🍺.

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
> Let iTerm do the rest of the work onwards 👇  

### Font
[Cascadia Code](https://github.com/microsoft/cascadia-code.git) is one of my favorite font for development environment. It is a fun new coding font with gorgeous coding experience.

Get `Cascadia Code` [here](https://github.com/microsoft/cascadia-code/releases). Download the package and open all font files to install them into the system.

### Profile
My customized profile for iTerm is included in the repository `./Terminal/iTermProfile.json`. Simply import it into iTerm and things are all done!

👉 __Note:__ The color theme `Atom One Dark` for both __Terminal__ and __iTerm__ is also available [here](https://github.com/nathanbuchar/atom-one-dark-terminal.git)! Check this out if the theme in profile above is not working.


## Oh My Zsh
[Oh My Zsh](https://ohmyz.sh) is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

**_Oh My Zsh will not make you a 10x developer...but you may feel like one._**

Run the following line to install `Oh My Zsh` now:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

💡 __Attention:__ A couple of zsh bundles by [zsh-users](https://github.com/zsh-users) to make your zsh more productive:
- [Zsh Syntax Highlighting](https://github.com/zsh-users/zsh-syntax-highlighting) (_Strongly Recommended_)
- [Zsh AutoSuggestions](https://github.com/zsh-users/zsh-autosuggestions)
- [Zsh Completions](https://github.com/zsh-users/zsh-completions)

    Do not forget to __activate__ those plugins in `~/.zshrc` after installing them:
    ```
    plugins=([plugins...] <Plugins you installed>)
    ```


## Powerlevel10k