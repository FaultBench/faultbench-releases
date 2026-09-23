<div align="center">

<img src="assets/mark.png" alt="FaultBench" width="120" height="120">

# FaultBench

**Answers from the service manuals on your own machine.**

<img src="assets/alpha-badge.svg" alt="Alpha — pre-release" height="38">
&nbsp;
<img src="assets/offline-badge.svg" alt="Runs with no signal" height="38">

<br><br>

[![Latest release](https://img.shields.io/github/v/release/FaultBench/faultbench-releases?include_prereleases&sort=semver&label=latest&labelColor=122442&color=0061FD&style=for-the-badge)](https://github.com/FaultBench/faultbench-releases/releases/latest)
[![Downloads](https://img.shields.io/github/downloads/FaultBench/faultbench-releases/total?labelColor=122442&color=0061FD&style=for-the-badge)](https://github.com/FaultBench/faultbench-releases/releases)
[![Windows](https://img.shields.io/badge/Windows-10%20%2F%2011-122442?style=for-the-badge&logo=windows&logoColor=white)](#-download)
[![Linux](https://img.shields.io/badge/Linux-deb%20%2F%20AppImage-122442?style=for-the-badge&logo=linux&logoColor=white)](#-download)

### [⬇&nbsp;&nbsp;Download the latest release](https://github.com/FaultBench/faultbench-releases/releases/latest)

</div>

---

## Contents

- [What it is](#-what-it-is)
- [Before you install](#-before-you-install)
- [Download](#-download)
- [Your computer will warn you](#-your-computer-will-warn-you-about-this-download)
- [Mac — please wait](#-mac--please-wait-for-the-next-release)
- [What it can't do yet](#-what-it-cant-do-yet)
- [Tell us when it's wrong](#-something-wrong-tell-us)

---

## 🔍 What it is

You import a PDF service manual. You describe the fault the way you'd say it out loud — *"unit runs but the house never gets cool"*. FaultBench gives you the checks to make, and the manual page each one came from.

Every answer is built out of passages it actually retrieved from your manuals. When the manual doesn't support an answer, it says so instead of guessing. You can open the page and see for yourself.

The language model runs on your machine. **Nothing you type and no manual you import leaves the device.**

---

## 📋 Before you install

> [!IMPORTANT]
> **Alpha builds stop working 100 days after they were built.**
> The date is fixed when the installer is made, so reinstalling the same file does not reset it. The app shows you the date, and warns in the title bar for the last fortnight. Come back here for a newer build when it expires.

**The model downloads once.** On first launch FaultBench works out what your computer can run and fetches a model — around 2.3 GB on a typical laptop. You need a connection for that step only. After it finishes, it works in a basement with no signal.

You do **not** need to install Java, Node, Rust or Ollama. Everything else is inside the installer.

---

## 💾 Download

Everything is on the **[latest release page](https://github.com/FaultBench/faultbench-releases/releases/latest)**. Pick the file for your machine:

| Your machine | File to take |
| :--- | :--- |
| 🪟 &nbsp;Windows 10 / 11, 64-bit | `..._x64-setup.exe` |
| 🐧 &nbsp;Ubuntu / Debian | `..._amd64.deb` |
| 🐧 &nbsp;Other Linux | `..._amd64.AppImage` |
| 🍎 &nbsp;Mac | **not yet — [see below](#-mac--please-wait-for-the-next-release)** |

**Linux install:**

```bash
sudo apt install ./FaultBench_*_amd64.deb     # apt, not dpkg, so dependencies resolve
```

```bash
chmod +x FaultBench_*_amd64.AppImage && ./FaultBench_*_amd64.AppImage
```

Both are built on Ubuntu 22.04 and need a glibc at least that new.

---

## ⚠️ Your computer will warn you about this download

FaultBench has no code signing certificate yet. A certificate is what lets an operating system say who built a program and prove nobody changed it since. Without one, Windows and macOS assume the worst.

Nothing is wrong with the file — but you shouldn't take our word for that alone. Every release ships `SHA256SUMS.txt`. It can't prove *who* built the file, but it proves the file you downloaded is exactly the one the build produced. It takes ten seconds:

```powershell
# Windows, in PowerShell
Get-FileHash .\FaultBench_*_x64-setup.exe -Algorithm SHA256
```

```bash
# Linux
sha256sum FaultBench_*_amd64.deb
```

Compare what you get against the line for your file in `SHA256SUMS.txt`. If they don't match, don't open it — tell us.

> **Windows:** SmartScreen will say *"Windows protected your PC"*. Click **More info**, then **Run anyway**.

---

## 🍎 Mac — please wait for the next release

The Mac builds are *ad-hoc signed*, which means signed by nobody. macOS doesn't warn you about these and let you continue — it refuses the app and removes it. There's no button to click, so there's nothing we can tell you to click.

This needs an Apple Developer ID and notarization, and it's the next thing being fixed. The `.dmg` files are attached to releases for completeness, **not for use.** If you're on a Mac, sit this one out.

---

## 🚧 What it can't do yet

- **It can't read diagrams or schematics.** Retrieval works on text. Ask about a wiring diagram and FaultBench should decline rather than invent an answer. If it ever invents one, that's the most valuable bug you can report.
- **One manufacturer at a time works best.** A question spanning several manuals can pull a procedure from the wrong machine.
- **It's a starting point, not an authority.** Every check cites its page. Open the page. Use your own judgement and follow proper safety procedures.
- **No installed build has been through a full test pass on a clean machine.** You are genuinely among the first. That's what alpha means.

---

## 🐛 Something wrong? Tell us

**In the app:** the **Feedback** tab sends a note straight to support. It carries only what you type, your reply address if you give one, and the version number — never your manuals, your diagnoses or your logs.

**Here:** [open an issue](https://github.com/FaultBench/faultbench-releases/issues/new).

For a crash or a wrong answer, the **Diagnostics** tab has a **Copy for a bug report** button. Paste that in. It carries timings and error messages, and deliberately carries nothing you typed and nothing your manuals say.

> The single most useful report is **an answer that was confidently wrong** — tell us the question you asked and which manual you had imported.

---

<div align="center">
<sub>This repository holds downloads only. FaultBench's source is maintained privately.</sub>
</div>
