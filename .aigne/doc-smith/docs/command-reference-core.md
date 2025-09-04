# Core Commands

The core commands are the foundation of `to-where-cli`, providing the essential tools for managing your directory aliases. This section provides a detailed reference for adding, removing, listing, and clearing aliases.

---

## add

The `add` command creates a new alias for a specified directory path. If an alias or address is not provided, it will use the current working directory as a default.

### Usage

```bash
tw add [alias] [address] [options]
```

### Arguments & Options

| Parameter | Description                                                                                    | Required |
| :-------- | :--------------------------------------------------------------------------------------------- | :------- |
| `[alias]`   | The name to assign to the address. If omitted, the current directory's name is used.           | No       |
| `[address]` | The directory path to be aliased. If omitted, the current working directory (`cwd`) is used.     | No       |
| `-f, --force` | Overwrites an existing alias with the same name. Without this flag, the command will fail if the alias exists. | No       |

### Examples

**1. Create an alias for a specific path:**

This command creates an alias named `docs` that points to `~/documents/work`.

```bash
tw add docs ~/documents/work
```

**2. Create an alias for the current directory:**

If you are already in the target directory, you can omit the `address` argument.

```bash
cd ~/projects/my-app
tw add my-app
```

**3. Create an alias using defaults:**

If both `alias` and `address` are omitted, the command will use the current directory's name as the alias and its path as the address.

```bash
cd ~/projects/website
tw add
# This creates an alias 'website' pointing to the current path.
```

**4. Overwrite an existing alias:**

Use the `-f` or `--force` flag to update an existing alias to point to a new address.

```bash
tw add docs ~/documents/personal -f
```

---

## rm

The `rm` command removes one or more aliases from your configuration.

### Usage

```bash
tw rm [alias]
```

### Arguments

| Argument | Description                                                                                                                   | Required |
| :------- | :---------------------------------------------------------------------------------------------------------------------------- | :------- |
| `[alias]`  | The name of the alias to remove. If omitted, an interactive prompt will appear, allowing you to select multiple aliases for deletion. | No       |

### Examples

**1. Remove a specific alias:**

```bash
tw rm docs
```

**2. Remove multiple aliases interactively:**

Running the command without an alias will launch an interactive multi-select menu. Use the arrow keys to navigate, the spacebar to select, and enter to confirm.

```bash
tw rm
```

Upon execution, you will see a prompt similar to this:

```
? Select the alias to be deleted233 (Press <space> to select, <a> to toggle all, <i> to invert selection)
❯ ◯ my-app => /Users/user/projects/my-app => 15
  ◯ website => /Users/user/projects/website => 10
  ◯ docs => /Users/user/documents/personal => 5
```

---

## ls (or list)

The `ls` command (aliased as `list`) displays your saved aliases, their corresponding paths, and their usage frequency count. The list is sorted by the number of visits in descending order.

### Usage

```bash
tw ls [alias]
```

### Arguments

| Argument | Description                                                        | Required |
| :------- | :----------------------------------------------------------------- | :------- |
| `[alias]`  | The name of a specific alias to display. If omitted, all aliases are listed. | No       |

### Examples

**1. List all aliases:**

```bash
tw ls
```

Example output:
```
my-app => /Users/user/projects/my-app => 15
website => /Users/user/projects/website => 10
docs => /Users/user/documents/personal => 5
```

**2. Display details for a specific alias:**

```bash
tw ls my-app
```

Example output:
```
my-app => /Users/user/projects/my-app => 15
```

---

## clean

The `clean` command removes all saved aliases permanently. This is a destructive operation and requires a confirmation flag to prevent accidental data loss.

### Usage

```bash
tw clean [options]
```

### Options

| Option        | Description                                       | Required |
| :------------ | :------------------------------------------------ | :------- |
| `-f, --force` | Confirms the action to delete all aliases. This flag is mandatory for the command to execute. | Yes      |

### Examples

**1. Attempting to clean without confirmation:**

Running `tw clean` without the `--force` flag will result in an error message to ensure you are aware of the action.

```bash
tw clean
# Output: To make sure you know what you're doing, you must use '-f' or '--force' to empty
```

**2. Clearing all aliases:**

To proceed with deleting all aliases, use the `--force` flag.

```bash
tw clean --force
# All aliases will be removed.
```