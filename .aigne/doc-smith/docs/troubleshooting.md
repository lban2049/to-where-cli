# Troubleshooting

This section addresses common issues you might encounter while using `to-where-cli` and provides solutions to help you resolve them efficiently. Understanding these common scenarios and how the tool logs information can help you debug problems more quickly.

## Common Error Messages

`to-where-cli` provides clear error messages when something goes wrong. Here are some of the frequently seen errors and how to address them.

### Alias Not Found

This error occurs when you try to open, delete, or list an alias that does not exist in your configuration.

**Error Message Example:**

```
Alias my-alias was not found
```

**Cause:**
The alias you provided does not match any entry in your `to-where-cli` configuration.

**Solution:**

1.  **Check for typos:** Ensure the alias is spelled correctly.
2.  **List existing aliases:** Use the `tw list` command to see all currently configured aliases. This will help you identify if the alias exists under a different spelling or if it was never added. Refer to the [Alias Management](./command-reference-alias-management.md) section for more details on listing aliases.

### Alias Already Exists

This message appears when you attempt to add a new alias that already exists in your configuration without explicitly requesting to overwrite it.

**Error Message Example:**

```
Alias my-alias already exists, you can use '-f' or '--force' to overwrite it
my-alias => /path/to/existing/location => 5
```

**Cause:**
The alias you are trying to add is already configured. By default, `to-where-cli` prevents accidental overwrites to protect your existing entries.

**Solution:**

*   **Use the `--force` option:** If you intend to update the existing alias's address, use the `-f` or `--force` flag with the `tw add` command. This will overwrite the old entry with the new one.
    ```bash
tw add my-alias /new/path/to/location --force
    ```
*   **Choose a different alias:** If you want to add a completely new entry, pick a unique alias name.

### Emptying Configuration Without Force

Attempting to clear your entire `to-where-cli` configuration requires an explicit confirmation, which is done using the `--force` flag. This prevents accidental data loss.

**Error Message Example:**

```
To make sure you know what you're doing, you must use '-f' or '--force' to empty
```

**Cause:**
You ran the `tw clean` command without the necessary `-f` or `--force` flag.

**Solution:**

*   **Add the `--force` option:** If you are certain you want to remove all configured aliases, include the `-f` or `--force` flag.
    ```bash
tw clean --force
    ```

## Configuration File Problems

`to-where-cli` stores all your aliases and their corresponding paths in a configuration file. Understanding its location and structure can be useful for troubleshooting.

**Configuration File Location:**

By default, `to-where-cli` stores its configuration in a YAML file located in your home directory:

*   `~/.tw.config.yml`

**Potential Issues:**

*   **File Corruption:** Manual edits to the `.tw.config.yml` file might introduce syntax errors, leading to the tool being unable to read or write its configuration.
*   **Permission Issues:** Incorrect file permissions might prevent `to-where-cli` from accessing or modifying the configuration file.

**Resolution:**

1.  **Inspect the file:** Open `~/.tw.config.yml` in a text editor to check for any obvious YAML syntax errors. Ensure that the structure is valid (e.g., proper indentation, correct key-value pairs).
2.  **Empty the configuration:** If you suspect the file is corrupted or if you want to start fresh, you can use the `tw clean --force` command. This will reset the `points` section of your configuration, effectively removing all aliases while keeping the file structure intact.
    *   **Caution:** This action is irreversible and will delete all your stored aliases.

## Understanding Logs and Output

`to-where-cli` uses standard console output to provide feedback on its operations. This includes informational messages, success confirmations, and error details.

**Key aspects of `to-where-cli` output:**

*   **Informational Messages:** Operations like successfully adding or deleting an alias will typically result in a message prefixed with `info`.
    ```
Added successfully
Alias my-alias has been removed
    ```
*   **Error Messages:** As seen in the "Common Error Messages" section, errors are clearly indicated with specific messages to guide you.
*   **Listing Aliases Output:** When you list aliases using `tw list` or after `add`/`delete` commands, `to-where-cli` provides a formatted output, sorting aliases by visit count in descending order.
    ```
my-alias => /path/to/my/location => 10
another-alias => /another/path => 5
    ```
    In this format:
    -   The **alias** is displayed in blue.
    -   The **address** (path) is shown in cyan.
    -   The **visit count** is displayed in green.

These logs provide immediate feedback on command execution and are your first point of reference for understanding `to-where-cli`'s behavior or diagnosing issues.

---

This troubleshooting guide covers the most frequent issues and how to resolve them, from common error messages to configuration file problems and understanding the tool's output. For information on the latest features and bug fixes, refer to the [Release Notes](./release-notes.md) section.