# Publishing & Versioning

## Automated Publishing

This extension uses GitHub Actions to automatically publish to both the VS Code Marketplace and Open VSX registry when a new version tag is pushed.

### How to publish a new release
1. Update your changelog and bump the version in `package.json` (see below for automation).
2. Push a new version tag (e.g., `v0.0.5`):
   ```sh
   git tag v0.0.5
   git push origin v0.0.5
   ```
3. The GitHub Actions workflow will package and publish the extension to both registries.

## Auto-Incrementing the Version

You can use the VSCE CLI to bump the version and publish in one step:

- To increment the minor version:
  ```sh
  vsce publish minor
  ```
- To set a specific version:
  ```sh
  vsce publish 1.1.0
  ```

This will:
- Update the `package.json` version.
- Commit the change and create a git tag.
- Publish the extension to the Marketplace.

### Automating Version Bumping & Publishing

To automate version bumping and publishing (without manual edits):

1. Run the desired VSCE publish command:
   ```sh
   vsce publish patch   # or minor, major, or a specific version
   ```
2. This will:
   - Update `package.json`
   - Commit the change
   - Create a tag
   - Publish to the Marketplace

3. Push the commit and tag to GitHub:
   ```sh
   git push && git push --tags
   ```
4. The workflow will also publish to Open VSX using the same package.

**Tip:** You can add a script to your `package.json` for convenience:
```json
"scripts": {
  "release:patch": "vsce publish patch && git push && git push --tags"
}
```
