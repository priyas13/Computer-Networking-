
# Mergeable type work 

## Distributed setting
- I had setup virtual box with linux installed in it which I am considering as another machine or as another replica.
- Hence, my macbook pro and the linux machines are two replicas that we are trying to run in parallel. 

## API for setting up remote in Irmin
```
val remote_uri : string -> remote 
```
As we could see the string here represents the address of the remote machine. But there is a limitation in using that uri.
- remote_uri only supports GIT protocol for communication between remotes. We could not use any other protocols. All the remote located in the distributed setting must follow the git protocol for transmitting data. 
- I tried writing example where I was trying to use http protocol but it didn't work. 
- I tried writing example where I was trying to use ssh protocol but it didn't work.

## Git server
In this section, I want to discuss how to run a Git server?
- For running a Git server, we must decide which protocol we want our server to support. As I studied in the computer networking lectures, always a server must follow a protocol which describes the set of rules for the communication. 

## Git protocols
Git can use four distinct protocols to transfer data: Local, HTTP, Secure Shell (SSH) and Git. 
**Point to be noted here: Irmin remote setup only follows Git protocol**

For learning about all the protocols we could go to this [link](https://git-scm.com/book/en/v2/Git-on-the-Server-The-Protocols)

### Git Protocol
- It comes with Git and listens to a dedicated port (9418). 
- Git protocol is often the fastest network transfer protocol available. 
- For using this protocol, we must set-up a Git daemon.
- It uses the same data-transfer mechanism as the SSH protocol but without authentication and  encryption overhead.
- It also requires firewall access to port 9418.

### Git on the Server - Git Daemon 
- We want to set-up daemon (server) serving repository using the "Git" protocol.
- **GitHub** and **bitbucket** are some of the Git hosting services.

### STEPS
#### On the server machine (That is mac for me)
- made git as a user on my mac machine 
- mkdir repos (we should make a repos folder inside the git user)
- cd git/repos
- git daemon --export-all --base-path=.
- Now we need to make sure that remote login is enabled on the machine where we are tryng to set up the git server

  (Settings -> Sharing and ensure Remote Login is checked, "Remote Login:On")
  #### On another machine (That is Ubuntu for me)
- mkdir git 
- mkdir repos
- cd git/repos
- mkdir test
- cd git/repos/test
- git init 
- git remote add swarnpriya git://192.168.254.14:9418/test

Now from another machine, we can add my Mac as remote in git from withing a repo. (in my case it is Ubuntu) 
- git remote -v (checks the remotes we have set up)
- git clone git://192.168.254.14:9418/ocaml-irmin 
- ls
- ocaml-irmin will be present in the remote machine that is Ubuntu
- **Problems are git pull, git add is not working on the remote machine**
- Suppose I add a new readme file in the remote and want to pull that commit from the remote
git pull swarnpriya master (**this doesn't work**) (**but git clone worked and ocaml-irmin is present in the Ubuntu machine**)


