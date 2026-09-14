# TODO

Suggestions, grouped by how much each one disturbs.
Light edits change text in place.
Moderate ones add files or change repo settings, but leave every page where it is.
Invasive ones move files, change URLs, or change how the site deploys.

## Light

- Delete the chatbot leftover in the MLOps section of `learning_material.md` ("Would you be looking to implement LGTM..."), and cut the pasted list of job roles to a line saying what LGTM is
- Fix the "Return to top" link in `src/fastapi/README.md`, which climbs one directory too far
- Fix the pre-commit link in `src/python/README.md`: it uses backslashes and a path from the repo root, so it should read `pre-commit/README.md`
- Fix the testing link in `src/python/README.md` the same way: `testing/README.md`
- Fill in or remove the stubs: `src/aws/sagemaker/README.md`, `src/python/testing/README.md`, and the bare "Orchestration" and "Data Versioning" bullets in `learning_material.md`
- Say how to request access to the private coursework repos, since the README offers access but gives no way to ask
- Remove the citation section from `README.md`, or give it a real title; "Title: Francisco Camargo" and a blank "Date Accessed" read as a template left unfilled
- Update the `dev_workflow` paths in `src/linux/README.md`, since the repo is now `dev-workflow`
- Set the repo's homepage (the About box) to the Pages site; it points at the GitHub profile now

## Moderate

- Bring in the repo-template files the repo lacks (`.gitignore`, `.editorconfig`, `.pre-commit-config.yaml`, `cspell.json`, `SECURITY.md`) and run `pre-commit install`; lychee would have caught the broken links above
- Turn on secret scanning push protection and private vulnerability reporting, both off on this public repo
- Copy the screenshot in `src/testing/README.md` into this repo; it lives in the `dev-workflow` repo's uploads, and breaks if that repo goes away
- Add a way to reach you to `README.md`: email, LinkedIn, or a resume link
- List public projects under Projects with a line on what each does; the section now holds only coursework, mostly private, while the public repos sit in the learning material

## Invasive

### Rename `master` to `main`

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

### Other

- Build the site with a GitHub Actions workflow instead of the legacy build, so the build lives in the repo, can pin its Jekyll version, and can check links on every push
- Keep each page's images beside it (as `src/python` does) rather than in the top-level `image/README/`, which `src/git` and `src/vscode` reach into
- Move the learning notes under `src/` to their own repo, so this one, which doubles as the GitHub profile README, stays about you and your projects; every notes URL would change
