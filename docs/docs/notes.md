# My notes 

A list of commands and notes to myself for reference.

## Powershell Commands

## Linux Commands
**Creating Aliases**

`
vim ~/.bashrc
`

Add the alias at the end of the file.

`
alias mycommand='cd ~/some/directory/'
`
save and exit.

Run the file to apply the new alias

`
. ~/.bashrc
`

### VIM Commands
`Esc` Switches from input mode to command mode. Press this key before typing any command.
``
`i or a` Switches from command mode to input mode at (i) or after (a) the current cursor position.

`o` Opens a new line below the current cursor position and goes to input mode.

`:wq` Writes the current file and quits.

`:q!` Quits the file without applying any changes. The ! forces the command to do its work. Add the ! only if you really know what you are doing.

:w filename Writes the current file with a new filename.

`dd` Deletes the current line and places the contents of the deleted line into memory.

`yy` Copies the current line.

`p` Pastes the contents that have been cut or copied into memory.

`v` Enters visual mode, which allows you to select a block of text using the arrow keys. Use d to cut the selection or y to copy it.

`u` Undoes the last command. Repeat as often as necessary.

`Ctrl-r` Redoes the last undo. (Cannot be repeated more than once.)

`gg` Goes to the first line in the document.

`G` Goes to the last line in the document.

`/text` Searches for text from the current cursor position forward.

`?text` Searches for text from the current cursor position backward.

`^` Goes to the first position in the current line.

`$` Goes to the last position in the current line.

`!ls` Adds the output of ls (or any other command) in the current file.

`:%s/old/new/g` Replaces all occurrences of old with new.

## Tmux Commands
`tmux` Create a new tmux session

`ctrl+b+s` Open current running sessions

`ctrl+b+%` Split Panes Vertically

`ctl+b+"` Split Panes Horizontally

`ctrl+b+:` Command Mode

`ctrl+b+ an arrow key` Navigate up down left and right

`ctrl+b+d` Detach from a session

`tmux ls` View sessions

`tmux attach` or `tumux a` Attache to previous session

`tmux a -t session_name` Attache to a particular session

To close a specific session, use `tmux list-sessions` to identify the session you want to kill, and then use `tmux kill-session -t targetSession` to kill that specific session.

kill all tmux processes with `pkill -f tmux`.




## Generating and Configuring SSH
1. `ssh-keygen -t ed25519` and hit [enter] or [return].
2. When it says, “`Enter file in which to save the key (/Users/yourname/.ssh/id_ed25519):`”, hit [enter] or [return].
3. When it says, “`Enter passphrase (empty for no passphrase):`”, hit [enter] or [return].
4. When it says, “`Enter same passphrase again:`”, hit [enter] or [return].
5. See the line that starts, “`Your public key has been saved in`” and ends in “`id_ed25519.pub`”? **That’s the file placed on the other server**.
6. If the key needs to be configured for something like github then **In a text editor, open “`id_ed25519.pub`”**.
    - Windows? Type `notepad .ssh/id_ed25519.pub`
    - Mac? Type `open -e .ssh/id_ed25519.pub`
    - It should be a single line like this:  
    `ssh-ed25519 AAAAC3Nz5AAAAIPIXO5icj4LUpqa2baqYQRmCZ1+NV4sBDr you@computer`
7. Copy the key to the remote server`**ssh-copy-id user@remoteserver**` It will be located at `~/.ssh/authorized_keys`

## SCP
To copy from local machine to remote host
`scp /from/path/file user@domain.com:/destination/path/`

To copy from remote host to local machine
`scp remote ip:/home/remote_dir/sample_example.txt home/Desktop`

To copy directory
`scp -r /from/path/dir user@domain.com:/destination/path/dir`

## Cisco Commands

### Upgrading a Switch

### Resetting a Switch
