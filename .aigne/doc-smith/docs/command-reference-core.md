# Core Commands

The core commands are the foundation of `to-where-cli`, providing essential tools for managing your directory aliases. These commands allow you to add, list, remove, and clear all aliases from your configuration.

## add

The `add` command creates a new alias for a specified directory path. If no path is provided, it defaults to the current working directory. If no alias is given, it uses the name of the current directory.

### Usage

```sh
tw add [alias] [address]
```

### Arguments & Options

| Parameter | Description | Required |
|---|---|---|
| `alias` | A short, memorable name for the directory path. | No |
| `address` | The full or relative path to the directory. | No |
| `-f`, `--force` | Overwrites an existing alias if it already has the same name. | No |

### Examples

**1. Create an alias for the current directory**

If you are in `~/projects/my-cool-app`, this command creates an alias named `my-cool-app` pointing to it.

```sh
tw add
```

**2. Create an alias with a custom name for the current directory**

This creates an alias named `cool-app` pointing to the current directory.

```sh
tw add cool-app
```

**3. Create an alias for a specific path**

This command creates an alias `docs` that points to `~/documents/work`.

```sh
tw add docs ~/documents/work
```

**4. Overwrite an existing alias**

If the alias `docs` already exists, this command updates its path to a new location.

```sh
tw add docs /new/path/to/docs --force
```

---

## rm

The `rm` command removes one or more aliases from your configuration.

### Usage

```sh
tw rm [alias]
```

### Behavior

- **With an alias:** If you provide an alias, the command will remove that specific alias.
- **Without an alias:** If you run the command without an alias, it enters an interactive mode, presenting a list of all your aliases. You can select multiple aliases to remove at once.

### Arguments

| Parameter | Description | Required |
|---|---|---|
| `alias` | The name of the alias to be removed. | No |

### Examples

**1. Remove a specific alias**

This command removes the alias named `docs`.

```sh
tw rm docs
```

**2. Remove aliases interactively**

Running the command without arguments will display a prompt to choose which aliases to delete.

```sh
tw rm
```

This will trigger a prompt similar to the following, where you can use arrow keys and the spacebar to make selections:

```
? Select the alias to be deleted233 (Press <space> to select, <a> to toggle all, <i> to invert selection)
❯ ◯ docs => ~/documents/work => 5
  ◯ cool-app => ~/projects/my-cool-app => 12
```

---

## ls

The `ls` command (aliased as `list`) displays your saved aliases, their corresponding paths, and their usage count.

### Usage

```sh
tw ls [alias]
```

### Behavior

- **Without an alias:** Lists all saved aliases, sorted by the number of visits in descending order.
- **With an alias:** Displays the details for only the specified alias.

### Arguments

| Parameter | Description | Required |
|---|---|---|
| `alias` | The name of a specific alias to display. | No |

### Examples

**1. List all aliases**

```sh
tw ls
# or
tw list
```

The output will be formatted like this:

```
cool-app => ~/projects/my-cool-app => 12
docs => ~/documents/work => 5
```

**2. Display a specific alias**

This command shows the details for the `docs` alias only.

```sh
tw ls docs
```

---

## clean

The `clean` command completely removes all saved aliases from your configuration file. This action is irreversible.

### Usage

```sh
tw clean
```

### Options

To prevent accidental data loss, this command requires a confirmation flag to execute.

| Parameter | Description | Required |
|---|---|---|
| `-f`, `--force` | Confirms the action to delete all aliases. | Yes |

### Example

To permanently delete all your aliases, run:

```sh
tw clean --force
```