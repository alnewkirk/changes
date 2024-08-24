## Contributing

changes - Curate changelog and release documents with ease, from the command-line using your `$EDITOR`.

## Features

- One prerequisite, Bash
- Does not rely on version control history
- Manage changelog and release documents alongside your source code
- Iteratively create and curate changes, tracked as simple files and directories
- Generate CHANGELOG and RELEASE documents in markdown and plain text
- Search and recall recorded changes by content or file name
- Create category-specific change templates

## Aspirations

The following features and goals should anchor the direction and development of
this project:

- No dependencies
- Performance-minded
- Exception handling
- Pure-Perl autoboxing
- Pluggable standard library
- Consistent naming, intuitive behaviors
- Robust and accurate documentation
- Small, flexible, powerful, optional
- Simple package reflection
- Utility classes for common behaviors
- Value classes for primitives data types
- Composable standards via traits (roles)

## Installation

Install Venus using [Git](https://git-scm.com):

```bash
git clone /path/to/changes.git

cd changes
```

## Directory Structure

```
.
├── CHANGELOG
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── GITHUB.md
├── README.md
├── RELEASE
├── RELEASE.md
└── changes
```

* `changes`: The application.

## Testing

No tests. Do it live!

## Support

**Questions, Suggestions, Issues/Bugs**

Please post any questions, suggestions, issues or bugs to the issue
tracker on GitHub.

## Philosophy

The goal of "changes" is to be a zero-config application for changelog and
release notes managememnt that facilitates the
[keepachangelog](https://keepachangelog.com/) philosophy.
