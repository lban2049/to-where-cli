# Git Command

The `tw git` command provides a convenient way to quickly open your project's remote repository pages directly from your terminal. It automatically detects your remote Git URL and opens the relevant page in your default web browser. The default subcommand is `open`, so `tw git` is an alias for `tw git open`.

This command functions by reading the remote origin URL from your local Git configuration. It then constructs the appropriate URL for various repository pages—such as issues, pull requests, or specific files—based on the provided options. If no options are specified, it defaults to opening the main page for the current branch.

## Usage

```bash
tw git [options]
# or
tw git open [options]
```

## Workflow

The following diagram illustrates how the `tw git` command processes a request and opens the corresponding repository page.

```d2
direction: down

Terminal: {
  shape: rectangle
  User: {
    shape: person
  }
  CLI: {
    label: "tw git --issue"
  }
  User -> CLI: "Executes command"
}

"to-where-cli": {
  shape: package
  grid-columns: 1

  "Git-Command-Parser": {
    label: "Git Command Parser"
    shape: rectangle
  }

  "Git-Util": {
    label: "Git Remote URL Util"
    shape: rectangle
  }

  "URL-Builder": {
    label: "URL Builder"
    shape: rectangle
  }

  "System-Open": {
    label: "OS Open Command"
    shape: rectangle
  }

  "Git-Command-Parser" -> "Git-Util": "Requests remote URL"
  "Git-Util" -> "Git-Command-Parser": "Returns base URL"
  "Git-Command-Parser" -> "URL-Builder": "Provides base URL & option"
  "URL-Builder" -> "System-Open": "Passes final URL"
}

"Local-Filesystem": {
  label: "Local Filesystem"
  shape: cylinder
  "git-config": {
    label: ".git/config"
  }
}

Browser: {
  shape: rectangle
  "GitHub-Issues-Page": {
    label: "GitHub Issues Page"
  }
}

Terminal -> "to-where-cli"."Git-Command-Parser"
"to-where-cli"."Git-Util" -> "Local-Filesystem": "Reads config"
"to-where-cli"."System-Open" -> Browser: "Opens URL"
```

## Options

| Option | Alias | Description |
|---|---|---|
| `--actions` | `-a` | Open the repository's Actions page. |
| `--author` | | Open the profile page of the last commit's author. |
| `--branch [branch]` | `-b` | Open a specific branch page. Defaults to the current branch if no branch name is provided. |
| `--commit [hash]` | `-c` | Open a specific commit page. Defaults to the latest commit if no hash is provided. |
| `--committer` | | Open the profile page of the last commit's committer. |
| `--file <filePath>` | `-f` | Open the page for a specific file in the repository. |
| `--find` | | Open the file search page for the current branch. |
| `--first-commit` | | Open the very first commit page of the repository. |
| `--issue` | `-i` | Open the issues list page. |
| `--main` | `-m` | Open the main repository page (root). |
| `--pull-request` | `-p` | Open the pull requests list page. |
| `--pull [branch]` | | Open the page to create a new pull request. The source branch defaults to the current branch. |
| `--release` | `-r` | Open the releases page. |
| `--settings` | `-s` | Open the repository settings page. |
| `--star` | | Open the stargazers page. |

## Examples

### Open the Current Branch Page

If you are on a branch named `feature/new-ui`, running the command without any options will open the page for that branch.

```bash
tw git
```

### Open the Issues List

To quickly navigate to the issues page for the repository.

```bash
tw git --issue
# or using the alias
tw git -i
```

### Create a New Pull Request

This command opens the 'New Pull Request' page in your browser, pre-populating the source branch with your current branch.

```bash
tw git --pull
```

To specify a different source branch for the pull request:

```bash
tw git --pull my-feature-branch
```

### Open a Specific File

To view a specific file in the repository on its default branch.

```bash
tw git -f "src/cli/git/open.ts"
```

### View a Specific Commit

Provide a commit hash to open its details page directly.

```bash
tw git -c a1b2c3d4e5f6
```

---

The `git` command streamlines your development workflow by reducing the need to manually navigate repository websites. For other direct actions from your terminal, see the [Search Commands](./command-reference-search.md).