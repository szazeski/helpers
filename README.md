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

`dockershell <partial-name>` will open a shell into the container that you typed
```
dockershell jenkins
82f3844a1234 Jenkins.1.89hjcgm4bacqs432x04skyfov jenkins/jenkins:lts
docker exec -it 82f3844a1234 bash
jenkins@82f3844a1234:/$
```
