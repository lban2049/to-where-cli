# Core Commands

The core commands are the foundation of `to-where-cli`, providing all the necessary tools to manage your directory aliases. You can use them to add, remove, list, and clear your shortcuts.

---

## add

The `add` command creates a new alias for a specified directory path. If no path is provided, it defaults to the current working directory.

### Usage

```bash
tw add [alias] [address]
```

### Arguments & Options

| Parameter | Description | Required |
|---|---|---|
| `alias` | The name of the alias you want to create. If omitted, the name of the current directory is used. | No |
| `address` | The directory path you want to associate with the alias. If omitted, the current working directory is used. | No |
| `-f`, `--force` | Overwrites an existing alias if it has the same name. | No |

### Examples

**1. Create an alias for the current directory**

If you are in `/Users/dev/my-project`, this command creates an alias named `my-project` pointing to it.

```bash
tw add
```

**2. Create a named alias for a specific directory**

```bash
tw add my-app /Users/dev/my-application
```

**3. Overwrite an existing alias**

If the alias `my-app` already exists, you must use the `--force` flag to update it.

```bash
tw add my-app /Users/dev/new-path --force
```

Without the `--force` flag, you will receive an error:

```
Alias my-app already exists, you can use '-f' or '--force' to overwrite it
```

---

## rm

The `rm` command removes one or more aliases.

### Usage

```bash
tw rm [alias]
```

### Arguments

| Parameter | Description | Required |
|---|---|---|
| `alias` | The name of the alias to be deleted. | No |

### Behavior

- **With an alias:** If you provide an alias name, the command will delete that specific alias.
- **Without an alias:** If you run the command without an alias, it will launch an interactive prompt, allowing you to select multiple aliases to delete.

### Examples

**1. Remove a specific alias**

```bash
tw rm my-app
```

Expected output:

```
Alias my-app has been removed
my-app => /Users/dev/new-path => 0
```

**2. Remove aliases using interactive mode**

Run the command without any arguments to enter a selection prompt.

```bash
tw rm
```

This will display a list where you can use the arrow keys and spacebar to select aliases for deletion:

```
? Select the alias to be deleted233
  Instructions: 
    ↑/↓: Highlight option
    ←/→/[space]: Toggle selection
    a: Toggle all
    [enter]: Done
❯ ◯ project-a => /path/to/project-a => 10
  ◯ project-b => /path/to/project-b => 5
  ◯ project-c => /path/to/project-c => 2
```

---

## ls

The `ls` command (aliased as `list`) displays your saved aliases, their corresponding paths, and their visit counts.

### Usage

```bash
tw ls [alias]
tw list [alias]
```

### Arguments

| Parameter | Description | Required |
|---|---|---|
| `alias` | The name of a specific alias to display. If omitted, all aliases will be listed. | No |

### Examples

**1. List all saved aliases**

The list is sorted by the number of visits in descending order.

```bash
tw ls
```

Expected output:

```
project-a => /path/to/project-a => 10
project-b => /path/to/project-b => 5
project-c => /path/to/project-c => 2
```

**2. Display a specific alias**

```bash
tw ls project-b
```

Expected output:

```
project-b => /path/to/project-b => 5
```

---

## clean

The `clean` command removes all saved aliases. This action is irreversible and requires a confirmation flag.

### Usage

```bash
tw clean
```

### Options

| Parameter | Description | Required |
|---|---|---|
| `-f`, `--force` | Confirms the action to delete all aliases. This is a required safeguard. | Yes |

### Examples

**1. Attempting to clean without the force flag**

Running `clean` without `--force` will result in an error to prevent accidental data loss.

```bash
tw clean
```

Expected output:

```
To make sure you know what you're doing, you must use '-f' or '--force' to empty
```

**2. Clearing all aliases**

Use the `--force` flag to proceed with the deletion.

```bash
tw clean --force
```

After executing, all aliases will be permanently removed.