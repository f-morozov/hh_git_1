git clone https://github.com/f-morozov/hh_git_1.git
cd hh_git_1
vim A
vim B
git add A B
git commit -m "Add A and B"
git branch branch1
cd ..
git clone hh_git_1 hh_git_1b
cd hh_git_1b
git checkout -b branch1 origin/branch1
vim C
git add C
git commit -m "Add C"
git push origin branch1
cd ../hh_git_1
git checkout branch1
vim C
git add C
git commit -m "Modify C"
cd ../hh_git_1b
vim C
git add C
git commit -m "Modify C"
git fetch
git merge origin/branch1
vim C
git add C
git commit -m "Fix conflict in C"
cd ../hh_git_1
git remote add B ../hh_git_1b
git fetch B
git merge B/branch1
git push --all origin
