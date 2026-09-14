# TODO

## Rename `master` to `main`

Rename the default branch from `master` to `main`.

Take care: GitHub Pages builds https://francisco-camargo.github.io/francisco-camargo/ from `master`.
Pages uses the legacy build (source: branch `master`, path `/`), set in the repo's Pages settings rather than in a workflow file.

Steps:

- Rename the branch on GitHub (Settings > Branches), which retargets open pull requests and branch protection rules
- Check that the `protect-main` ruleset now targets `main`; it names `refs/heads/master` outright, and may not follow the rename
- Check that Settings > Pages now builds from `main`, and set it if not
- Confirm the site still loads and shows the latest content
- Point local clones at the new branch: `git fetch origin`, `git branch -m master main`, `git branch -u origin/main main`, `git remote set-head origin -a`
- Search the repo and the other repos for links or scripts that name `master`
