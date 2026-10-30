# Privacy setup

Configure your GitHub-provided noreply address locally with `git config --local user.email YOUR_GITHUB_NOREPLY_ADDRESS`. Do not use a private email.

Install the checksum-pinned scanner with `python3 -B scripts/privacy-install.py`, then enable the local hooks with `git config --local core.hooksPath .githooks`. The hooks inspect the staged tree, commit identities and messages, and every introduced commit at push time.

Run `python3 -B scripts/privacy.py full --all-objects` before publication. Reports redact detected values. CI uses the approved PR-base scanner, checks every introduced commit and the integration tree, and scans the available history weekly. Changes to the scanner, dependencies or workflows require local validation of the exact SHA before merge.
