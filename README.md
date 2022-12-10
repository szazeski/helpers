# cli helpers
helper bash scripts to make your cli a little easier


# Install
`git clone https://github.com/szazeski/helpers.git`
into a folder that is in your $PATH and you should be able to start using these commands from anywhere in your shell.

To add it to your path, edit your `.bash_rc` or `.zsh_rc` and add in `PATH=~/helpers:$PATH` then save and restart the shell.

You can also just save/copy individual bash files into a PATH folder and run `chmod +x <FILENAME>`


# Commands

`7zsha256` generates a sha256 file next to the file in the same format that the 7zip GUI tools generates. Can be used with globs and will skip over files that have already been processed. (expects system to already have `7z` installed)
```
7zsha256 *.iso
```

`adb-screenshot` will save a PNG of the device screenshot directly to the current working directory on the host machine (not the device)

`adb-type <value>` allows you to send keyboard presses to the connected android device
```
adb-type dkalsdu32jds#
```

`cleanpdf` runs ghostscript to re-encode the pdf. 

`dockerps` shows just the container name and status of all containers on the machine. This command is using the regular docker ps command with special formatting and some extra flags.


`dockershell <partial-container-name> <command-optional>` will open a shell into the container that you typed
```
dockershell jenkins sh
82f3844a1234 Jenkins.1.89hjcgm4bacqs432x04skyfov jenkins/jenkins:lts
docker exec -it 82f3844a1234 sh
jenkins@82f3844a1234:/$
```

`fasttrace <url>` will do a standard traceroute but with parameters to only make 1 request per hop, 50 max hops and only wait up to 1s for a reply to speed up the results.

`fix-audio-levels <filename>` will use ffmpeg to find the highest volume in the file, then applies audio gain to normalize it to 0db. Will save the old file incase it damages the file.


`sshlist` will show what ssh hosts your machine has configured, you can also add a `sshlist db` to search for entries with `db`

```
Host build-machine
Host db
Host db-backup
Host aws
```

`tree1` shows the tree from current directory with depth 1

`tree2` shows the tree from current directory with depth 2

`tree3` shows the tree from current directory with depth 3

`trimvideo <filename> <secondsToTrimOffFront>` allows you to remove the first x seconds of a video file, renames the current file to <filename>.old and places the new trimmed file with the old name. To revert just delete the trimmed file and remove the .old from the filename. 
