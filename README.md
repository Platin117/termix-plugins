# Platin117 Plugins

The plugin registry for Termix. Add this URL once under Plugins in Termix and
every plugin listed here, with its updates, shows up there:

```
https://raw.githubusercontent.com/Platin117/termix-plugins/main/index.json
```

## What is in here

| Plugin | Repository |
| --- | --- |
| Compact Layout | [termix-compact-layout](https://github.com/Platin117/termix-compact-layout) |
| Snippet Terminals | [termix-snippet-terminals](https://github.com/Platin117/termix-snippet-terminals) |

## How index.json is written

Nobody edits it by hand. Each plugin's release workflow checks this repository
out and runs its own `scripts/update-index.mjs`, which derives the entry from
that plugin's manifest and the packed file: the download URL, the checksum,
the size and the signature. Hand-written entries are how a registry ends up
describing a build nobody can install.

Those workflows push here with a fine-grained token that may write to this
repository and nothing else.

`publicKey` is the key every release is signed with. Termix refuses an install
whose signature does not match it.
