# Installation

## Ask Codex to install

If Codex includes skill-installer, paste the request from the [README](README.md#start-with-codex). The installer downloads the skill folder from the repository; this is not a one-click completed installation. An existing installation should be preserved.

## Manual installation

Download the [v1.0.0 skill ZIP](https://github.com/Benz4000/benz-book-publisher/releases/download/v1.0.0/benz-book-publisher-v1.0.0.zip) and its [SHA256 checksum](https://github.com/Benz4000/benz-book-publisher/releases/download/v1.0.0/SHA256SUMS.txt), or download the repository using GitHub's Code menu. Extract the archive first.

Copy the **publish-ingramspark-kdp** folder, including its references directory, into the `skills` directory under your Codex home. A normal default is `~/.codex/skills`; if you set `CODEX_HOME`, use its `skills` subdirectory instead. Do not copy this repository's documentation or archive into that folder.

From the extracted archive directory in PowerShell:

```powershell
$codexRoot = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $HOME '.codex' }
$destination = Join-Path $codexRoot 'skills/publish-ingramspark-kdp'
if (Test-Path -LiteralPath $destination) { throw 'An installation already exists. Review it before replacing it.' }
New-Item -ItemType Directory -Path (Join-Path $codexRoot 'skills') -Force | Out-Null
Copy-Item -LiteralPath './publish-ingramspark-kdp' -Destination $destination -Recurse
Test-Path -LiteralPath (Join-Path $destination 'SKILL.md')
```

For a POSIX shell, with the same working directory:

```sh
codex_root="${CODEX_HOME:-$HOME/.codex}"
destination="$codex_root/skills/publish-ingramspark-kdp"
if [ -e "$destination" ]; then
  echo 'An installation already exists. Review it before replacing it.' >&2
  exit 1
fi
mkdir -p "$codex_root/skills"
cp -R ./publish-ingramspark-kdp "$destination"
test -f "$destination/SKILL.md"
```

Start a new Codex turn and invoke `$publish-ingramspark-kdp`. Check that Codex can read the skill and its references. Merely copying the folder does not verify a complete publishing workflow. PDF/EPUB tooling and authenticated account access remain separate.

## Other platforms: possible, untested options

The following products document skill import or discovery. Their support for the format makes them possible options; this package has **not been installed or exercised in any of them**. Preserve the entire skill folder and its relative references. Review current product documentation before installing; managed accounts can restrict custom skills.

| Product | Documented path to try | Invocation / verification |
| --- | --- | --- |
| Claude Code | Copy `publish-ingramspark-kdp/` into `~/.claude/skills/` for personal use, or `.claude/skills/` inside a project. | Try `/publish-ingramspark-kdp` and verify the references load. [Official guide](https://code.claude.com/docs/en/skills). |
| Claude web / Desktop Skills | Where custom Skills are available, upload a ZIP containing the skill folder through Customize > Skills and enable it. | Ask to use the skill by name and inspect the result. The help article specifies a 200-character description limit; the current package's longer description may need shortening in a separate local copy before repackaging. Preserve the instructions and references. [Official guide](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills). |
| Cursor | Copy the folder into `.cursor/skills/` inside a project, or `~/.cursor/skills/` for local user-level discovery. | Type `/` in Agent chat and look for the skill. Remote sessions may need a project-level copy. [Official guide](https://cursor.com/docs/skills). |
| Gemini CLI | Copy the folder into `.gemini/skills/` inside a workspace, or `~/.gemini/skills/` for user-level discovery. | Use `/skills list`, then ask Gemini to use the skill and review its activation prompt. [Official guide](https://geminicli.com/docs/cli/skills/). |

Documentation checked October 31, 2026. These paths do not install the required PDF/EPUB/image tools or provide authenticated browser access. An environment might support editing and file preparation while lacking supported account operations. Request only the steps its tools can perform, and record external publishing steps as blocked until a supported, authorized path exists. Follow that product's own permissions and invocation behavior; do not copy Codex-specific controls or the Codex installer request into another product.

The v1.0.0 download is unchanged. These online setup notes add possible import paths, not newly tested package behavior.

## Verify the download

Compare the archive's SHA256 with the separately downloaded checksum before extracting:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath './benz-book-publisher-v1.0.0.zip'
```

The versioned ZIP contains only the skill folder. Repository source and documentation are also available at the [v1.0.0 release](https://github.com/Benz4000/benz-book-publisher/releases/tag/v1.0.0).
