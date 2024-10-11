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

## Generating and Configuring SSH
1. `**ssh-keygen -t ed25519**` and hit [enter] or [return].
2. When it says, “`Enter file in which to save the key (/Users/yourname/.ssh/id_ed25519):`”, hit [enter] or [return].
3. When it says, “`Enter passphrase (empty for no passphrase):`”, hit [enter] or [return].
4. When it says, “`Enter same passphrase again:`”, hit [enter] or [return].
5. See the line that starts, “`Your public key has been saved in`” and ends in “`id_ed25519.pub`”? **That’s the file placed on the other server**.
6. If the key needs to be copied (like for github) **In a text editor, open “`id_ed25519.pub`”**.
    - **Windows?** Type `**notepad .ssh/id_ed25519.pub**`
    - **Mac?** Type `**open -e .ssh/id_ed25519.pub**`
    - It should be a single line like this:  
    `ssh-ed25519 AAAAC3Nz5AAAAIPIXO5icj4LUpqa2baqYQRmCZ1+NV4sBDr you@computer`
7. Otherwise type `**ssh-copy-id server2**` to copy the public key to the remote server. It will be located at `~/.ssh/authorized_keys`

## Cisco Commands

### Upgrading a Switch

### Resetting a Switch
