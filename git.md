#### SSH key
```sh
# generate key
ssh-keygen -t ssh-rsa -b 4096 -C "name@github.com"
ssh-keygen -t rsa -b 4096 -C "name@github.com"
# start ssh agent
ssh-agent -s
# list of all keys stored
ssh-add -l
# add key
ssh-add #<generated key>
# test connection
ssh -T git@github.com
```
#### Store Settings
```sh
git config user.name "GitHub Name"
git config user.email "name@example.com"
git config --global user.name "GitHub Name"
git config --global user.email "name@example.com"
git config --global credential.helper cache
# set default commit editor
git config core.editor "vim" or "path of executable file"
```
#### Commit without setting user.email and user.name
```sh
git -c user.name='Paul Draper' -c user.email='my@email.org' commit -m '...'
git config alias.ccommit "-c user.name='Name' -c user.email='my@email.org' commit -S -m"
```
#### Pull From Another Branch
```sh
git pull origin dev
```
#### Checkout only one file
```sh
git checkout origin/branch_name -- path/to/app.js
```
#### Remove from git remote branch
```sh
git rm --cached file1.txt
git commit -m "remove file1.txt"
git push origin branch_name
```
#### Create empty branch on GitHub
```sh
git checkout --orphan branch_name
```
#### git-remote
```sh
git remote add origin #<YOUR-REPO-URL>
git remote set-url origin #<YOUR-REPO-URL>
git remote remove origin
```
#### Remove commit from remote
```sh
git reset --hard HEAD~1
git push --force
```
#### git DELETE Branch
```sh
git checkout -b release master    # Create and switch to the release branch
git push -u origin release        # Push the release branch to the remote and track it
git branch -d master              # Delete local master
git push --delete origin master   # Delete remote master
git remote prune origin           # Delete the remote tracking branch
```
#### cherry-pick
```sh
git cherry-pick A..B
```
#### clone from specific branch
```sh
git clone --branch branch_name https://github.com/USERNAME/REPOSITORY.git
```
#### GPG
```sh
# lesser option
gpg --gen-key
# for non expire key
gpg --full-gen-key

# List all GPG public keys.
gpg --list-keys --keyid-format long

# List all GPG secret keys.
gpg --list-secret-keys --keyid-format long

# The syntax is: gpg --armor --export KEY-ID
gpg --armor --export 0E6198DFB2D67A26

# Deletes GPG secret key.
gpg --delete-secret-key #<EMAIL>

# Deletes GPG public key.
gpg --delete-key #<EMAIL>

# GPG export
gpg -a --export-secret-keys [key-id] > key.asc
gpg --export-secret-keys -a keyid > my_private_key.asc
gpg --export -a keyid > my_public_key.asc

# GPG import
gpg --import key.asc
gpg --import my_private_key.asc
gpg --import my_public_key.asc

# verify gpg keys
gpg --edit-key foo@bar.com
#>Type in the command `trust` and it will prompt you:

# The syntax is git config user.signingkey KEY-ID
git config user.signingkey #<KEY>

# Set git config gpg.program
git config gpg.program gpg
git config gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"

# Git sign commit
git commit -S -m "Sign Commit"
```
#### Search in Git
```sh
git rev-list --all | xargs git grep -F '<PATTERN>'
```
#### Viewing other branch files
```sh
git show main:<path/to/file>
```
#### current state of HEAD:
```sh
cat .git/HEAD
```
#### backup of untracked files
```sh
git ls-files --others --exclude-standard -z | xargs -0 tar rvf ~/<file-name>.zip
```
####  Optimize your repository
```sh
git gc --prune=now --aggressive
```
#### Counting commits
```sh
git rev-list --count branch_name
```
#### Auto-correction in Git
```sh
git config help.autocorrect 1
git config --global help.autocorrect 1
```
#### Graphical alternative
```sh
git gui
# Open GUI tool.
git citool
# Gitk user interface.
gitk
```
#### zip your entire branch
```sh
git archive --format zip --output file-name.zip branch_name
```
#### Amending the most recent commit message
```sh
git commit --amend -m "New commit message"
```
#### Resolution tools to resolve merge conflicts
```sh
git config merge.tool npp
git mergetool --tool=npp
git mergetool -t npp
git config mergetool.npp.path "<executable-path>.exe"
git config mergetool.sublime.cmd "subl -w \$MERGED"
git config mergetool.sublime.trustExitCode false 
git config merge.tool sublime
git mergetool -y
```