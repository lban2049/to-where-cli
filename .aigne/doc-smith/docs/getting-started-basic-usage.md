# Basic Usage

Once you have `to-where-cli` installed, you can start managing your address aliases with a few simple commands. This guide will walk you through the core workflow: adding, opening, listing, updating, and removing aliases.

### Add an Alias

To save a new address, use the `tw add` command. You need to provide a short, memorable `alias` and the full `address` you want to save.

```shell
tw add home https://github.com/skypesky
```

**Pro Tip:** If you run `tw add` without an address, it will use your current working directory. If you also omit the alias, it will use the directory's name as the alias.

```shell
# In folder /Users/dev/my-project
tw add my-proj # Creates an alias 'my-proj' for the current directory

# In folder /Users/dev/my-project
tw add # Creates an alias 'my-project' for the current directory
```

### Open an Address by Alias

To open a saved address in your default browser, simply type `tw` followed by the alias.

```shell
tw home
```

This command will open `https://github.com/skypesky`.

### List Your Aliases

If you forget an alias, you can list all saved aliases and their corresponding addresses using the `tw ls` command (or its full-length version, `tw list`).

```shell
# List all saved aliases
tw ls
```

You can also check the address for a specific alias.

```shell
# Show the address for the 'home' alias
tw ls home
```

### Update an Alias

To update the address associated with an existing alias, simply use the `tw add` command again with the same alias and the new address. This will overwrite the previous entry.

```shell
tw add home https://github.com/skypesky/to-where-cli
```

If you want to be explicit about overwriting, you can use the `--force` or `-f` flag.

### Remove an Alias

To delete an alias you no longer need, use the `tw rm` command followed by the alias name.

```shell
tw rm home
```

If you run `tw rm` without specifying an alias, the tool will enter an interactive mode, allowing you to select multiple aliases to delete from a list of all your saved entries.

### Get Help

For a complete list of commands and options, you can always use the help flag.

```shell
tw -h
```

Now that you've mastered the basics, you can explore all the available commands and their options in the [Command Reference](./command-reference.md).