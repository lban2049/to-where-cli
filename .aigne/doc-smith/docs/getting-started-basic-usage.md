# Basic Usage

This guide provides a quick walkthrough of the core `to-where-cli` workflow. You'll learn how to add, use, list, update, and remove aliases through practical examples.

### Adding an Alias

To get started, you need to associate an alias with an address (like a URL or a local file path). The `tw add` command handles this.

For example, to create a shortcut named `home` for a GitHub profile:

```shell
tw add home https://github.com/skypesky
```

If you run `tw add` without specifying an alias or address, it will use the current working directory as the address and the directory's name as the alias.

```shell
# In a project folder named 'my-project'
tw add
# This creates an alias 'my-project' pointing to the current directory path.
```

### Opening an Address by Alias

Once an alias is set, you can open its corresponding address by simply typing `tw` followed by the alias name.

```shell
# This will open https://github.com/skypesky in your default browser
tw home
```

### Listing Aliases

To see a list of all your saved aliases and their corresponding addresses, use the `tw ls` command.

```shell
# List all saved aliases
tw ls
```

You can also check the address for a specific alias:

```shell
# Show the address associated with the 'home' alias
tw ls home
```

### Updating an Alias

To update an alias, simply use the `add` command again with the same alias name and the new address. This will overwrite the previous entry.

```shell
# Update the 'home' alias to point to a different repository
tw add home https://github.com/skypesky/leetcode-for-javascript
```

If you need to overwrite an existing alias without any prompts, you can use the `--force` or `-f` flag.

```shell
tw add home https://github.com/skypesky/new-repo --force
```

### Removing an Alias

When you no longer need an alias, you can remove it with the `tw rm` command.

```shell
# Remove the 'home' alias
tw rm home
```

If you run `tw rm` without specifying an alias, it will launch an interactive menu, allowing you to select one or more aliases to delete from a list.

```shell
# Run in interactive mode to select aliases for deletion
tw rm
```

This covers the fundamental operations for managing your shortcuts. For a complete list of commands and all their available options, please refer to the [Command Reference](./command-reference.md).