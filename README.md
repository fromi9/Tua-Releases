# Tua — Your Budget & Tua Studio

A personal finance tracker and a pixel art editor for Windows.

**Latest release: beta 2 (Windows x64)**

- **Tua: Your Budget:** 1.0.0-beta.2
- **Tua Studio:** 0.1.0-beta.2

**[Download the latest release](https://github.com/fromi9/Tua-Releases/releases/tag/1.0.0-beta.2)**

Both applications are still in development. These are public preview builds, not finished products.

---

## About the project

Hi! Tua is a hobby project I've been working on in my spare time.

I originally made it for myself and never really planned to release it. I'm not a programmer, and most of the code was written with the help of AI tools. I've mainly been responsible for the ideas, interface design, testing, and deciding how everything should work.

At some point, the project grew into something much bigger than I expected, so I decided to share it. Maybe someone else will find it useful.

Tua currently consists of two Windows applications:

- **Tua: Your Budget** — a personal finance tracker.
- **Tua Studio** — a pixel art editor for creating custom content for Budget.

Both applications are still in development, especially Studio. There are probably bugs, unfinished features, and things I haven't tested properly yet.

## Tua: Your Budget

Budget is the main application. It's a personal finance tracker that works locally on your computer, without requiring an account or an online service.

Here's what you can do with it:

- Track income and expenses.
- Create categories and subcategories.
- Set spending limits.
- Create savings goals and track your progress.
- Manage recurring payments and reminders.
- View transaction history and spending statistics.
- Work with different currencies and retrieve exchange rates.
- Create and restore local backups.
- Optionally encrypt financial data using Windows DPAPI.
- Export password-protected portable backups.
- Customize the interface with themes, backgrounds, music, and animated pixel-art companions.

You can also create your own appearance packs using Tua Studio.

<img width="1920" height="1009" alt="Tua Budget screenshot 1" src="https://github.com/user-attachments/assets/53140001-a7f1-4840-8ede-5fb4789be3bf" />
<img width="1920" height="1009" alt="Tua Budget screenshot 2" src="https://github.com/user-attachments/assets/6ea1b054-65f8-4e18-9d30-c47c771b1993" />
<img width="1920" height="1009" alt="Tua Budget screenshot 3" src="https://github.com/user-attachments/assets/0ab8335e-4e87-423c-ac49-79e21fd02034" />
<img width="1920" height="1009" alt="Tua Budget screenshot 4" src="https://github.com/user-attachments/assets/ecb6e858-1489-46f4-b98c-b98b2da74074" />
<img width="1920" height="1009" alt="Tua Budget screenshot 5" src="https://github.com/user-attachments/assets/199a3495-4711-46dd-b8d4-9bc4d87cd1ab" />
<img width="1920" height="1009" alt="Tua Budget screenshot 6" src="https://github.com/user-attachments/assets/318ad185-4e05-4f10-ae97-47d59e5a057d" />

## Tua Studio (Experimental)

Studio is a separate application I made for creating pixel art, animations, and custom content for Budget.

It currently includes:

- Pixel art drawing with layers.
- Frame-by-frame animation.
- Character movements and expressions.
- Animals and decorations.
- Backgrounds and ground textures.
- Weather effects and scene previews.
- Exporting custom packs for Budget.

Studio is still pretty rough compared to Budget. Some tools might behave strangely, and I'm sure there are bugs I haven't discovered yet.

If you decide to try it, please keep copies of your `.tuastudio` project files. Exported packs are meant to be used in Budget and don't replace the original editable projects.

**You don't need Studio to use Budget.** Both applications can be installed separately.

<img width="1920" height="1009" alt="Tua Studio screenshot 1" src="https://github.com/user-attachments/assets/68a78d2e-0f26-4c10-b1a0-a0287e9f86a1" />
<img width="1920" height="1009" alt="Tua Studio screenshot 2" src="https://github.com/user-attachments/assets/85d6699e-ed8e-46ba-ab17-bad5626ca5e3" />

## What's new in beta 2

The main focus of beta 2 is financial-data protection and reliability.

### Optional financial-data encryption

- Added automatic financial-data encryption using Windows DPAPI CurrentUser.
- Encryption can be enabled optionally.
- No password is required at every startup when automatic encryption is enabled.
- Automatic backups are encrypted while financial-data encryption is enabled.
- Portable `.tuabackup` exports use a separate password and recovery key, allowing restoration without the original Windows encryption key.

### Data safety improvements

- Improved financial-data saving and file replacement safety.
- Failed decryption prevents the application from opening and saving an empty replacement budget.
- Safer encryption-mode switching preserves original data when tested migration or write operations fail.
- Existing data paths and project formats are retained.

These improvements reduce certain risks but do not guarantee protection against every possible failure.

For the complete changelog and limitations, see the [beta 2 release notes](https://github.com/fromi9/Tua-Releases/releases/tag/1.0.0-beta.2).

## Privacy and data storage

One of the things I wanted from the beginning was to keep everything as local as possible.

Tua doesn't require an account, and there's no cloud synchronization or analytics telemetry built into the applications.

Your financial data is stored locally on your computer. Budget normally only connects to the internet to retrieve currency exchange rates. Your transaction history and account balances aren't sent with those requests.

### Default storage locations on Windows

- **Budget data and settings:** `%AppData%\ExpenseTracker`
- **Budget backups:** `Documents\My Budget backups`
- **Studio projects:** `%AppData%\ExpenseTracker\TuaStudio\Projects`

Older installations may use a different backup folder name.

### Financial-data encryption

Starting with beta 2, Budget supports optional automatic encryption of financial data using Windows DPAPI CurrentUser.

When enabled, encryption is tied to your Windows user account.

**Important:** If your Windows profile is deleted, lost, or reinstalled, encrypted financial data and Windows-bound backups may become inaccessible.

Before reinstalling Windows or moving to another computer, create a portable password-protected `.tuabackup` backup and keep its password and recovery key safe.

Previously encrypted backups retain their original protection even after changing the main profile's encryption mode.

Appearance settings, images, and Studio projects are not included in financial-data encryption.

Encryption does not securely erase previously stored plaintext copies or old cloud versions.

If your Documents folder is synchronized with OneDrive or another cloud service, backups stored there may also be uploaded by that service.

**Please keep independent backups, especially while using beta software.**

## Languages

Tua currently supports nine languages:

English, Russian, German, French, Italian, Spanish, Japanese, Korean, and Simplified Chinese.

English is the default for new installations.

Some translations are still preliminary and may contain mistakes or layout issues. If you notice anything strange, feel free to report it.

After changing the language in Studio, save your project and restart the application.

## Installation

Both applications are available as separate Windows x64 downloads.

### Available packages

- **Windows Installer (.exe)** — standard per-user installation.
- **Portable ZIP (.zip)** — extract and run without installation.

The .NET runtime is bundled, so no separate .NET installation is required.

Installers do not require administrator privileges. Desktop shortcuts are optional.

ZIP builds still use standard Windows user directories for application data. They are not fully self-contained portable profiles.

Uninstalling should leave your personal data and projects untouched.

The builds are not digitally signed, so Windows may display an unknown publisher or SmartScreen warning.

A `SHA256SUMS.txt` file is provided with SHA-256 checksums for all four downloads.

**[Download Tua beta 2](https://github.com/fromi9/Tua-Releases/releases/tag/1.0.0-beta.2)**

### Before updating

- Close all running Budget instances.
- Back up your financial data and editable Studio projects.
- Do not delete AppData when updating.
- Remember that older versions may not understand encrypted financial files.

These early preview releases use the same data folders, so updates aren't completely isolated from previous installations.

## Known issues and limitations

A few things worth knowing before trying Tua:

- Studio is still experimental and needs more testing.
- Some translations may contain incorrect wording or layout problems.
- Animated backgrounds and visual effects can use a noticeable amount of CPU.
- Performance on older or less powerful computers hasn't been tested thoroughly.
- There are probably bugs I haven't encountered on my own computer.
- Recovery on a second physical computer or Windows account hasn't been fully tested.
- Broader manual UI and hardware testing is still incomplete.

The beta 2 encryption verification suite passed **390 automated tests** before packaging, including tests involving corrupted files, unavailable keys, backup recovery, and interrupted file replacement.

This number refers to the encryption verification suite, not necessarily every test across both applications.

Automated testing doesn't guarantee that everything is bug-free.

If you're experiencing performance problems, try lowering the animation frame rate or disabling some visual effects.

**Please don't use beta software as your only financial record.**

## Bugs and feedback

If you find a bug, please open an issue here on GitHub.

It would help if you could include:

- Which application you're using (Budget or Studio).
- Your Windows version.
- What you were doing when the problem happened.
- What you expected to happen and what actually happened.
- A screenshot or error message, if possible.

For performance issues, mentioning your CPU and which visual effects are enabled would also be useful.

Please make sure screenshots and logs don't contain any private financial information.

I'm also interested in suggestions, opinions about the interface, and anything that feels confusing or unnecessary.

## A final note

Tua started as a small personal project and ended up becoming much bigger than I originally planned.

I'm still learning, and I work on it in my spare time, so I can't promise regular updates or quick fixes. But I'd like to keep improving it.

If you give it a try, I'd be happy to hear what you think.

Thanks for checking out Tua!
