# Creating a new repository from commandline

## Create REpo
curl -u 'USER' https://api.github.com/user/repos -d '{"name":"REPO"}'

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
