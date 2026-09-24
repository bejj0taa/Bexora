# Bexora

Bexora is distributed as a standalone Windows application.

No Python installation, `.env` file, external GIF directory, or additional runtime files are required for the official compiled release.

> **Authorized use only.**  
> You are responsible for ensuring that you have permission to use Bexora with any Discord bot, server, account, environment, or system where it is executed.

---

## Installation

Bexora does not require a traditional installation.

Download the latest official release and extract:

```text
Bexora/
└── Bexora.exe
```

Run:

```text
Bexora.exe
```

That is all that is required.

Do not run the executable directly from inside a compressed archive. Extract it to a normal directory first.

---

## First Launch

When Bexora is started for the first time, the application will display the bot authentication screen.

Enter the token of the Discord bot you are authorized to use.

```text
Bexora.exe
    ↓
Bot Authentication
    ↓
Enter your bot token
    ↓
Token validation
    ↓
Bexora
```

Bexora validates the token before allowing access to the main interface.

An invalid, revoked, expired, or otherwise rejected token will not be accepted.

---

## Bot Authentication

Bexora validates the supplied bot token directly against Discord before starting the main application.

The token is never required through a `.env` file in the official portable release.

Once successfully validated, the token is stored locally for the current Windows user.

On future launches, Bexora will attempt to validate the stored token automatically.

If the stored token is no longer valid, Bexora will discard it and request a new token.

---

## Local Credential Storage

Bot credentials are stored locally on the computer where Bexora is used.

The local Bexora configuration is stored under:

```text
%LOCALAPPDATA%\Bexora
```

The bot token is protected using Windows user-level encryption before being stored.

This means the saved credential is associated with the Windows user that created it.

Moving `Bexora.exe` to another computer does **not** transfer the saved bot token.

Each user or computer must authenticate independently.

---

## Resetting the Saved Bot Token

To force Bexora to request a new bot token, close the application and remove the local Bexora configuration directory:

```text
%LOCALAPPDATA%\Bexora
```

You can also remove it from PowerShell:

```powershell
Remove-Item "$env:LOCALAPPDATA\Bexora" -Recurse -Force
```

The next time Bexora starts, the bot authentication screen will appear again.

---

## Portable Release

The official release is designed to operate as a standalone executable.

The user only needs:

```text
Bexora.exe
```

The following files are **not required** beside the executable:

```text
.env
nukegif/
app.py
bot_core.py
requirements.txt
Python
Nuitka
```

Application assets required by the official build are packaged with the executable.

---

## Bundled Assets

Images, GIFs, icons, and other required application resources are bundled into the official Bexora executable during compilation.

You do not need to create, download, move, or maintain an external `nukegif` directory when using an official compiled release.

The source project may contain directories such as:

```text
nukegif/
```

These directories are used during development and compilation.

They are embedded into the final portable build.

---

## Internet Connection

An internet connection is required for operations that communicate with Discord, including bot token validation.

If Discord cannot be reached because of an internet connection problem, firewall restriction, service outage, DNS issue, or other network problem, Bexora may be unable to authenticate or perform Discord-related operations.

---

## Discord Bot Token Security

A Discord bot token is a private credential.

Never:

- publish a bot token;
- commit a bot token to GitHub;
- include a token in screenshots;
- post a token in issue reports;
- share a token through Discord messages;
- include a token in public archives;
- hard-code a private token into a public build;
- send your token to another person.

If a token is accidentally exposed, regenerate it immediately through the appropriate Discord developer settings.

Bexora will never require a public `.env` file containing your bot token.

---

## Official Builds

Only releases published through the official Bexora repository should be treated as official Bexora builds.

A release obtained from another source may have been:

- modified;
- repackaged;
- patched;
- bundled with additional software;
- renamed;
- altered after publication.

Its integrity therefore cannot be guaranteed by the Bexora project.

When cryptographic hashes are provided with a release, compare the downloaded executable against the published hash before running it.

---

## Windows Security Warnings

Bexora is distributed as a compiled Windows executable.

Windows SmartScreen or Microsoft Defender may display a warning for newly published executables that do not yet have established reputation or a recognized code-signing certificate.

A SmartScreen warning alone does not indicate that the application failed to compile correctly.

Always download Bexora from the official release source and verify published hashes when available.

---

## Do Not Modify the Official Release

The official Bexora release is distributed in its compiled form.

Do not:

- patch or modify `Bexora.exe`;
- remove or bypass application restrictions;
- redistribute altered builds as official Bexora releases;
- impersonate the original project or author;
- bundle Bexora with unknown executables, loaders, or injectors;
- distribute private source code obtained without authorization.

Modified or unofficial builds are not supported and may behave differently from the official release.

Support requests involving altered binaries or unofficial packages may be rejected.

---

## Reverse Engineering and Integrity

Bexora is distributed as a compiled executable to provide a consistent release and protect the original source distribution.

Reverse engineering, decompilation, unpacking, patching, redistribution, or source reconstruction may be restricted by the project terms and applicable law.

Modified executables must not be presented as official Bexora releases.

Future releases may publish hashes, signatures, or other integrity information to help users distinguish official artifacts from modified copies.

Bexora does not claim to automatically identify or track individuals attempting to inspect or modify the executable unless such functionality is explicitly implemented and disclosed in that version.

---

## Modified Builds

If you create a modified version of Bexora where permitted, it must be clearly identified as an unofficial modification.

Do not represent a modified build as an original release from Bexora or its author.

The author is not responsible for issues caused by:

- third-party modifications;
- repackaged executables;
- injected code;
- altered assets;
- unofficial distributions;
- modified dependencies;
- unauthorized builds.

---

## Troubleshooting

### Bexora asks for the bot token again

The previously stored token may have been:

- revoked;
- regenerated;
- invalidated;
- removed from local storage;
- created under another Windows user.

Enter a valid token again.

---

### Bexora cannot validate the token

Check that:

- the token is correct;
- the bot still exists;
- the token has not been regenerated;
- the computer has internet access;
- Discord is reachable from the current network.

---

### The application does not start

Make sure the executable was fully extracted from the downloaded archive before running it.

Recommended:

```text
Downloads/
└── Bexora/
    └── Bexora.exe
```

Avoid running it directly from inside `.zip`, `.rar`, or temporary archive directories.

---

### Images or GIFs are missing

Official portable builds contain the required assets internally.

If an official release reports missing bundled resources, verify that you are running the original release artifact and not an altered or incomplete build.

---

## Development

The source version of Bexora may require Python and additional dependencies.

Example development structure:

```text
Bexora/
├── app.py
├── bot_core.py
├── bexora.ico
├── requirements.txt
└── nukegif/
```

Development files are not required by users of the official portable build.

---

## Building

Official Windows builds are compiled as standalone executables.

Example Nuitka build:

```powershell
python -m nuitka app.py --mode=onefile --windows-console-mode=disable --windows-icon-from-ico=bexora.ico --include-data-files=bexora.ico=bexora.ico --include-data-dir=nukegif=nukegif --enable-plugin=tk-inter --output-filename=Bexora.exe --assume-yes-for-downloads
```

The resulting release artifact is:

```text
Bexora.exe
```

Build directories generated by Nuitka are development artifacts and are not required for distribution.

---

## Security

Use Bexora only with bots, servers, systems, and environments where you have explicit authorization.

Do not download Bexora from unknown mirrors or third-party download pages.

Do not share your Discord bot token with other people.

Do not place private credentials inside public repositories or release archives.

Keep Discord bot permissions limited to what the bot actually requires.

---

## Copyright

Copyright © 2026 bejj0taa.

All rights reserved.

Bexora and its official release materials may not be represented as another person's original work.

Unauthorized redistribution, modification, source reconstruction, or commercial redistribution may be prohibited except where applicable law provides otherwise.
