# Connections Manager

![Latest release](https://img.shields.io/github/v/release/GoblinRules/ecpa-connections-manager)

Named Cloudflare and GitHub accounts, secure Windows credentials, project assignments and a process-scoped CLI/MCP helper.

This is the dedicated **release repository** for `connections-manager`. It owns this plugin's releases and version history. The source lives in the shared [ECPA Plugins workspace](https://github.com/GoblinRules/ecpa-plugins/tree/master/plugins/connections-manager); shared libraries are maintained once, rather than copied between release repositories.

## Install and update

Add this public registry in ECPA's plugin settings:

```text
https://raw.githubusercontent.com/GoblinRules/ecpa-plugins/master/registry.json
```

Refresh the Plugin store and install **Connections Manager**. Existing users keep the same registry URL and plugin ID. Restart the core when prompted. Windows x64 binaries are available under [Releases](https://github.com/GoblinRules/ecpa-connections-manager/releases).

## Documentation

- [Usage, configuration and supported features](https://github.com/GoblinRules/ecpa-plugins/tree/master/plugins/connections-manager/README.md)
- [Shared agent tools documentation](https://github.com/GoblinRules/ecpa-plugins/blob/master/docs/agent-tools.md)
- [Source workspace and contributing](https://github.com/GoblinRules/ecpa-plugins)
- [Release process](https://github.com/GoblinRules/ecpa-plugins/blob/master/docs/releases.md)

## Repository layout

```text
README.md                      Installation and source links
LICENSE                        MIT license
THIRD_PARTY_NOTICES.md          Agent icon attribution
plugin.json                    Plugin and source identity
.github/workflows/release.yml   Build and publish this plugin from a source commit
```

Each release includes the DLL ZIP, SHA-256 checksums, `release.json` with its source commit, and a complete source workspace ZIP. The source commit in the release is authoritative; documentation on master may describe later changes.

## Publishing

Bump only `plugins/connections-manager/Cargo.toml` in the source workspace, update its lockfile, test, commit and push. Run **Actions → Publish plugin release** here with the full 40-character source commit SHA. The workflow builds only this plugin and publishes its version using this repository's own GitHub Actions token. No cross-repository token or token for end users is required.

Initial release: 0.1.0. The separately checksummed `ecpa-connect_windows_amd64.exe` helper is required for launching CLI/MCP processes with managed connections. Download it from Releases and place it at a stable path; the store installs only the plugin DLL. See the usage documentation for setup.
