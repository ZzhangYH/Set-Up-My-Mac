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
  - [Setup SSH Key](#setup-ssh-key)
      - [Generate a new SSH key](#generate-a-new-ssh-key)
      - [Add your SSH key to the ssh-agent](#add-your-ssh-key-to-the-ssh-agent)
      - [Add your SSH Key to your account](#add-your-ssh-key-to-your-account)
      - [Test your SSH connection](#test-your-ssh-connection)

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

#### Font
[Cascadia Code](https://github.com/microsoft/cascadia-code.git) is one of my favorite font for development environment. It is a fun new coding font with gorgeous coding experience. Get `Cascadia Code` [here](https://github.com/microsoft/cascadia-code/releases). Download the package and open all font files to install them into the system.

#### Profile
My customized profile for iTerm is included in the repository `Default.json`. Simply import it into iTerm and things are all done!

👉 __Note:__ The color theme `Atom One Dark` for both __Terminal__ and __iTerm__ is also available [here](https://github.com/nathanbuchar/atom-one-dark-terminal.git)! Check this out if the theme in profile above is not working.


## Oh My Zsh
[Oh My Zsh](https://ohmyz.sh) is a delightful, open source, community-driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, themes, and a few things that make you shout...

> **_Oh My Zsh will not make you a 10x developer...but you may feel like one._**

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
[Powerlevel10k](https://github.com/romkatv/powerlevel10k) is a theme for Zsh. It emphasizes _speed_, _flexibility_ and _out-of-the-box experience_. It is always my first choice for zsh themes, so do try it out!

Install `Powerlevel10k` with __Oh My Zsh__:
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
👉 __Note:__ Set the theme in `~/.zshrc`:
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Reload zsh by `exec zsh` or simply restart the terminal, the __Configuration Wizard__ is supposed to automatically pop out. If not, type `p10k configure`  to access it right from your Terminal. Just follow the instructions shown on screen to complete the set up!

Additionally, Powerlevel10k comes with dozens of **_built-in high quality segments_**. Many of these segments get enabled by default while others can be manually enabled by opening `~/.p10k.zsh` and uncommenting them. You can enable as many segments as you like to enhance your command line experience.


## Setup SSH Key
With SSH keys, you can connect to GitHub or GitLab without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.

#### Generate a new SSH key
Open Terminal and run the line below, substituting your email address as a label.
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Follow the prompts and by default just `[Press Enter]` on every step:
```
> Generating public/private ALGORITHM key pair.
> Enter a file in which to save the key (/Users/YOU/.ssh/id_ALGORITHM): [Press enter]
> Enter passphrase (empty for no passphrase): [Press Enter]
> Enter same passphrase again: [Press Enter]
```

#### Add your SSH key to the ssh-agent
Start the ssh-agent in the background.
```
eval "$(ssh-agent -s)"
```

Add your SSH key to the ssh-agent.
```
ssh-add ~/.ssh/id_rsa
```

#### Add your SSH Key to your account
Copy your SSH key to clipboard.
```
pbcopy < ~/.ssh/id_rsa.pub
```

Then you can **_paste_** your SSH Key to your GitHub or GitLab account to enable authentication for Git operations over SSH.

#### Test your SSH connection
Open Terminal and run the following line.
```
ssh -T git@github.com
```
👉 __Note:__ Use the GitHub or GitLab **_instance URL_** you are trying to connect to. The instance URL can be found within the option __Clone with SSH__. For example, in `git@github.com:username/repository-space-name`, the prefix `git@github.com` is the instance URL.

Follow the instructions and type `yes`:
```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)? [yes]
```

Receiving a welcome with `Hi username!` or `@username!` means you are all done!





> To be continued...
