# cli helpers
helper bash scripts to make your cli a little easier


# Install
`git clone https://github.com/steve-at-pixo/helpers.git`
into a folder that is in your $PATH and you should be able to start using these commands from anywhere in your shell.

You can also just save/copy individual bash files into a PATH folder and run `chmod +x <FILENAME>`


# Commands

`sshlist` will show what ssh hosts your machine has configured, you can also add a `sshlist db` to search for entries with `db`

```
Host build-machine
Host db
Host db-backup
Host aws
```

`dockershell <partial-name> <command-optional>` will open a shell into the container that you typed
```
dockershell jenkins sh
82f3844a1234 Jenkins.1.89hjcgm4bacqs432x04skyfov jenkins/jenkins:lts
docker exec -it 82f3844a1234 sh
jenkins@82f3844a1234:/$
```

`adb-type <value>` allows you to send keyboard presses to the connected android device
```
adb-type dkalsdu32jds#
```

`adb-screenshot` will save a PNG of the device screenshot directly to the current working directory

`dockerps` shows just the container name and status of all containers on the machine. This command is using the regular docker ps command with special formatting and some extra flags.

`fasttrace <url>` will do a standard traceroute but with parameters to only make 1 request per hop, 50 max hops and only wait up to 1s for a reply to speed up the results.

`trimvideo <filename> <secondsToTrimOffFront>` allows you to remove the first x seconds of a video file, renames the current file to <filename>.old and places the new trimmed file with the old name. To revert just delete the trimmed file and remove the .old from the filename. 
