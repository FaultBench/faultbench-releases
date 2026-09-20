<div align="center">

<img src="assets/mark.png" alt="FaultBench" width="128" height="128">

# FaultBench

**Answers from the service manuals on your own machine.**

<img src="assets/alpha-badge.svg" alt="Alpha 0.1.0 — macOS pending" height="40">
&nbsp;
<img src="assets/offline-badge.svg" alt="Runs with no signal" height="40">

### [⬇&nbsp; Download the latest release](https://github.com/adisagar2003/faultbench-releases/releases/latest)

</div>

---

## What it is

You import a PDF service manual. You describe the fault the way you'd say it out loud — *"unit runs but the house never gets cool"*. FaultBench gives you the checks to make, and the manual page each one came from.

Every answer is built out of passages it actually retrieved from your manuals. When the manual doesn't support an answer, it says so instead of guessing. You can open the page and see for yourself.

The language model runs on your machine. **Nothing you type and no manual you import leaves the device.**

## Before you install

**The model downloads once.** On first launch FaultBench works out what your computer can run and fetches a model — around 2.3 GB on a typical laptop. You need a connection for that step only. After it finishes, it works in a basement with no signal.

You do **not** need to install Java, Node, Rust or Ollama. Everything else is inside the installer.

## Download

| Your machine | File |
| --- | --- |
| Windows 10 / 11, 64-bit | `FaultBench_0.1.0_x64-setup.exe` |
| Ubuntu / Debian | `FaultBench_0.1.0_amd64.deb` |
| Other Linux | `FaultBench_0.1.0_amd64.AppImage` |
| Mac | **not yet — see below** |

Everything is on the [releases page](https://github.com/adisagar2003/faultbench-releases/releases).

## Your computer will warn you about this download

FaultBench has no code signing certificate yet. A certificate is what lets an operating system say who built a program and prove nobody changed it since. Without one, Windows and macOS assume the worst.

Nothing is wrong with the file — but you shouldn't take our word for that alone. Every release ships `SHA256SUMS.txt`. It can't prove *who* built the file, but it proves the file you downloaded is exactly the one the build produced. It takes ten seconds:

```powershell
# Windows, in PowerShell
Get-FileHash .\FaultBench_0.1.0_x64-setup.exe -Algorithm SHA256
```

```bash
# Linux
sha256sum FaultBench_0.1.0_amd64.deb
```

Compare what you get against the line for your file in `SHA256SUMS.txt`. If they don't match, don't open it — tell us.

**Windows:** SmartScreen will say *"Windows protected your PC"*. Click **More info**, then **Run anyway**.

**Linux:**

```bash
sudo apt install ./FaultBench_0.1.0_amd64.deb     # apt, not dpkg, so dependencies resolve
```

```bash
chmod +x FaultBench_0.1.0_amd64.AppImage && ./FaultBench_0.1.0_amd64.AppImage
```

Both are built on Ubuntu 22.04 and need a glibc at least that new.

## Mac — please wait for the next release

The Mac builds are *ad-hoc signed*, which means signed by nobody. macOS doesn't warn you about these and let you continue — it refuses the app and removes it. There's no button to click, so there's nothing we can tell you to click.

This needs an Apple Developer ID and notarization, and it's the next thing being fixed. The `.dmg` files are attached to releases for completeness, **not for use.** If you're on a Mac, sit this one out.

## What it can't do yet

- **It can't read diagrams or schematics.** Retrieval works on text. Ask about a wiring diagram and FaultBench should decline rather than invent an answer. If it ever invents one, that's the most valuable bug you can report.
- **One manufacturer at a time works best.** A question spanning several manuals can pull a procedure from the wrong machine.
- **It's a starting point, not an authority.** Every check cites its page. Open the page. Use your own judgement and follow proper safety procedures.
- **No installed build has been through a full test pass on a clean machine.** You are genuinely among the first. That's what alpha means.

## Something wrong? Tell us

Open an issue right here: **[report a problem](https://github.com/adisagar2003/faultbench-releases/issues/new)**

Inside the app, the **Diagnostics** tab has a **Copy for a bug report** button. Paste that in. It carries timings and error messages, and deliberately carries nothing you typed and nothing your manuals say.

The single most useful report is **an answer that was confidently wrong** — tell us the question you asked and which manual you had imported.

---

<div align="center">
<sub>This repository holds downloads only. FaultBench's source is maintained privately.</sub>
</div>
