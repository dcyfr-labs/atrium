# Contributing to Atrium

Atrium is at the design stage. There is no code yet, so most contributions right now are discussion in issues.

## Before you start

Read [CLEAN_ROOM.md](CLEAN_ROOM.md). It is a condition of contributing. In short: no code, assets, or layouts from other agent-room, agent-office, or visualizer projects, and third-party code only as unmodified dependencies. While you work on Atrium, do not read the source code of the projects CLEAN_ROOM.md lists, and do not have a tool or AI agent read it for you. If you have read that source before, say so in your pull request.

## Code of conduct

The [DCYFR Labs code of conduct](https://github.com/dcyfr-labs/.github/blob/main/CODE_OF_CONDUCT.md) applies to everyone taking part in Atrium.

## Proposing changes during the design stage

- **Open an issue first.** Describe the problem or idea and what you would change. Questions about the design, the threat model, or the event model are all welcome.
- **Small documentation fixes** (typos, broken links) can go straight to a pull request.
- **Code.** Please hold code pull requests until the repository has a code layout and CI. Start with an issue instead.

## Pull requests

- Fill in the [pull request template](.github/pull_request_template.md), including the clean-room checklist. A pull request with an unticked box does not merge.
- Keep each pull request to one change.
- Add a row to [assets/PROVENANCE.md](assets/PROVENANCE.md) for every asset you add or change.
- Unless a DCYFR Labs maintainer produces it, an AI-generated asset needs a DCYFR Labs maintainer to approve it in an issue before you open the pull request. See [CLEAN_ROOM.md](CLEAN_ROOM.md).

## Sign your commits (DCO)

Atrium uses the [Developer Certificate of Origin](https://developercertificate.org/) (DCO) 1.1 instead of a contributor license agreement. A `Signed-off-by` line on a commit certifies that you agree to the DCO. In short: you wrote the change, or otherwise have the right to submit it under this project's license, and you understand that the contribution and your sign-off are public and kept on record.

Every commit you author needs the line, and its name and email must match the commit author:

```text
Signed-off-by: Your Name <you@example.com>
```

`git commit -s` adds it for you. To fix commits that are missing it, run the commands below. In them, `upstream` is the remote that points at dcyfr-labs/atrium (use `origin` if you cloned it directly).

```sh
git commit --amend --signoff                                # the last commit
git fetch upstream && git rebase --signoff upstream/main    # every commit on your branch
git push --force-with-lease                                 # update your pull request branch
```

Two kinds of commit go without the line: commits a bot authors, since a bot cannot make the DCO certification (a `Signed-off-by` line a bot adds for itself does not count), and the commits GitHub itself creates (the repository's initial commit and pull request merges). A pull request opened by a bot follows the bot rule in [CLEAN_ROOM.md](CLEAN_ROOM.md). A CI check for the line is planned; it will skip both kinds.

## License of contributions

Atrium is licensed under the [Apache License 2.0](LICENSE). Contributions are accepted under the same license (inbound equals outbound), as section 5 of the license describes. The one exception is an asset whose row in [assets/PROVENANCE.md](assets/PROVENANCE.md) records a different license; that row is the license the asset is contributed under. There is no separate contributor agreement.

## Security issues

Do not report vulnerabilities in public issues. See [SECURITY.md](SECURITY.md).
