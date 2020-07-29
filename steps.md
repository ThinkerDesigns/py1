# Github experience from client machine CLI

>Creating a new repository from commandline 

## Tasks
* Step 1
  * Create a github repository named __py1__ using https
  * Initialize and add contents
* Step 2
  * Create further files __using echo__
  * Add added/modified files using __git add__
  * Add comment using __git commit -m__
  * Push  files to github using __git push__


## Create Repo using curl
curl -u 'DSBUSA' https://api.github.com/user/repos -d '{"name":"py1"}'

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
