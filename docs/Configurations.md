# Configurations

> _This part is mainly about configuring your command line and managing your __dotfiles__ across devices. It will then be unprecedentedly easy to synchronize your configurations on all your devices __ALL IN ONE__!_

The configuration files often appear as a `.fileName` file or a `.folderName` folder your root directory. They keep track of your settings of various applications or system functionalities so that you can customize your machine as freely as you like. 

However, those files are, _by default_, normally hidden by the system.

Simply press `Command+Shift+.` to show and hide them on macOS, or run this command in Terminal to get a list of them with detailed access permissions and modification dates:

```
ls -la
```

The way I use to keep my dotfiles updated across all devices is utilizing **_Symbolic Links_** (also called [symlinks](https://www.freecodecamp.org/news/symlink-tutorial-in-linux-how-to-create-and-remove-a-symbolic-link/)) and **_Git Repositories_**. We can make symlinks of our config files from our repo to the system root folder so that everywhere will be synced wherever changes take place.

## List of config files included

_These files are subject to updates_ \
_(Please add new files down below and create symlink commands for them)._

- `.zshrc` - Zsh configurations
- `.p10k.zsh` - Powerlevel10k configurations
- `.gitconfig` - Git configurations

💡 __Attention:__ Remember to delete the existing or newly-created ones first before making symlinks!

```
rm <fileName>
```

All config files are updated in the directory `../.dotfiles/`. Create the symlinks with the following commands.

```
ln -s ~/Developer/Set-Up-My-Mac/.dotfiles/.zshrc ~/.zshrc
ln -s ~/Developer/Set-Up-My-Mac/.dotfiles/.p10k.zsh ~/.p10k.zsh
ln -s ~/Developer/Set-Up-My-Mac/.dotfiles/.gitconfig ~/.gitconfig
```

👉 __Note:__ Every time you edit those configurations, **_DO NOT FORGET_** to `push` and `pull` this repository to sync those modifications across your devices.
