merge-github-fork - Automated git commands for merging forks
============================================================

# Install

```sh
npm install merge-github-fork -g
```

or

> npm install -g https://github.com/HansHammel/MergeGithubFork.git

## Done manually ##

```bash
#clone someones repo
git clone https://github.com/myghname/somereponame.git
cd somereponame
```

# Usage

> merge-github-fork https://github.com/someghname/somereponame.git

Now (>=v1.1.0) supports urls like

	owner/repo#branch

or

	git://github.com/owner/repo.git#branch

Internally https://github.com/... urls are used!

Own server urls are not supported!

## The script essentially does this: ##

```bash
#merge forkes by gh-url
git remote add someghname https://github.com/someghname/somereponame.git#branch
git fetch someghname
git checkout master
git merge -s recursive -X ignore-all-space someghname/branch # while branch defaults to master
git status
git push origin master
```

### TODO
- [] add no push option
- [] add no test option (for version >2)
- [] color