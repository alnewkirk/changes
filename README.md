## Project

changes - Curate changelog and release documents with ease, from the command-line using your `$EDITOR`.

## Description

Changes is a powerful and efficient command-line application for managing
software release documents. Designed to seamlessly produce changelog and
release documents composed of a curated chronologically ordered list of
noteworthy changes.

## Features

- One prerequisite, Bash
- Does not rely on version control history
- Manage changelog and release documents alongside your source code
- Iteratively create and curate changes, tracked as simple files and directories
- Generate CHANGELOG and RELEASE documents in markdown and plain text
- Search and recall recorded changes by content or file name
- Create category-specific change templates

## Example
You're building a todo-list application and you want to use "changes" to manage
your changelog and release notes.
1. Change the directory:
   ```bash
   cd todo
   ```
2. Initialize release tracking:
   ```bash
   changes init
   ```
3. Track the initial release:
   ```bash
   changes update "initial release"
   ```
4. Release version 0.1.0:
   ```bash
   changes release 0.1.0
   ```
5. Describe the current release:
   ```bash
   changes show
   ```

## Installation
1. Clone the repository:
   ```bash
   git clone /path/to/changes.git
   ```
2. Make the script executable:
   ```bash
   chmod +x changes/changes
   ```
3. Add the directory to the `PATH` environment variable:
   ```bash
   PATH="$PATH:$PWD/changes"
   ```

## Usage

The following are common usage examples:

### Base Command

Change the changes base, i.e. the base path.

```
changes base PATH
```

Example:
```bash
changes base /path/to/changes
```

### Conf Command

Print the environment variables.

```
changes conf
```

Example:
```bash
changes conf
```

### Defect Command

Record defect. Optionally providing a slug, or filename, and release name.

```
changes defect [SLUG] [NAME]
```

Examples:
```bash
changes defect
changes defect user-management
changes defect user-management 0.0.1
```

### Detract Command

Record detraction. Optionally providing a slug, or filename, and release name.

```
changes detract [SLUG] [NAME]
```

Examples:
```bash
changes detract
changes detract user-management
changes detract user-management 0.0.1
```

### Feature Command

Record feature. Optionally providing a slug, or filename, and release name.

```
changes feature [SLUG] [NAME]
```

Examples:
```bash
changes feature
changes feature user-management
changes feature user-management 0.0.1
```

### Files Command

Find files matching the terms provided and print the filename(s).

```
changes files TERM [TERM, ...]
```

Examples:
```bash
changes files next
changes files next feature
```

### Find Command

Find changes matching the terms provided and print the filename(s).

```
changes find TERM [TERM, ...]
```

Examples:
```bash
changes find user management
changes find user management add
changes find user management remove
```

### Form Command

Create a change form, i.e. template, using the NAME provided.

```
changes form NAME
```

Examples:
```bash
changes form defect
changes form detract
changes form feature
changes form notice
changes form remove
changes form secure
changes form update
```

### Generate Command

Generate the version and release documents for the current release.

```
changes generate
```

Example:
```bash
changes generate
```

### Grep Command

Find changes matching the terms provided and print matches using grep.

```
changes grep TERM [TERM, ...]
```

Examples:
```bash
changes grep user management
changes grep user management add
changes grep user management remove
```

### Hook Command

Create a runtime hook using the NAME provided.

```
changes hook NAME
```

Example:
```bash
changes hook vars
```

### Init Command

Initialize the changes repository.

```
changes init
```

Example:
```bash
changes init
```

### Merge Command

Merge a release into another, on undo a release by merging into "next".

```
changes merge [FROM] [INTO]
```

Examples:
```bash
changes merge
changes merge 0.0.1
changes merge 0.0.1 0.0.2
changes merge 0.0.2 next
```

### Notice Command

Record notice. Optionally providing a slug, or filename, and release name.

```
changes notice [SLUG] [NAME]
```

Examples:
```bash
changes notice
changes notice user-management
changes notice user-management 0.0.1
```

### Open Command

Find changes matching the terms provided and open the file(s) in the EDITOR.

```
changes open TERM [TERM, ...]
```

Examples:
```bash
changes open user management
changes open user management add
changes open user management remove
```

### Path Command

Change the changes path for changes.

```
changes path PATH
```

Example:
```bash
changes path /path/to/changes/.changes
```

### Release Command

Create release and generate changelog and release text and makrdown documents.

```
changes release NAME
```

Examples:
```bash
changes release 0.0.1-alpha
changes release 0.0.1-beta
changes release 0.0.1
```

### Remove Command

Record removal. Optionally providing a slug, or filename, and release name.

```
changes remove [SLUG] [NAME]
```

Examples:
```bash
changes remove
changes remove user-management
changes remove user-management 0.0.1
```

### Report Command

Print pending changes, released changes, or the changes from the current release.

```
changes report [TYPE] [FORMAT]
```

Examples:
```bash
changes report
changes report changes
changes report changes markdown
changes report changes plaintext
changes report release
changes report release markdown
changes report release plaintext
changes report next
```

### Revert Command

Revert the current release and move the changes into the release queue.

```
changes revert
```

Example:
```bash
changes revert
```

### Root Command

Change the changes root path name, i.e. under the base.

```
changes root NAME
```

Example:
```bash
changes root .changes
```

### Search Command

Find changes matching the terms provided and print the results and filename(s).

```
changes search TERM [TERM, ...]
```

Examples:
```bash
changes search user management
changes search user management add
changes search user management remove
```

### Secure Command

Record vulnerability. Optionally providing a slug, or filename, and release name.

```
changes secure [SLUG] [NAME]
```

Examples:
```bash
changes secure
changes secure user-management
changes secure user-management 0.0.1
```

### Show Command

Show changes for a specific release or the current release. Optionally providing a release name.

```
changes show [NAME]
```

Examples:
```bash
changes show
changes show 0.0.1
```

### Type Command

Change the file type, i.e. the file suffix.

```
changes type NAME
```

Examples:
```bash
changes type md
changes type txt
```

### Update Command

Record update. Optionally providing a slug, or filename, and release name.

```
changes update [SLUG] [NAME]
```

Examples:
```bash
changes update
changes update user-management
changes update user-management 0.0.1
```

### Version Command

Print the latest release name.

```
changes version
```

Example:
```bash
changes version
```

### Versions Command

Print the list of release names in chronological order.

```
changes versions
```

Example:
```bash
changes versions
```

## Searching

This application supports searching through changes using inclusion and
exclusion terms. Use of inclusion and exclusion terms are supported by `find`,
`open`, `search`, and `view` commands.

### Implicit inclusion
By default, any term provided, not prefixed, will be treated as an inclusion term.

Example:
```bash
changes search release
```

### Explicit inclusion
Any term provided that is prefixed with a `+` symbol, will be treated as an
inclusion term. Notes containing the term will be included in the results.

Example:
```bash
changes search +release
```

### Explicit exclusion
Any term provided that is prefixed with a `-` symbol, will be treated as an
exclusion term. Notes containing the term will be excluded from the results.

Example:
```bash
changes search -release
```

## Environment Variables

The following are overridable environment variables:

#### CHANGES_BASE

The `CHANGES_BASE` variable is the filepath for the parent directory of the
changes folder where all changes will be stored, and defaults to `$PWD`.

Example:
```bash
export CHANGES_BASE=$HOME
```

### CHANGES_FILE_CHANGES_MARKDOWN

The `CHANGES_FILE_CHANGES_MARKDOWN` variable is the filename for the changelog
being generated in markdown format.

Example:
```bash
export CHANGES_FILE_CHANGES_MARKDOWN="CHANGES.md"
```

### CHANGES_FILE_CHANGES_PLAINTEXT

The `CHANGES_FILE_CHANGES_PLAINTEXT` variable is the filename for the changelog
being generated in plaintext format.

Example:
```bash
export CHANGES_FILE_CHANGES_PLAINTEXT="CHANGES.txt"
```

### CHANGES_FILE_RELEASE_MARKDOWN

The `CHANGES_FILE_RELEASE_MARKDOWN` variable is the filename for the release
notes being generated in markdown format.

Example:
```bash
export CHANGES_FILE_RELEASE_MARKDOWN="RELEASE.md"
```

### CHANGES_FILE_RELEASE_PLAINTEXT

The `CHANGES_FILE_RELEASE_PLAINTEXT` variable is the filename for the release
notes being generated in plaintext format.

Example:
```bash
export CHANGES_FILE_RELEASE_PLAINTEXT="RELEASE.txt"
```

#### CHANGES_INIT

The `CHANGES_INIT` variable is the fully-qualified filepath for the initial (or
bootstrapping) changes directory, and defaults to `$PWD/.changes`. This
directory is checked for pre-processing hooks before executing the program.

Example:
```bash
export CHANGES_INIT=$PWD/.changes
```

#### CHANGES_PATH

The `CHANGES_PATH` variable is the fully-qualified filepath for the changes
directory, and defaults to `$CHANGES_BASE/$CHANGES_ROOT`.

Example:
```bash
export CHANGES_PATH=$HOME/changes
```

#### CHANGES_ROOT

The `CHANGES_ROOT` variable is the name of the changes directory, and defaults
to `.changes`.

Example:
```bash
export CHANGES_ROOT=changes
```

#### CHANGES_TYPE

The `CHANGES_TYPE` variable is the file suffix used when operating on changes, and
defaults to `txt`.

Example:
```bash
export CHANGES_TYPE=md
```

## Git Hooks

Git hooks are scripts that run automatically at specific stages of Git
operations, like committing or pushing. As an example, see the `git` pre-commit
[hook](.githooks/pre-commit) that requires that all changes are recorded for
each commit to a branch that isn't _"main"_ or _"master"_. The idea is that if
you're working on the branch `implement-user-management` then you should have a
change (and corresponding change file) named _"implement-user-management"_. The
git hooks can be install by using the following commands:

```bash
git config core.hooksPath .githooks
```

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

---

Curate changelog and release documents with ease using `changes`.
