# svn

> Subversion command-line client tool.
> More information: <https://subversion.apache.org>.

- Check in only certain files, specified in a file

`svn ci -m {{commit_log_message}} --targets {{files_to_change.txt}}`

- Resolve a ! next to something in svn status. Means it was moved without using svn rm .. 

svn revert {{file}}
svn delete {{file}}

- Check out a working copy from a repository:

`svn co {{url/to/repository}}`

- Bring changes from the repository into the working copy:

`svn up`

- Put files and directories under version control, scheduling them for addition to repository. They will be added in next commit:

`svn add {{PATH}}`

- Send changes from your working copy to the repository:

`svn ci -m {{commit_log_message}} [{{PATH}}]`

- Display changes from the last 10 revisions, showing modified files for each revision:

`svn log -vl {{10}}`

- Show detailed help:

`svn help`
