# My First Github Experience  - CLI

>Creating a new repository from commandline 

## CLI Tasks
* Step 1
  * Create a github repository named __py1__ using https
  * Initialize and add contents
* Step 2
  * Create further files __using echo__
  * Add added/modified files using __git add__
  * Add comment using __git commit -m__
  * Push  files to github using __git push__


## Create Repo using curl
> [curl](https://curl.haxx.se/) - Command line tools and libraries for URLs

~~~~

curl -u 'DSBUSA' https://api.github.com/user/repos -d '{"name":"py1"}'

~~~~

## Initialize from CLI

~~~~

mkdir py1
cd py

echo "# py1" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/DSBUSA/py1.git
git push -u origin master

~~~~

## Further Edits

~~~~

# Create new file
echo "# Hello World" > hello.md
echo "## This is nice" >> hello.md
echo "* Adding line 1 " >> hello.md
echo "* Adding line 2 " >> hello.md

# Add this to the list of commits
git add hello.md
git commit -m "Added Hello World file hello.md"
git push

# Follow proompts to enter user and password info

~~~~

## Add a folder
* Create __newfolder__
* Create file(s) inside __newfolder__
* Checkin __newfolder__ along with files.

~~~~
mkdir newfolder
echo "Folder 1 README" > newfolder/README.md
git add newfolder/README.md
git commit -m "Added newfolder"
git push
~~~~
 
## Add SSH access to repository using a key

~~~~

# Generate Keys
  eval $(ssh-agent -s)
  ssh-keygen -t rsa -b 4096 -C "DSBUSA@github.com"
  ssh-add ~/.ssh/id_rsa
  cat ~/.ssh/id_rsa.pub


# Put keys on the server

  curl -u DSBUSA:PASSWORD https://api.github.com/user/keys -d '{"title":"KEY_NAME", "key":"ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDaX6aUV9Pu7MzYjKwamWHJXKtIfXUnaXomwPYNoAedGvxNY9r20VPRHXz1RP8tKP6qB3P+lywlsSILdJ5T0SCc9ESC7fhTJeo/DqlYunvTbRpZrmWeZGJfJ4rZxuDXSdix+3ZxuilD6xl+uY+3QAfZeoeFDpsxt3bEhMvYzGQ6WsbP4oF+2pPXpmSGY4XmN8GdB6hsQKIg/26/paSdBTi6PgBy+BLXrXTHjEjIIawUaCmCXKTk2MJVkyPesEFj8kp8aLIXEERoll8d1aztuLf4SYdtoSSdfaIDo0GE+jJE/bdMqT/BKLKFifIOBY1SB+OCHyOLQQvGKwgZ5775wNGKm6rCCSBy3JMges8w0SXag+TEkc3eOqOYuVx0RJGljp1r4yU7kedK4OxP70vI8PquAKP9BcLdGQETrFUtCHtTXmzjEB1QbO5WlEh5By3W3SAbB0mqyh5TQvaqnOLqkyq28DP7Od/4JR90gTxkXRKCHAaCdTwGekAIni1bgscJ/GhESe2N6QF6z1GjLSFeJdH6L4cl56JLsHHDKxnHxIxDr0w10XFExQ87V5VnZ6vnq65UV1RoAXHKjEv99aAQEL5m8sGZLU3IiagbqEBSHGV80X0G3feTjsJ0BtxZxtFtsjGdSU/h7FcQElJJaGZ/LtGfr4jn/TvY3vVpYzW+U4eylw== DSBUSA@github.com"}'

  git push -u origin master

# Clone using SSH
  cd ~/proj/
  git clone git@github.com:DSBUSA/py1.git py3

~~~~

## Notes
* Git configuration information is stored in __${HOME}/.gitconfig__
  * Global configuration can be manipulated using __git config --global user.name DSBUSA__
  * Change __name__ in __gitconfig__  using __git config --global__ 
* Cache credentials using __git config --global credential.helper cache__
* Chain commands to say checkin steps.md over and over after modifications
  * __git add steps.md ; git commit -m "Updated steps"; git push__
