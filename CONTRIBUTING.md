# Contributing to Atrium

Atrium is at the design stage. There is no code yet, so most contributions right now are discussion in issues.

## Before you start

Read [CLEAN_ROOM.md](CLEAN_ROOM.md). It is a condition of contributing. In short: no code, assets, or layouts from other agent-room, agent-office, or visualizer projects, and third-party code only as unmodified dependencies.

## Proposing changes during the design stage

- **Open an issue first.** Describe the problem or idea and what you would change. Questions about the design, the threat model, or the event model are all welcome.
- **Small documentation fixes** (typos, broken links) can go straight to a pull request.
- **Code.** Please hold code pull requests until the repository has a code layout and CI. Start with an issue instead.

## Pull requests

- Fill in the [pull request template](.github/pull_request_template.md), including the clean-room checklist. A pull request with an unticked box does not merge.
- Keep each pull request to one change.
- Add a row to [assets/PROVENANCE.md](assets/PROVENANCE.md) for every asset you add or change.

## Sign your commits (DCO)

Atrium uses the [Developer Certificate of Origin](https://developercertificate.org/) (DCO) 1.1 instead of a contributor license agreement. A `Signed-off-by` line on a commit certifies that you wrote the change, or otherwise have the right to submit it, under this project's license.

Every commit needs the line, and its name and email must match the commit author:

```text
Signed-off-by: Your Name <you@example.com>
```

`git commit -s` adds it for you. To fix commits that are missing it:

```sh
git commit --amend --signoff      # the last commit
git rebase --signoff main         # every commit on your branch since main
git push --force-with-lease       # update your pull request branch
```

## License of contributions

Atrium is licensed under the [Apache License 2.0](LICENSE). Contributions are accepted under the same license (inbound equals outbound), as section 5 of the license describes. There is no separate contributor agreement.

## Security issues

Do not report vulnerabilities in public issues. See [SECURITY.md](SECURITY.md).
