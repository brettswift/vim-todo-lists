# Release Process

This fork tracks its own release history separately from upstream
(`aserebryakov/vim-todo-lists`). Releases are plain git tags, no build step
required since this is a pure Vimscript plugin.

## Versioning

Semantic versioning, `MAJOR.MINOR.PATCH`, no `v` prefix, matching upstream's
existing tag history (`0.1.0`, `0.8.0`, etc).

- **MAJOR**: breaking changes to configuration variables, commands, or mappings
- **MINOR**: new features, backward compatible
- **PATCH**: bug fixes, backward compatible

## Cutting a Release

1. Confirm `main` is up to date and working tree is clean:

   ```
   git checkout main
   git pull origin main
   git status
   ```

2. Tag the release:

   ```
   git tag -a X.Y.Z -m "X.Y.Z"
   ```

3. Push the tag:

   ```
   git push origin X.Y.Z
   ```

## Pinning to a Release

To install a specific tagged version with vim-plug:

```
Plug 'brettswift/vim-todo-lists', { 'tag': 'X.Y.Z' }
```

Omit the `tag` key to track `main` directly during active development.

## Syncing with Upstream

The original project is configured as the `upstream` remote:

```
git fetch upstream
git merge upstream/main
```

Resolve conflicts, then continue with a normal release as above.
