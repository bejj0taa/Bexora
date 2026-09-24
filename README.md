# Bexora

Bexora is distributed as a compiled Windows application.

This release is intended for authorized use only. You are responsible for making sure you have permission to use the application in any Discord server, account, environment, or system where it is executed.

---

## Installation

Keep the release files together in the same directory:

```text
Bexora/
├── Bexora.exe
├── .env
└── nukegif/
```

Open `.env` and replace:

```env
DISCORD_TOKEN=SET TOKEN HERE
```

with the token for the Discord bot you are authorized to use.

Never publish, share, upload, or send a configured `.env` file containing a real token.

---

## `nukegif` Directory

The `nukegif` directory is required by the application.

Bexora references the GIF assets by their expected path and filename. If a GIF is renamed, moved, deleted, or replaced with a file that uses a different name, the application may no longer be able to display that GIF.

If you replace one of the GIF files, keep the **exact same filename** as the original file.

For example, if the application expects:

```text
nukegif/nuked-nuke1.gif
```

then replacing that asset should still result in:

```text
nukegif/nuked-nuke1.gif
```

Do not change it to:

```text
nukegif/new-nuke.gif
```

unless the corresponding path is also changed in the source code.

Moving the `nukegif` folder away from `Bexora.exe` may also break asset loading.

### Important

The public release does not guarantee compatibility with renamed, removed, reorganized, or externally modified assets.

If Discord-hosted media, external URLs, or referenced resources change or become unavailable, the related content may stop displaying even if Bexora itself has not changed.

---

## Do Not Modify the Release

The official Bexora release is distributed in its original compiled form.

Do not:

- patch or modify `Bexora.exe`;
- decompile, unpack, disassemble, or attempt to reconstruct the source code;
- remove or bypass application restrictions;
- redistribute modified builds as official Bexora releases;
- impersonate the original project or author;
- bundle Bexora with unknown executables, loaders, injectors, or modified dependencies;
- publish private source code obtained without authorization.

Modified or unofficial builds are not supported and may behave differently from the official release.

Any support request involving an altered executable, changed runtime files, or an unofficial package may be rejected.

---

## Reverse Engineering and Integrity

Bexora is provided as a compiled executable in order to protect the original source distribution.

Unauthorized reverse engineering, decompilation, unpacking, patching, or redistribution is prohibited by the project terms.

Do not assume that modifying the executable produces an official or trusted Bexora build. Hashes, signatures, release artifacts, or future integrity checks may be used to distinguish official releases from modified copies.

**Important:** Bexora does not claim to automatically identify a person attempting to reverse engineer the executable unless a specific telemetry or integrity-reporting feature is explicitly implemented and disclosed in that version.

---

## Official Builds

Only releases published through the official Bexora repository should be treated as official.

If an executable has been downloaded from another source, modified, renamed, repackaged, or bundled with additional software, its integrity cannot be guaranteed.

When release hashes are provided, compare the downloaded file against the published hash before running it.

---

## Environment File

The `.env` file is intentionally kept outside the executable.

Example:

```env
DISCORD_TOKEN=SET TOKEN HERE
```

Each user should configure their own authorized bot token locally.

Never commit a real `.env` file to GitHub.

Never include your real token in screenshots, logs, issue reports, archives, or public release packages.

If a token is accidentally exposed, revoke or regenerate it immediately through the appropriate Discord developer settings.

---

## File Integrity

Bexora expects its runtime files to remain in the structure provided with the release.

Changing filenames or moving required files can cause:

- missing GIFs;
- missing resources;
- startup errors;
- incomplete UI content;
- unexpected application behavior.

Before reporting an issue, restore the original release structure and test the official build again.

---

## Modified Builds

If you modify any part of the distributed package, clearly label it as an unofficial modification.

Do not present modified builds as original releases from Bexora or its author.

The author is not responsible for problems caused by third-party modifications, repackaging, altered assets, injected code, or unofficial distributions.

---

## Security

Do not execute Bexora releases obtained from unknown mirrors or third-party download pages.

Do not share your Discord bot token with another person.

Do not hard-code private credentials into a redistributed executable.

Use Bexora only in environments where you have explicit authorization.

---

## Copyright

Copyright © 2026 bejj0taa.

All rights reserved.

Unauthorized redistribution, modification, reverse engineering, decompilation, source reconstruction, or commercial redistribution of Bexora is prohibited except where applicable law provides otherwise.

Bexora and its official release materials may not be represented as another person's original work.
