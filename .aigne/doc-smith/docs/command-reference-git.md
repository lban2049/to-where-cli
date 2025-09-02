# Git Command

The `tw git` command provides a convenient way to quickly open various pages of your project's hosted git repository (like GitHub, GitLab, etc.) directly from your terminal. It reads your local repository's remote URL and constructs the correct address for common destinations like issues, pull requests, and specific branches.

This eliminates the need to manually find your repository in the browser and navigate through its interface.

## How It Works

The command follows a simple process to open the correct web page:

```d2
direction: down
shape: sequence_diagram

Developer
Terminal
"to-where-cli"
"Git Host (e.g., GitHub)"

Developer -> Terminal: "Runs `tw git --issue`"
Terminal -> "to-where-cli": "Executes command"
"to-where-cli" -> "to-where-cli": "Reads .git/config to find remote URL"
"to-where-cli" -> "to-where-cli": "Constructs URL: https://github.com/user/repo/issues"
"to-where-cli" -> "Git Host (e.g., GitHub)": "Opens URL in default browser"

```

## Usage

The `git` command is the default subcommand, so you can use `tw git [options]`.

```bash
tw git [options]
```

If no options are provided, the command defaults to opening the main page for the current branch of your repository.

## Options

Here is a comprehensive list of all available options for the `tw git` command:

| Option | Alias | Description |
|---|---|---|
| `--actions` | `-a` | Opens the repository's Actions/CI page. |
| `--author` | | Opens the profile page of the last commit's author. |
| `--branch [branch]` | `-b` | Opens a specific branch page. If `[branch]` is omitted, it defaults to the current branch. |
| `--commit [hash]` | `-c` | Opens a specific commit page. If `[hash]` is omitted, it defaults to the latest commit. |
| `--committer` | | Opens the profile page of the last commit's committer. |
| `--file <filePath>` | `-f` | Opens the page for a specific file in the current branch. |
| `--find` | | Opens the file search page for the current branch. |
| `--first-commit` | | Opens the page for the very first commit in the repository's history. |
| `--issue` | `-i` | Opens the issues list page. |
| `--main` | `-m` | Opens the main page of the repository's default branch. |
| `--pull-request` | `-p` | Opens the pull request list page. |
| `--pull [branch]` | | Opens the page to create a new pull request. Defaults to the current branch if `[branch]` is not specified. |
| `--release` | `-r` | Opens the releases page. |
| `--settings` | `-s` | Opens the repository settings page. |
| `--star` | | Opens the repository's stargazers page. |

## Examples

### Open Current Branch

Opens the repository page for your current working branch. This is the default action if no options are provided.

```bash
tw git
```

### Open Issues Page

Navigates directly to the list of issues for the repository.

```bash
tw git -i
```

### Open Pull Requests

Opens the list of all pull requests.

```bash
tw git -p
```

### Create a New Pull Request

Opens the page to create a new pull request, using the current branch as the head branch.

```bash
tw git --pull
```

### View a Specific Commit

Opens the page for a specific commit hash.

```bash
tw git -c a1b2c3d4
```

### View a Specific File

Navigates to the specified file within the repository.

```bash
tw git -f "src/cli/git/index.ts"
```

---

After mastering repository navigation, learn how to perform web searches directly from your terminal with the [Search Commands](./command-reference-search.md).
