# Dot files for FE developers @ Unic

Stolen from all around the web :) Thanks Internet! ❤️

## Proceeding

### Preparation

Fork this repo, then:

- Configure your installation variables in `config/installation.sh`
- Configure your ZSH variables in `lib_zsh/frontend.zsh` (Config vars section)
- Configure your system adjustments in `lib_sh/system_adjustments_opinionated.sh`
- Go through `install.sh` and `lib_sh/system_adjustments_general.sh` and adapt it in case you don't like something
- Adapt the software you use with the `Brewfile`
- Add this repo as an upstream and use it from now on for your installs

You can also clone this repo in your "old" machine, then in the folder where this was cloned run the following in order to get the last state of your installed apps:

`brew bundle dump --describe --force`

This 👆will update the `Brewfile` with your current installed apps (9)if installed using Brew). Notice that this also requires you to have Homebrew and MAS installed (which you eventually have if you also run this in your old machine, back in the day you got it 😉).

> You should always review arbitrary code from the internet before running it on your machine with sudo power!
> You are responsible for everything this script does to your machine (see LICENSE)

### Installation

Run this 👇 on your new machine's terminal app and follow the instructions there.

```bash
git clone --recurse-submodules https://git.unic.com/scm/budc/frontend-dotfiles.git ~/.dotfiles && cd ~/.dotfiles && ./install.sh
```

When it finishes reboot the system when the prompt requires so. After the reboot you may see a message like the following in the terminal:

If you see this message 👇 type `y` and `enter`. If not ignore this and go on.

```bash
zsh compinit: insecure directories, run compaudit for list.
Ignore insecure directories and continue [y] or abort compinit [n]?
```

> Note: running install.sh is idempotent. You can run it again and again as you add new features or software to the scripts!

### Finalization

When it finishes, open iTerm or terminal and:

1. press `Command + ,` to open preferences.
1. Under Profiles > Colors, select "Load Presets" and choose the theme scheme defined in `instal.sh`. If it isn't there for some reason, import it from `~/.dotfiles/configs`
1. Eventually you may also need to select the `Hack` font and check the box for non-ascii font and set to `Roboto Mono For Powerline` or any other Powerline font (I've had mixed results for automating these settings -- I'd love a pull request that improves this)

---

## Restoring Dot files

If you have existing dot files for configuring git, zsh, vim, etc, these will be backed-up into `~/.dotfiles_backup/$(date +"%Y.%m.%d.%H.%M.%S")` and replaced with the files from this project. You can restore your original dot files by using `./restore.sh $RESTOREDATE` where `$RESTOREDATE` is the date folder name you want to restore.

> The restore script does not currently restore system settings--only your original dot files. To restore system settings, you'll need to manually undo what you don't like (so don't forget to fork, review, tweak)

---

## Settings

This project changes a number of settings and configures software on MacOS.

## License

This project is licensed under ISC. Please fork, contribute and share.

## Contributions

Contributions are always welcome! Open pull requests with explanatory comments.

## ¯\\_(ツ)_/¯ Warning / Liability

Neither Unic nor the creator(s) are responsible if your machine ends up in a state you are not happy with. If you are concerned, look at the code to review everything this will do to your machine :)
