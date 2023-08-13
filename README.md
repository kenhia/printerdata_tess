# printerdata_tess
Printer data for Tess, a Voron Trident 300

This corresponds to my ~/printer_data/config directory.

## How-To
Unless otherwise noted, all of this is from a terminal where you are ssh'd into the Pi for your printer.

### Create .ssh key
1. `ssh-keygen` (hit enter repeatedly to get the defaults)
2. `cat ~/.ssh/id_rsa.pub` (copy this)
3. *on github* add your key https://github.com/settings/keys

### Git setup

1. `git config --global user.email "you@example.com"`
2. `git config --global user.name "Your Name"`
3. `git config --global init.defaultBranch main`

### Local Repo setup
1. `cd ~/printer_data/config`
2. *on github* Copy the [.gitignore](.gitignore)
3. `vi .gitignore` (or create the gitignore with your editor of choice)
    1. `A` to add
    2. `CTRL-SHIFT-V` to paste
    3. `:wq` to save and exit
4. `git init`
5. `git add .gitignore`
6. `git commit -m "starter gitignore"`
7. `git add *`
    * Ignore the hints
8. `git commit -m "<your comment here"`

### Create empty repository on GitHub
*This is on github*
1. Go to https://github.com/<your_username>?tab=repositories
2. Click "New"
3. Give the repository a name (I name my printers, so I'll be using "printerdata_<name>"
4. Give a description, optional (I use "Printer data for <name>, a Voron <model> <size>"
5. Make private if you choose...I like public so I can point others to my config
6. Don't add any of the other stuff, you want this empty!
    * You can add README/license/etc later if you want
7. Click "Create Repository"

> Note: the next step will be using the lines from the resulting screen, so if you like, copy the section "…or push an existing repository from the command line"

### Push your config to your new repository
*back to the ssh session on the pi*
1. `cd ~/printer_data/config` (probably already there, but just in case)
2. `git remote add origin git@github.com:<github_username>/<repo_name>.git`'
3. `git branch -M main`
4. `git push -u origin main`

**Congrats, if all the preceeding worked, you can now do normal git operations, push/pull/commit/etc from the Pi and have a copy of the config on GitHub**
