# Creating a new repository from commandline

## Task
* Create a github repository named __py1__ using https
* Initialize and add contents


## Create REpo
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
