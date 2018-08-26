<h1>GIT commands</h1>
<!-- =========================== -->
<h2>CONFIG PATH</h2>
<h4>/* global */</h4>
<code>~/.gitconfig</code>
<h4>/* local */</h4>
<code>.git/config</code>

<!-- =========================== -->
<h2>ADD PARAMS TO GLOBAL CONFIG</h2>
<code>git config --global user.name "userName"</code><br>
<code>git config --global user.email "userEmail"</code><br>
<code>git config --global core.editor "atom --wait"</code><br>
<code>git config --global core.autocrlf true</code><br>
<code>git config --list</code><br>
<code>cat ~/.gitconfig</code>
<!-- =========================== -->
<h2>WORKING WITH REMOTE/LOCAL REPO</h2>
<code>git remote -v</code>

<h4>/* initializing - add remote - push changes */</h4>
<code>git init</code><br>
<code>git add fileName;</code>
<code>git commit -m 'first commit'</code><br>
<code><b>git remote add origin <ref></b></code><br>
<code><b>git push</b></code>

<h4>/* clone repo */</h4>
<code>git clone remoteName branchName ref</code>

<h4>/* get changes from remote */</h4>
<code>git fetch;</code>
<code>git merge origin/master</code><br>

<code>git pull = git fetch + git merge origin/master</code><br>
<code>git pull --rebase = git pull + git rebase origin/master</code>

<h4>/* push changes to remote */</h4>
<code>git push</code><br>
<code>git push origin master</code><sup>doesn't depend on where is HEAD now</sup><br>
<code>git push origin src:<dest> </code><br>

<h4>/* delete local branch with git fetch */</h4>
<code>git fetch origin :foo</code>
<h4>/* delete remote branch with git push */</h4>
<code>git push origin :foo</code>

<!-- =========================== -->
<h2>WORKING WITH BRANCHES</h2>
<h4>/* branches list, create, rebase */</h4>
<code>git branch -v</code><br>

<code>git branch branchName</code><br>
<code>git branch branchName master^^2^</code><sup>working with rel refs</sup>
<br>
<code>git checkout -b branchName</code><br>

<code>git checkout -b branchName</code><br>
<code>git rebase mainBranch rebasingBranch</code>

<h4>/* moving HEAD */</h4>
<code>git checkout C1</code>
<code>git checkout branchName</code>

<h4>/* cancel changes locally */</h4>
<code>git reset</code><br>
<code>git reset --hard C1</code><sup>remove all changes from C2 state </sup><br>
<code>git reset --mixed C1</code><sup>default - there'll no changes in index</sup><br>
<code>fit reset --soft C1</code><sup>there'll the changes in index</sup><br>
<h4>/* cancel changes when opensource*/</h4>
<code>git revert</code>

<!-- =========================== -->
<h2>WORKING WITH COMMITS</h2>
<h4>/* create - change - log*/</h4>
<code>git commit -m 'message'</code><br>
<code>git commit --amend -m 'message'</code><br>
<code>git show commitHash</code><br>
<code>git diff</code><br>
<code>git log --oneline </code>

<h4>/* tags */</h4>
<code>git tag</code><br>
<code>git tag tagName commitHash</code><br>
<code>git describe ref</code><sup>output tag_numCommits_ghash</sup>

<h4>/* to get to commit use first 4 symbols of hash*/</h4>
<code>git checkout fe1p</code>

<h4>/* to get commits pointwise */</h4>
<code>git cherry-pick C1 C4 C6</code><br>
<code>git rebase -i HEAD~2</code><sup>rebase on HEAD~2, choose commits with editor, change the order, delete if no need</sup>

<!-- =========================== -->
<h2>COMMON</h2>
<code>git status</code><br>
<code>git add fileName</code><br>
<code>git add .</code><sup>to add all files to index</sup><br>
<code>git mv fileName<directory></code><br>
<code>git rm fileName</code><sup>delete file from index and fs</sup><br>
<code>git rm --cached fileName</code><sup>delete file from index, not fs</sup><br>

<code>git checkout commitHash fileName</code><sup>remove fileName changes to commitHash</sup><br>
<code>git reset fileName</code><sup>to remove file from index</sup><br>
