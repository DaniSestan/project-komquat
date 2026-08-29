# Overview on Git Cliff

### Basic guidelines

#### Installing Git Cliff

Linux Fedora 44:
```
sudo dnf install cargo

cargo install git-cliff
```

#### Initializing the config

`git-cliff --init`

This command creates the git-cliff config; However, running other git-cliff commands in the project directory without initially running this command refers the git-cliff program to the git-cliff config in the default config folder, `~/.config/cliff.toml`.

#### Creating a CHANGELOG
```
git-cliff -o
#The filepath is set to CHANGELOG.md by default; the filepath does not need to be specified unless it's not the default
git-cliff -o <FILEPATH_OF_CHANGELOG>
```

Uploading changes to the CHANGELOG through git commits:
```
# When creating any new commits, the commit msg is prefixed with a desc of the type of commit -- e.g.,
{ message = "^feat", group = "<!-- 0 -->🚀 Features" },
{ message = "^fix", group = "<!-- 1 -->🐛 Bug Fixes" },
{ message = "^doc", group = "<!-- 3 -->📚 Documentation" },
{ message = "^perf", group = "<!-- 4 -->⚡ Performance" },
{ message = "^refactor", group = "<!-- 2 -->🚜 Refactor" },
{ message = "^style", group = "<!-- 5 -->🎨 Styling" },
{ message = "^test", group = "<!-- 6 -->🧪 Testing" },
{ message = "^chore\\(release\\): prepare for", skip = true },
{ message = "^chore\\(deps.*\\)", skip = true },
{ message = "^chore\\(pr\\)", skip = true },
{ message = "^chore\\(pull\\)", skip = true },
{ message = "^chore|^ci", group = "<!-- 7 -->⚙️ Miscellaneous Tasks" },
{ body = ".*security", group = "<!-- 8 -->🛡️ Security" },
{ message = "^revert", group = "<!-- 9 -->◀️ Revert" },
{ message = ".*", group = "<!-- 10 -->💼 Other" },
```

Git-cliff commit syntax:

`<GIT_COMMIT_TYPE_DESC>:<COMMIT_MSG>`

For any commits that don't fall under any of the pre-defined categories, create your own description.

Commit msg example:
`git commit -m "pentesting: running through issue ABC etc"`


##### Simplifying the CHANGELOG
You can use git cliff to only upload relevant changes to maintain a simpler CHANGELOG when necessary.
- selectively choose message categories from the complete list or comment out any commit categories if you create a 
custom template 
- set filter_commits to true in the cliff.toml to only log commits prefixed with the commit parsing message categories
file:
`filter_commits = true`

Commit categories:
```
    { message = "feat: yada yada yada", group = "<!-- 0 -->🚀 Features" },
    { message = "doc: yada yada yada", group = "<!-- 3 -->📚 Documentation" },
    { message = "perf: yada yada yada", group = "<!-- 4 -->⚡ Performance" },
    { message = "ref: yada yada yada", group = "<!-- 2 -->🚜 Refactor" },
    { message = "test:  yada yada yada", group = "<!-- 6 -->🧪 Testing" },
    { message = "other: yada yada yada", group = "<!-- 10 -->💼 Other" },
```

_[Internal note] Refer to ~/Work-Information/Work-Notes/Technical-Documentation/Technical-Processes/Versioning
-Workflows.md for information on how to use these commit categories_

___

### CHANGELOG customization

You can customize the CHANGELOG using the config template and git-cliff options.
#### Options/Arguments

Specify a config:
`--config <FILEPATH>`

Specify a repository:
`--repository <REPOSITORY_PATH>`

Specify git tag:
`--tag <TAG>`

Specify tag range:
```
# latest/newest commit:
--latest

# current tag; note the checked out branch must be tagged
--current

# unreleased commits:
--unreleased

# unreleased commits with a specified tag:
--unreleased --tag <TAG>
```

Specify git commit range:
```
# uses git's format for specifying ranges: https://git-scm.com/docs/git-range-diff
<STARTING_COMMIT_ID>..<ENDING_COMMIT_ID>
```

For other useful options, see: https://git-cliff.org/docs/usage/examples/

#### Editing the config
To edit what is uploaded to the changelog, it's easier to modify the git commits; refer to /home/dani/Work-Information/Work-Notes/Versioning/tools-and-pkgs/git/editing-git-commits.txt

It is possible to customize the default CHANGELOG template; however, this isn't necessary in most situations. To do so, edit the config as needed.
After customizing the CHANGELOG config, it can then be modified by appending specific changes, such as changes within a commit range or tagged commits.
```
# For instance, to specify a commit range, starting with the most recent commit:
git cliff HEAD~<RANGE_END_NUM> --prepend CHANGELOG.md
# e.g., `git cliff HEAD~1 --prepend CHANGELOG.md` creates a changelog with entries associated with changes made through the specified commit range
```

___

##### Sources
Getting Started | Git-cliff. git-cliff.org/docs.
