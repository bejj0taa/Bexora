# Bexora

Bexora is distributed as a standalone Windows application.

No Python installation, `.env` file, or external asset directory is required.

> Bexora is intended only for authorized use in environments, servers, accounts, and systems where you have permission to operate.

---

## Installation

Download the latest official Bexora release.

Extract the downloaded archive and run:

```text
Bexora.exe
```

No additional installation is required.

---

## First Launch

When Bexora starts for the first time, you will be asked to connect a Discord bot.

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

Only valid Discord bot tokens are accepted.

---

## Bot Authentication

Bexora validates the supplied bot token before opening the main interface.

If the token is invalid, revoked, or no longer available, authentication will fail.

After successful authentication, the credential is stored locally for the current Windows user.

Future launches will automatically validate the stored credential before opening Bexora.

---

## Credential Storage

Bexora stores its local configuration under:

```text
%LOCALAPPDATA%\Bexora
```

The saved bot credential is protected locally for the Windows user.

The token is not embedded into `Bexora.exe`.

Copying the executable to another computer does not copy the saved credential.

---

## Resetting the Saved Bot

To connect another bot, close Bexora and delete:

```text
%LOCALAPPDATA%\Bexora
```

You can also use PowerShell:

```powershell
Remove-Item "$env:LOCALAPPDATA\Bexora" -Recurse -Force
```

Bexora will request a bot token again the next time it starts.

---

## Portable Application

The official Bexora release requires only:

```text
Bexora.exe
```

Images, GIFs, icons, and other required application resources are included inside the official build.

You do not need:

```text
.env
nukegif/
Python
additional runtime files
```

---

## Bot Token Security

Your Discord bot token is a private credential.

Never publish or share it through:

- GitHub repositories
- screenshots
- videos
- logs
- issue reports
- public ZIP files
- Discord messages
- support requests

If a token is accidentally exposed, regenerate it immediately through Discord's developer settings.

---

## Internet Connection

An internet connection is required for bot authentication and other Discord-related functionality.

Bexora may be unable to authenticate if Discord is unavailable or the current network blocks access to Discord services.

---

## Official Builds

Only releases published through the official Bexora repository should be considered official.

Executables obtained from unknown mirrors, reuploads, unofficial repositories, or third-party download pages may have been modified.

Modified or repackaged builds are not supported.

---

## Windows Security

Windows SmartScreen or Microsoft Defender may display a warning for newly published executables that do not yet have established reputation or a recognized code-signing certificate.

Always download Bexora from the official repository.

---

## Troubleshooting

### Bexora asks for the token again

The previously stored token may have been revoked, regenerated, deleted, or invalidated.

Enter a valid token again.

### The token is rejected

Verify that:

```text
the token is correct
the bot still exists
the token has not been regenerated
Discord is reachable
your internet connection is working
```

### Images or GIFs are missing

Official standalone builds contain the required application assets internally.

Make sure you are running an original official Bexora release.

### Bexora does not start

Make sure the executable was fully extracted before running it.

Do not run Bexora directly from inside a `.zip` or `.rar` archive.

---

## Compatibility

```text
Operating System: Windows
Architecture: 64-bit
Distribution: Standalone executable
Configuration: Built-in bot authentication
```

---

## Usage Notice

Bexora is intended for authorized use only.

You are responsible for ensuring that you have permission to use the application with any Discord bot, server, account, environment, system, or service where it is executed.

---

## Support

Support applies only to official Bexora releases.

When requesting support, never include your real Discord bot token.

---

## Copyright

Copyright © 2026 **bejj0taa**

All rights reserved.

Bexora and its official release materials may not be represented as another person's original work.

Modified builds must not be presented as official Bexora releases.

---

**Official Repository:** `bejj0taa/Bexora`
