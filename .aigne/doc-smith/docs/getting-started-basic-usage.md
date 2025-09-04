# Basic Usage

Once `to-where-cli` is installed, you can immediately start managing your address aliases. This guide walks you through the fundamental workflow: adding a new alias, opening its associated address, listing your saved aliases, and removing them when they are no longer needed.

## Add an Alias

To save a URL or a local file path with a memorable name, use the `tw add` command. The command follows the structure `tw add <alias> <address>`.

For example, to create an alias named `home` for a GitHub profile URL:

```shell
tw add home https://github.com/skypesky
```

If you omit the alias and address, the command will use the current working directory as the address and the directory's name as the alias.

## Open an Address by Alias

To open the address linked to an alias, simply run `tw` followed by the alias name. This will open the URL or path in the appropriate default application (e.g., a web browser for URLs).

```shell
tw home
```

Executing this command will open `https://github.com/skypesky` in your default browser.

## List Your Aliases

To view all your saved aliases and their corresponding addresses, use the `tw ls` command. The `list` command is an alias for `ls`.

```shell
tw ls
```

If you want to check the address for a specific alias, you can pass the alias name as an argument:

```shell
tw ls home
```

## Update an Alias

To change the address associated with an existing alias, simply use the `tw add` command again with the same alias name. The new address will overwrite the previous one.

```shell
# This updates the 'home' alias to point to a new repository
tw add home https://github.com/skypesky/leetcode-for-javascript
```

## Remove an Alias

To delete an alias you no longer need, use the `tw rm` command followed by the alias name.

```shell
tw rm home
```

If you run `tw rm` without specifying an alias, the tool will launch an interactive mode, presenting a list of all your aliases and allowing you to select one or more to delete.

---

You have now learned the core commands for managing aliases. For a comprehensive guide to all available commands and their options, please see the [Command Reference](./command-reference.md).