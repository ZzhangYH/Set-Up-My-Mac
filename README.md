# Set Up My Mac

> Congrats! 👏 \
> 🎊 Opening up this page seems you've got a brand new Mac! \
> 🥳 Now let's set this beast up for development environment just like what you what.

## Homebrew 🍺
The _very first_ thing to do is definitely install [Homebrew](https://brew.sh).

Homebrew is the Missing Package Manager for macOS, similar to those that are provided with mainstream Linux distributions. It installs **_the stuff you need that Apple didn’t_**.

Install `Homebrew` by running the following line in Terminal:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```


## Cascadia Code
[Cascadia Code](https://github.com/microsoft/cascadia-code.git) is one of my favorite font for development environment. It is a fun new coding font with gorgerous coding experience.

Install `Cascadia Code` [here](https://github.com/microsoft/cascadia-code/releases). Download the package and open all font files to install them into the system.


## iTerm2
Next, get [iTerm2](https://iterm2.com) ready for the ultimate command line experience.

iTerm2 is a terminal emulator for macOS that **_does amazing things_**. It is a replacement for Terminal and the successor to iTerm. It works on Macs with macOS 10.14 or newer. iTerm2 brings the terminal into the modern age with features you never knew you always wanted.

`iTerm2` package can be downloaded via their official website. Since we have installed Homebrew, just ask it to do it:
```
brew install --cask iterm2
```

My customized profile for iTerm is included in the repository `./Terminal/iTermProfile.json`. Simply import it into iTerm and things are all done!

👉 __Note:__ The color theme `Atom One Dark` for both __Terminal__ and __iTerm__ is also available [here](./Terminal/Atom%20One%20Dark%20Theme%20for%20Terminal/)! Check this out if the theme in profile above is not working.

> Let iTerm do the rest of the work onwards 👇

