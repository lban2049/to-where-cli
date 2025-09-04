# Changelog

This page documents the history of changes, new features, and bug fixes for each version of `to-where-cli`.

## [0.0.23] - 2024-06-06

### Chore
- Removed unused code.

## [0.0.22] - 2024-06-06

### Features
- Added RunKit options to the `npm` command.

## [0.0.21] - 2023-09-13

### Features
- Extended the `npm` command with new options (`tw npm -c/-d/-v`).

## [0.0.20] - 2023-07-11

### Features
- Added support for opening a specified branch.
- Added support for opening the first commit of a repository.

## [0.0.19] - 2023-05-21

### Features
- Added support for opening a specified branch.
- Added support for opening the first commit.

### Documentation
- Updated `README.md` and the GitBook site documentation.

## [0.0.18] - 2023-05-14

### Features
- Improved test coverage and implementation.

## [0.0.17] - 2023-02-26

### Features
- Added support for opening the star page of a project.
- Added support for removing multiple aliases using `tw rm`.

## [0.0.16] - 2023-02-10

### Features
- Added support for searching on npm, Baidu, Google, Bing, and GitHub pages.
- The `tw list` subcommand now accepts `tw ls` as a shorthand.

## [0.0.15] - 2023-02-06

### Features
- The `git` subcommand now works with Git SSH URLs.

## [0.0.14] - 2023-02-03

### Features
- Added support for creating a pull request using `tw git open --pull`.

## [0.0.13] - 2023-01-28

### Features
- Added support for releasing beta versions of `to-where-cli`.
- Implemented a version check before release.

### Bug Fixes
- Fixed a Windows installation error caused by the `npx only-allow pnpm` preinstall script.

## [0.0.12] - 2023-01-27

### Bug Fixes
- Corrected an error in the `README.md` file.

## [0.0.11] - 2023-01-27

### Features
- Added support for opening a file at a specified path via `tw git open --file <path>`.
- Added support for opening a specific commit via `tw git open -c <hash>`.

## [0.0.10] - 2023-01-27

### Features
- Added support for the Windows operating system.
- Added support for opening various Git pages, including branches, issues, and pull requests.
- Implemented visit statistics tracking.