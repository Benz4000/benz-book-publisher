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

## Verify the download

Compare the archive's SHA256 with the separately downloaded checksum before extracting:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath './benz-book-publisher-v1.0.0.zip'
```

The versioned ZIP contains only the skill folder. Repository source and documentation are also available at the [v1.0.0 release](https://github.com/Benz4000/benz-book-publisher/releases/tag/v1.0.0).
