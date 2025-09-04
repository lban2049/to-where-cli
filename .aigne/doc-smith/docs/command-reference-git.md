# Git Command

The `tw git` command provides a convenient way to quickly open various pages of your project's git repository (e.g., GitHub, GitLab) directly from your command line. It automatically detects your remote repository URL and navigates to the specified page in your default browser.

## Usage

To use the command, run it from within a directory that is a git repository.

```bash
tw git [options]
# or explicitly
tw git open [options]
```

If no options are provided, the command defaults to opening the main page of the current branch.

## Options

The `git` command supports a variety of options to navigate to different parts of a repository.

| Option | Alias | Description |
|---|---|---|
| `--actions` | `-a` | Opens the repository's Actions (CI/CD) page. |
| `--author` | | Opens the profile page of the last commit's author. |
| `--branch [branch]` | `-b` | Opens a specific branch page. Defaults to the current branch if no name is provided. |
| `--commit [hash]` | `-c` | Opens a specific commit page. Defaults to the latest commit if no hash is provided. |
| `--committer` | | Opens the profile page of the last commit's committer. |
| `--file <filePath>` | `-f` | Opens the page for a specific file on the current branch. |
| `--find` | | Opens the file finder/search page for the current branch. |
| `--first-commit` | | Opens the very first commit page of the repository. |
| `--issue` | `-i` | Opens the issues list page. |
| `--main` | `-m` | Opens the main branch page of the repository. |
| `--pull-request` | `-p` | Opens the pull request list page. |
| `--pull [branch]` | | Opens the page to create a new pull request, defaulting to the current branch. |
| `--release` | `-r` | Opens the releases page. |
| `--settings` | `-s` | Opens the repository settings page. |
| `--star` | | Opens the stargazers page. |

## Examples

Here are some practical examples of how to use the `tw git` command.

### Open the Repository Homepage

To open the repository's main page for the current branch, simply run the command without any options.

```bash
tw git
```

### View Issues and Pull Requests

Quickly navigate to the issues or pull requests list.

```bash
# Open the issues list
tw git --issue

# Open the pull requests list
tw git -p
```

### Create a New Pull Request

To open the 'New Pull Request' page for your current branch, use the `--pull` option.

```bash
tw git --pull
```

### Inspect Branches and Commits

View a specific branch or commit page.

```bash
# Open the page for the current branch
tw git -b

# Open a specific commit by its hash
tw git -c a1b2c3d4
```

### View a Specific File

Open a specific file in the repository on your current branch.

```bash
tw git -f "src/cli/git/open.ts"
```

---

Now that you are familiar with the `git` command, you may want to explore other ways to interact with online services. For more information, see the [Search Commands](./command-reference-search.md) documentation.