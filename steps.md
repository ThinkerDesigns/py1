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

## Notes
* Git configuration information is stored in __${HOME}/.gitconfig__
  * Global configuration can be manipulated using __git config --global user.name DSBUSA__
  * Change __name__ in __gitconfig__  using __git config --global__ 
* Cache credentials using __git config --global credential.helper cache__
* Chain commands to say checkin steps.md over and over after modifications
  * __git add steps.md ; git commit -m "Updated steps"; git push__
