# Basic Usage

This guide provides a quick tutorial on the core workflow of `to-where-cli`. You'll learn how to add, use, list, update, and remove aliases through practical command-line examples.

## Adding an Alias

The most fundamental command is `add`. It associates a memorable alias with a longer address, such as a URL or a local directory path.

For example, to create an alias named `home` for a GitHub profile, run:

```shell
tw add home https://github.com/skypesky
```

If you run `tw add` without providing an address, it will default to using your current working directory. If you also omit the alias, it will use the directory's name as the alias.

```shell
# In /Users/me/my-project
tw add
# This is equivalent to: tw add my-project /Users/me/my-project
```

## Opening an Address by Alias

Once an alias is set, you can open the corresponding address simply by typing `tw` followed by the alias name. This will open the URL in your default browser or the directory in your file explorer.

```shell
tw home
```

## Listing Aliases

To see a list of all your saved aliases and their corresponding addresses, use the `ls` or `list` command.

```shell
tw ls
```

You can also check the address for a specific alias:

```shell
tw ls home
```

## Updating an Alias

To update the address associated with an existing alias, simply use the `add` command again with the same alias and the new address. By default, the tool will overwrite the old entry. You can also use the `--force` or `-f` flag to make this explicit.

```shell
# This command updates the 'home' alias to a new URL
tw add home https://github.com/skypesky/leetcode-for-javascript
```

## Removing an Alias

You can remove an alias using the `rm` command.

To remove a specific alias, provide its name as an argument:

```shell
tw rm home
```

If you run `tw rm` without any arguments, the tool will launch an interactive menu, allowing you to select multiple aliases to delete at once.

```shell
tw rm
# This will open an interactive prompt to select aliases for deletion
```

---

Now that you understand the basic workflow, you can explore all the available commands and their options in the [Command Reference](./command-reference.md).